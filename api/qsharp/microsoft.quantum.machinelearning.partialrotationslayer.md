---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196249"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve una matriz de giros de un solo qubit a lo largo de un eje determinado, parametrizado por parámetros de modelo distintos.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

Índices de qubits que se van a usar como destinos para cada rotación.


### <a name="axis--pauli"></a>eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Eje de giro de cada giro de la capa especificada.



## <a name="output--controlledrotation"></a>Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Matriz de giros controlados sobre el eje dado, uno en cada `nQubits` qubits.