---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido por el usuario ControlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196572"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="8856f-102">Tipo definido por el usuario ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="8856f-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="8856f-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8856f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8856f-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8856f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="8856f-105">Describe una rotación controlada en cuanto a sus índices de destino y de control, el eje de giro y el índice en un vector de parámetro de modelo.</span><span class="sxs-lookup"><span data-stu-id="8856f-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="8856f-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="8856f-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="8856f-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8856f-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8856f-108">Índice del qubit de destino para esta rotación controlada.</span><span class="sxs-lookup"><span data-stu-id="8856f-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="8856f-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8856f-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8856f-110">Matriz de los índices de qubit de control para este giro.</span><span class="sxs-lookup"><span data-stu-id="8856f-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="8856f-111">Eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8856f-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8856f-112">Eje de este giro.</span><span class="sxs-lookup"><span data-stu-id="8856f-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="8856f-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8856f-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8856f-114">Índice de un vector de parámetro de modelo que describe el ángulo de este giro.</span><span class="sxs-lookup"><span data-stu-id="8856f-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="8856f-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8856f-115">Remarks</span></span>

<span data-ttu-id="8856f-116">Una rotación no controlada se puede representar estableciendo `ControlIndices` en una matriz vacía de índices, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="8856f-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>