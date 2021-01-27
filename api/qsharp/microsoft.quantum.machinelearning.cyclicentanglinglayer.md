---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847383"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve una matriz de rotaciones de control individual a lo largo de un eje determinado, organizadas cíclicamente por un registro de qubits y parametrizado por parámetros de modelo distintos.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en función de la capa especificada.


### <a name="axis--pauli"></a>eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Eje de giro de cada giro de la capa especificada.


### <a name="stride--int"></a>STRIDE: [int](xref:microsoft.quantum.lang-ref.int)

La separación entre el destino y los índices de control para cada rotación.



## <a name="output--controlledrotation"></a>Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Una matriz de rotaciones controladas de dos qubits que se distribuyen cíclicamente a lo largo de un registro de `nQubits` qubits.

## <a name="example"></a>Ejemplo

Los siguientes son equivalentes:

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```