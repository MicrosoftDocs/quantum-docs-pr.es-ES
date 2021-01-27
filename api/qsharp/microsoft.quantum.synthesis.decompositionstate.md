---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Tipo definido por el usuario DecompositionState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: eb2aed53b4116a4ea72ee732ff46c4a10eb3d67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855499"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="8d16d-102">Tipo definido por el usuario DecompositionState</span><span class="sxs-lookup"><span data-stu-id="8d16d-102">DecompositionState user defined type</span></span>

<span data-ttu-id="8d16d-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8d16d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8d16d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d16d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d16d-105">Estado durante la descomposición en función de los índices de variable</span><span class="sxs-lookup"><span data-stu-id="8d16d-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="8d16d-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="8d16d-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="8d16d-107">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d16d-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="8d16d-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8d16d-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="8d16d-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8d16d-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="8d16d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d16d-110">Description</span></span>

<span data-ttu-id="8d16d-111">El estado contiene la permutación actual y las funciones generadas actualmente para las puertas controladas a la izquierda y las puertas controladas a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8d16d-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>