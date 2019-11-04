---
title: Trabajar con qubits | Microsoft Docs
description: Trabajar con qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183478"
---
# <a name="working-with-qubits"></a>Trabajar con qubits #

Teniendo en cuenta que ahora hay una variedad de diferentes partes del lenguaje de preguntas y respuestas, vamos a profundizar en ella y veremos cómo usar qubits.

## <a name="allocating-qubits"></a>Asignar qubits ##

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

## <a name="intrinsic-operations"></a>Operaciones intrínsecas ##

Una vez asignado, una qubit se puede pasar a las funciones y operaciones.
En cierto sentido, esto es todo lo que puede hacer un programa de Q # con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.
Veremos estas operaciones con más detalle en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), pero por ahora se mencionan algunas operaciones útiles que se pueden usar para interactuar con qubits.

En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q # por las operaciones intrínsecas `X`, `Y`y `Z`, cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)`.
Tal y como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ y, por lo tanto, `X` como una operación de volteo de bits o no como una puerta.
Esto nos permite preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Más adelante, veremos formas más compactas de escribir esta operación que no requieren el control de flujo manual.

También podemos preparar estados como $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ y $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ mediante la transformación Hadamard $H $ , que se representa en Q # mediante la operación intrínseca `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Medidas ##

Con la operación de `Measure`, que es una operación no de unitario intrínseca integrada, podemos extraer información clásica de un objeto de tipo `Qubit` y asignar un valor clásico como resultado, que tiene un tipo reservado `Result`, que indica que el resultado es no el estado de Quantum es mayor. La entrada a `Measure` es un eje Pauli en la esfera Bloch, representado por un objeto de tipo `Pauli` (es decir, por ejemplo `PauliX`) y un objeto de tipo `Qubit`. 

Un ejemplo sencillo es la siguiente operación, que crea un qubit en $ \ket{0}$ State y, a continuación, aplica una puerta de Hadamard ``H`` a él y, a continuación, mide el resultado en la `PauliZ` base. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

La siguiente operación proporciona un ejemplo ligeramente más complicado que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` se encuentran en el estado cero, cuando se miden en una base de Pauli especificada y `false` en caso contrario. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

El lenguaje Q # permite las dependencias del flujo de control clásico en los resultados de la medición de qubits. A su vez, esto permite implementar gadgets de probabilística eficaces que pueden reducir el costo de cálculo para implementar unitaries. Por ejemplo, es fácil de implementar, lo que se conoce como *repetir-hasta-éxito* en Q #, que son los circuitos probabilística que tienen un costo bajo *esperado* en cuanto a las puertas elementales, pero para los que el costo real depende de una ejecución real y de un intercalación de varias ramificaciones posibles. 

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
donde `statementBlock1` y `statementBlock2` son cero o más instrucciones Q # y `expression` cualquier expresión válida que se evalúe como un valor de tipo `Bool`. En un caso de uso típico, el circuito siguiente implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt{5}$ en la esfera Bloch. Esto se logra mediante el uso de un patrón de RU conocido: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

En este ejemplo se muestra el uso de una variable mutable `finished` que está en el ámbito de todo el bucle de repetición hasta la corrección y que se inicializa antes del bucle y se actualiza en el paso de corrección.

Por último, se muestra un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partir del estado $ \ket{+} $. Vea también el [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Las características de programación más importantes que se muestran en esta operación son una parte más compleja `fixup` del bucle que implica operaciones Quantum y el uso de instrucciones `AssertProb` para determinar la probabilidad de medir el estado de cuanto en determinados puntos especificados en el introduce. Vea también [probar y depurar](xref:microsoft.quantum.techniques.testing-and-debugging) para obtener más información sobre las instrucciones `Assert` y `AssertProb`. 
