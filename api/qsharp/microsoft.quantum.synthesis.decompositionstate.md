---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Tipo definido por el usuario DecompositionState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733909"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="9e688-102">Tipo definido por el usuario DecompositionState</span><span class="sxs-lookup"><span data-stu-id="9e688-102">DecompositionState user defined type</span></span>

<span data-ttu-id="9e688-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9e688-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9e688-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e688-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e688-105">Estado durante la descomposición en función de los índices de variable</span><span class="sxs-lookup"><span data-stu-id="9e688-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="9e688-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="9e688-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="9e688-107">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9e688-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="9e688-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="9e688-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="9e688-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="9e688-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="9e688-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e688-110">Description</span></span>

<span data-ttu-id="9e688-111">El estado contiene la permutación actual y las funciones generadas actualmente para las puertas controladas a la izquierda y las puertas controladas a la derecha.</span><span class="sxs-lookup"><span data-stu-id="9e688-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>