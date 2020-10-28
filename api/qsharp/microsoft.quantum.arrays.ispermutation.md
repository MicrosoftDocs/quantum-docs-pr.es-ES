---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730173"
---
# <a name="ispermutation-function"></a><span data-ttu-id="3ee3f-102">IsPermutation función)</span><span class="sxs-lookup"><span data-stu-id="3ee3f-102">IsPermutation function</span></span>

<span data-ttu-id="3ee3f-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3ee3f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3ee3f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ee3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ee3f-105">Devuelve true si y solo si una matriz determinada representa una permutación.</span><span class="sxs-lookup"><span data-stu-id="3ee3f-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="3ee3f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ee3f-106">Description</span></span>

<span data-ttu-id="3ee3f-107">Dada una matriz `array` de longitud `n` , devuelve true solo si cada entero de `0` hasta `n - 1` aparece exactamente una vez en `array` , por `array` lo que se puede interpretar como una permutación en `n` los elementos.</span><span class="sxs-lookup"><span data-stu-id="3ee3f-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="3ee3f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ee3f-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="3ee3f-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3ee3f-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3ee3f-110">Matriz que puede o no representar una permutación.</span><span class="sxs-lookup"><span data-stu-id="3ee3f-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3ee3f-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ee3f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ee3f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ee3f-112">Remarks</span></span>

<span data-ttu-id="3ee3f-113">Una matriz de longitud cero es trivialmente una permutación.</span><span class="sxs-lookup"><span data-stu-id="3ee3f-113">An array of length zero is trivially a permutation.</span></span>