---
title: Trabajar con qubits
description: 'Trabajar con las técnicas qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820001"
---
# <a name="working-with-qubits"></a>Trabajar con qubits

Teniendo en cuenta que ahora hay una variedad de diferentes partes del lenguaje de preguntas y respuestas, vamos a profundizar en ella y veremos cómo usar qubits.

## <a name="allocating-qubits"></a>Asignar qubits

En primer lugar, para obtener un qubit que podamos usar en Q #, *asignamos* qubits dentro de un bloque `using`:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Los qubits asignados de esta manera se inician en $ \ket{0}$ State; en el ejemplo anterior, `register` está por tanto en el estado $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
Al final del bloque `using`, se desasignan inmediatamente los qubits asignados por ese bloque y no se pueden usar más.

> [!WARNING]
> Los equipos de destino esperan que los qubits se encuentren en $ \ket{0}$ State inmediatamente antes de la desasignación, de modo que se puedan volver a usar y ofrecer a otros bloques de `using` para su asignación.
> Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket{0}$.
> Si es necesario, la operación de @"microsoft.quantum.intrinsic.reset" se puede usar para medir un qubit en su lugar y para usar ese resultado de medida para asegurarse de que el qubit medido se devuelve a $ \ket{0}$. Dicha medida destruirá cualquier inenredo con el resto de qubits y, por tanto, puede afectar al cálculo.

## <a name="intrinsic-operations"></a>Operaciones intrínsecas

Una vez asignado, una qubit se puede pasar a las funciones y operaciones.
En cierto sentido, esto es todo lo que puede hacer un programa de Q # con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.
Veremos estas operaciones con más detalle en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), pero por ahora se mencionan algunas operaciones útiles que se pueden usar para interactuar con qubits.

En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q # por las operaciones intrínsecas `X`, `Y`y `Z`, cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)`.
Tal y como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ y, por lo tanto, `X` como una operación de volteo de bits o no como una puerta.
La operación `X` nos permite preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Más adelante, veremos formas más compactas de escribir esta operación que no requieren el control de flujo manual.

También podemos preparar estados como $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ y $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ mediante la transformación Hadamard $H $, que se representa en Q # mediante la operación intrínseca `H : (Qubit => Unit is Adj + Ctl)`:

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Medidas

Con la operación de `Measure`, que es una operación no unitario intrínseca integrada, podemos extraer información clásica de un objeto de tipo `Qubit` y asignar un valor clásico como resultado, que tiene un tipo reservado `Result`, que indica que el resultado ya no es un estado Quantum.
La entrada a `Measure` es un eje Pauli en la esfera Bloch, representada por un valor de tipo `Pauli` (por ejemplo `PauliX`) y un valor de tipo `Qubit`.

Un ejemplo sencillo es la siguiente operación, que asigna un qubit en $ \ket{0}$ State, aplica una operación Hadamard `H` a él y mide el resultado en la `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

La siguiente operación proporciona un ejemplo ligeramente más complicado, que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` se encuentran en el estado cero cuando se miden en una base de Pauli especificada y devuelve `false` de lo contrario.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

El lenguaje Q # permite que el flujo de control clásico dependa de los resultados de la medición de qubits.
Esta funcionalidad, a su vez, permite implementar gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.
Por ejemplo, es fácil implementar los modelos de *repetición-hasta el éxito* (RU) que se conocen en Q #.
Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales, pero para los que el costo real depende de una ejecución real y una intercalación real de varias ramas posibles.

Para facilitar patrones de repetición hasta la correcta (RU), Q # admite la construcción

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

donde `statementBlock1` y `statementBlock2` son cero o más instrucciones Q # y `expression` cualquier expresión válida que se evalúe como un valor de tipo `Bool`.
En un caso de uso típico, la siguiente operación de Q # implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt{5}$ en la esfera Bloch. Esto se logra mediante el uso de un patrón de RU conocido:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

En este ejemplo se muestra el uso de una variable mutable `finished` que está en el ámbito de todo el bucle de repetición hasta la corrección y que se inicializa antes del bucle y se actualiza en el paso de corrección.

Por último, se muestra un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partir del estado $ \ket{+} $.
Vea también el [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Las características de programación más importantes que se muestran en esta operación son una parte más compleja `fixup` del bucle, lo que implica operaciones Quantum y el uso de instrucciones `AssertProb` para determinar la probabilidad de medir el estado de cuanto en determinados puntos especificados en el programa.
Vea también [pruebas y depuración](xref:microsoft.quantum.techniques.testing-and-debugging) para obtener más información sobre las operaciones de [`Assert`](xref:microsoft.quantum.intrinsic.assert) y [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .
