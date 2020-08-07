---
title: Trabajo con qubits
description: Descripción de relleno
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867869"
---
# <a name="working-with-qubits"></a>Trabajo con qubits

Qubits son el objeto fundamental de la información en la informática Quantum. Para obtener una introducción general a qubits, consulte [Descripción de Quantum Computing](xref:microsoft.quantum.overview.understanding)y para profundizar más en su representación matemática, vea [qubit](xref:microsoft.quantum.concepts.qubit). 

En este artículo se explica cómo usar qubits en un Q# programa. 

> [!IMPORTANT]
>Ninguna de las instrucciones que se describen en este artículo son válidas dentro del cuerpo de una función. Solo son válidos dentro de las operaciones.

## <a name="allocating-qubits"></a>Asignar qubits

Dado que los qubits físicos son recursos valiosos en un equipo Quantum, parte del trabajo del compilador es asegurarse de que se usan de la forma más eficaz posible.
Como tal, debe indicar a que Q# *asigne* qubits para su uso dentro de un bloque de instrucciones determinado.
Puede asignar qubits como un qubit único o como una matriz de qubits, que se conoce como *registro*. 

### <a name="clean-qubits"></a>Limpiar qubits

Use la `using` instrucción para asignar nuevos qubits para su uso durante un bloque de instrucciones.

La instrucción consta de la palabra clave `using` , seguida de un enlace entre paréntesis `( )` y el bloque de instrucciones en el que están disponibles los qubits.
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

Cualquier qubits asignado de este modo se inicia en el estado $ \ket {0} $. Por lo tanto, en el ejemplo anterior, `auxiliary` es un único qubit en el estado $ \ket {0} $ y `register` está en el estado de cinco qubit $ \ket {00000} = \ket \otimes \ket \otimes {0} {0} \cdots \otimes \ket {0} $.
Al final del `using` bloque, cualquier qubits asignado por ese bloque se desasigna inmediatamente y no se puede usar más.

> [!WARNING]
> Los equipos de destino pueden reutilizar qubits desasignadas y ofrecerlas a otros `using` bloques para su asignación. Como tal, el equipo de destino espera que qubits se encuentren en el {0} Estado $ \ket $ inmediatamente antes de la desasignación.
> Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket {0} $.
> Si es necesario, puede usar la @"microsoft.quantum.intrinsic.reset" operación, que devuelve qubit a $ \ket {0} $ mediante la medición y la realización condicional de una operación basada en el resultado. Esta medida destruye cualquier inenredo con el Qubits restante y, por tanto, puede afectar al cálculo.


### <a name="borrowed-qubits"></a>Qubits prestado

Use la `borrowing` instrucción para asignar qubits para uso temporal, que no tienen que estar en un estado específico.

Puede usar qubits prestado como espacio de desecho durante un cálculo.
Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket {0} $.
A menudo se hace referencia a ellos como "sucios" qubits porque su estado es desconocido e incluso pueden estar inscritos con otras partes de la memoria del equipo Quantum.

El enlace sigue el mismo patrón y las mismas reglas que la `using` instrucción.
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
El prestatario confirma que se abandone el qubits en el mismo estado en que se encontraban cuando los prestó. es decir, su estado al principio y al final del bloque de instrucciones debe ser el mismo.
Dado que este estado no es necesariamente un estado clásico, en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas. 

Al tomar prestado qubits, el sistema primero intenta rellenar la solicitud de qubits que se están usando pero no se puede tener acceso a ella durante el cuerpo de la `borrowing` instrucción.
Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.

Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.
Para ver un ejemplo de su uso en Q# , consulte el [ejemplo de qubits de préstamos](#borrowing-qubits-example) de este artículo, o la factorización de papel que [*usa 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para un algoritmo que utiliza qubits prestado.

## <a name="intrinsic-operations"></a>Operaciones intrínsecas

Una vez asignada, puede pasar un qubit a las funciones y operaciones.
En cierto sentido, esto es todo lo que un Q# programa puede hacer con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.

En este artículo se describen algunas Q# operaciones útiles que puede usar para interactuar con qubits.
Para obtener más información sobre estos y otros, consulte [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude). 

En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q# mediante las operaciones intrínsecas [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) y [`Z`](xref:microsoft.quantum.intrinsic.z) , cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)` .

Como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), piense en $X $ y `X` , por tanto, en una operación de volteo de bits o no en una puerta.
Puede usar la `X` operación para preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Más adelante, verá formas más compactas de escribir esta operación que no requieren el flujo de control manual.

También puede preparar estados como $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ y $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ mediante {2} la transformación Hadamard $H $, que se representa en Q# mediante la operación intrínseca [`H`](xref:microsoft.quantum.intrinsic.h) (también de tipo (qubit => unidad es ADJ + CTL) '):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Medidas

Las medidas de qubits individuales se pueden realizar en diferentes bases, cada una representada por un eje Pauli en la [esfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere).
La *base de cálculo* se refiere a la `PauliZ` base y es la base más común que se usa para la medición.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Medir un único qubit de `PauliZ` base

Use la [`M`](xref:microsoft.quantum.intrinsic.m) operación, que es una operación intrínseca no unitario integrada, para medir un único qubit en `PauliZ` base y asignar un valor clásico al resultado.
`M`tiene un tipo de valor devuelto reservado, `Result` , que solo puede tomar valores `Zero` o `One` que corresponden a los Estados medidos $ \ket {0} $ o $ \ket {1} $-, lo que indica que el resultado ya no es un estado Quantum.

Un ejemplo sencillo es la siguiente operación, que asigna una qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Medir uno o más qubits en bases específicas

Para medir una matriz de uno o varios qubits en bases específicas, puede utilizar la [`Measure`](xref:microsoft.quantum.intrinsic.measure) operación.

Las entradas en `Measure` son una matriz de `Pauli` tipos (por ejemplo, `[PauliX, PauliZ, PauliZ]` ) y una matriz de qubits.

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

Tenga en cuenta que en este ejemplo solo se realiza `Measure` una qubits individual de una en una, pero la operación se puede extender a las medidas conjuntas en varios qubits.

## <a name="borrowing-qubits-example"></a>Ejemplo de qubits de préstamos

Hay ejemplos en el Canon que usan la `borrowing` palabra clave, como la siguiente función `MultiControlledXBorrow` . Si `controls` denota el qubits de control que se va a agregar a una `X` operación, el número de [ancillas](xref:microsoft.quantum.glossary#ancilla) modificados agregados por esta implementación es `Length(controls)-2` .

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

Tenga en cuenta que en este ejemplo se usó un uso extensivo del `With` combinador, en su forma que es aplicable a las operaciones que admiten el tipo de adjoin, por ejemplo, `WithA` .
Este es un buen estilo de programación, ya que agregar el control a las estructuras que implican `With` propaga el control únicamente a la operación interna.
Tenga en cuenta también que, además de la `body` de la operación, `controlled` se proporcionó explícitamente una implementación del cuerpo de la operación, en lugar de recurrir a una `controlled auto` instrucción.
La razón de esto es que, debido a la estructura del circuito, es fácil agregar más controles, que es beneficioso en comparación con agregar el control a cada puerta en `body` . 

Es instructivo comparar este código con otra función `MultiControlledXClean` de Canon que logre el mismo objetivo de implementar una operación controlada por multiplicación `X` , sin embargo, que usa varios qubits limpios mediante el `using` mecanismo. 

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre el [flujo de control](xref:microsoft.quantum.guide.controlflow) en Q# .