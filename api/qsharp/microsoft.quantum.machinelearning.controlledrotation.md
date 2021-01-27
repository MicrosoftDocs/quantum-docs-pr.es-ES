---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido por el usuario ControlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847392"
---
# <a name="controlledrotation-user-defined-type"></a>Tipo definido por el usuario ControlledRotation

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="example"></a>Ejemplo

Lo siguiente representa un giro sobre el $X $ Axis del primer qubit de un registro, controlado en el segundo qubit y con un ángulo dado por el cuarto parámetro en un modelo secuencial:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Observaciones

Una rotación no controlada se puede representar estableciendo `ControlIndices` en una matriz vacía de índices, `new Int[0]` .