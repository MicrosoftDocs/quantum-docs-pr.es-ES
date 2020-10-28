---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Descomponer función
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733916"
---
# <a name="decomposedon-function"></a><span data-ttu-id="09b92-102">Descomponer función</span><span class="sxs-lookup"><span data-stu-id="09b92-102">DecomposedOn function</span></span>

<span data-ttu-id="09b92-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="09b92-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="09b92-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09b92-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09b92-105">Descompone una permutación en una variable</span><span class="sxs-lookup"><span data-stu-id="09b92-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="09b92-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b92-106">Description</span></span>

<span data-ttu-id="09b92-107">Dada una permutación $ \pi $ ( `perm` ) y un índice $i $ ( `index` ), este método devuelve tres permutaciones $ ((\ pi_l, \ PI_R), \pi ') $ de modo que las imágenes de $ \ pi_l $ y $ \ PI_R $ no cambian bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambie el bit $i $ en sus elementos.</span><span class="sxs-lookup"><span data-stu-id="09b92-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="09b92-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="09b92-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="09b92-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="09b92-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="09b92-110">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09b92-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="09b92-111">Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="09b92-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

