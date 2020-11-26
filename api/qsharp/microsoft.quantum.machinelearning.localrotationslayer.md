---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 1549f24427f19bacbadf72e00c1c0181b64bcb73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211736"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve una matriz de giros no controlados (qubit) a lo largo de un eje determinado, con un giro para cada qubit de un registro, parametrizado por parámetros de modelo distintos.

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en función de la capa especificada.


### <a name="axis--pauli"></a>eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Eje de giro de cada giro de la capa especificada.



## <a name="output--controlledrotation"></a>Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Matriz de giros controlados sobre el eje dado, uno en cada `nQubits` qubits.