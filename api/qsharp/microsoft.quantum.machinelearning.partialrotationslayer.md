---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732324"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


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