---
title: Trabajo con qubits
description: Descripción de relleno
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430941"
---
# <a name="working-with-qubits"></a>Trabajo con qubits

Teniendo en cuenta que ahora hay una variedad de diferentes partes del lenguaje de preguntas y respuestas, vamos a profundizar en ella y veremos cómo usar qubits.

Tenga en cuenta que ninguna de estas instrucciones está permitida dentro del cuerpo de una función.
Solo son válidos dentro de las operaciones.

## <a name="allocating-qubits"></a>Asignar qubits

### <a name="clean-qubits"></a>Limpiar qubits

La `using` instrucción se usa para *asignar* nuevos qubits para su uso durante un bloque de instrucciones.

La instrucción consta de la palabra clave `using` , seguida de un paréntesis de apertura `(` , un enlace, un paréntesis de cierre `)` y el bloque de instrucciones en el que estará disponible el qubits.
El enlace sigue el mismo patrón que las `let` instrucciones: un solo símbolo o una tupla de símbolos, seguido de un signo igual `=` y un solo valor o una tupla coincidente de *inicializadores*.

Los inicializadores están disponibles para un único qubit, indicado como `Qubit()` , o una matriz de qubits, `Qubit[n]` , donde `n` es una `Int` expresión.
Por ejemplo,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Los qubits asignados de esta manera se inician en el {0} Estado $ \ket $; en el ejemplo anterior, `register` es así en el estado $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.
Al final del `using` bloque, cualquier qubits asignado por ese bloque se desasigna inmediatamente y no se puede usar más.

> [!WARNING]
> Los equipos de destino esperan que los qubits se encuentren en el estado $ \ket {0} $ inmediatamente antes de la desasignación, de modo que se puedan volver a usar y ofrecer a otros `using` bloques para su asignación.
> Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket {0} $.
> Si es necesario, la @"microsoft.quantum.intrinsic.reset" operación se puede usar para medir un qubit en su lugar y para usar ese resultado de medida para asegurarse de que el qubit medido se devuelve a $ \ket {0} $. Dicha medida destruirá cualquier inenredo con el resto de qubits y, por tanto, puede afectar al cálculo.


### <a name="borrowed-qubits"></a>Qubits prestado

La `borrowing` instrucción se usa para hacer que qubits esté disponible para uso temporal, que no es necesario que esté en un estado específico.

El mecanismo de préstamos permite la asignación de qubits que se puede usar como espacio de desecho durante un cálculo.
Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket {0} $.
A menudo se hace referencia a ellos como "sucios" qubits porque su estado es desconocido e incluso pueden estar inscritos con otras partes de la memoria del equipo Quantum.

El enlace sigue el mismo patrón y las mismas reglas que el de una `using` instrucción.
Por ejemplo,
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Los qubits prestados se encuentran en un estado desconocido y salen del ámbito al final del bloque de instrucciones.
El prestatario se compromete a mantener el qubits en el mismo estado en que se encontraban cuando se prestó, es decir, su estado al principio y al final del bloque de instrucciones se espera que sea el mismo.
En concreto, este estado no es necesariamente un estado clásico, de modo que en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas. 

Al tomar prestado qubits, el sistema intentará en primer lugar rellenar la solicitud de qubits en uso, pero no se podrá acceder a ella durante el cuerpo de la `borrowing` instrucción.
Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.


Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.
Vea el [ejemplo de qubits de préstamos](#borrowing-qubits-example) que se muestra a continuación para ver un ejemplo de su uso en Q # o la factorización del papel que [*usa 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para un algoritmo que utiliza qubits prestado.


## <a name="intrinsic-operations"></a>Operaciones intrínsecas

Una vez asignado, una qubit se puede pasar a las funciones y operaciones.
En cierto sentido, esto es todo lo que puede hacer un programa de Q # con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.
Veremos estas operaciones con más detalle en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), pero por ahora se mencionan algunas operaciones útiles que se pueden usar para interactuar con qubits.

En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q # mediante las operaciones intrínsecas `X` , `Y` y `Z` , cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)` .
Como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ y `X` , por lo tanto, como una operación de volteo de bits o no como una puerta.
La `X` operación nos permite preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:

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

También podemos preparar estados como $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ y $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ mediante {2} la transformación Hadamard $H $, que está representada en Q # por la operación intrínseca `H : (Qubit => Unit is Adj + Ctl)` :

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

Mediante la `Measure` operación, que es una operación intrínseca no unitario integrada, podemos extraer información clásica de un objeto de tipo `Qubit` y asignar un valor clásico como resultado, que tiene un tipo reservado `Result` , que indica que el resultado ya no es un estado de Quantum.
La entrada de `Measure` es un eje Pauli en la esfera Bloch, representada por un valor de tipo `Pauli` (por ejemplo, `PauliX` ) y un valor de tipo `Qubit` .

Un ejemplo sencillo es la siguiente operación, que asigna una qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.

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

La siguiente operación proporciona un ejemplo ligeramente más complicado, que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` están en el estado cero cuando se miden en una base de Pauli especificada y, de `false` lo contrario, devuelve.

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

## <a name="borrowing-qubits-example"></a>Ejemplo de qubits de préstamos

En Canon hay ejemplos que usan la `borrowing` palabra clave, por ejemplo, la función que se `MultiControlledXBorrow` define a continuación.
Si `controls` denota el qubits de control que se debe agregar a una `X` operación, `Length(controls)-2` esta implementación agregará un total de muchos ancillas modificados.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Tenga en cuenta que el uso extensivo del `With` combinador---en su forma que es aplicable a las operaciones que admiten el modo contiguo, es decir, `WithA` ---se realizó en este ejemplo.
Este es un buen estilo de programación, ya que agregar el control a las estructuras que implican `With` propaga el control únicamente a la operación interna.
Además, tenga en cuenta que aquí, además de la `body` de la operación, `controlled` se proporcionó explícitamente una implementación del cuerpo de la operación, en lugar de recurrir a una `controlled auto` instrucción.
La razón es que sabemos de la estructura del circuito cómo agregar fácilmente más controles, lo que es beneficioso en comparación con la adición de control a cada una de las puertas individuales de `body` . 

Es instructivo comparar este código con otra función `MultiControlledXClean` de Canon que logre el mismo objetivo de implementar una operación controlada por multiplicación `X` , sin embargo, que usa varios qubits limpios mediante el `using` mecanismo. 

## <a name="whats-next"></a>¿Qué debe hacer a continuación?
Obtenga información sobre el [flujo de control](xref:microsoft.quantum.guide.controlflow) en Q #.