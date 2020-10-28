---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido por el usuario ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726639"
---
# <a name="controlledrotation-user-defined-type"></a>Tipo definido por el usuario ControlledRotation

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Describe una rotación controlada en cuanto a sus índices de destino y de control, el eje de giro y el índice en un vector de parámetro de modelo.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Índice del qubit de destino para esta rotación controlada.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de los índices de qubit de control para este giro.
### <a name="axis--pauli"></a>Eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Eje de este giro.
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

Índice de un vector de parámetro de modelo que describe el ángulo de este giro.

## <a name="remarks"></a>Observaciones

Una rotación no controlada se puede representar estableciendo `ControlIndices` en una matriz vacía de índices, `new Int[0]` .