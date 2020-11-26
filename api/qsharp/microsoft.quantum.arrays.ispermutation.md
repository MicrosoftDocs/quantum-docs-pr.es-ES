---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220933"
---
# <a name="ispermutation-function"></a><span data-ttu-id="2ea0a-102">IsPermutation función)</span><span class="sxs-lookup"><span data-stu-id="2ea0a-102">IsPermutation function</span></span>

<span data-ttu-id="2ea0a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2ea0a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2ea0a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ea0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ea0a-105">Devuelve true si y solo si una matriz determinada representa una permutación.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="2ea0a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ea0a-106">Description</span></span>

<span data-ttu-id="2ea0a-107">Dada una matriz `array` de longitud `n` , devuelve true solo si cada entero de `0` hasta `n - 1` aparece exactamente una vez en `array` , por `array` lo que se puede interpretar como una permutación en `n` los elementos.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="2ea0a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ea0a-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="2ea0a-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2ea0a-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2ea0a-110">Matriz que puede o no representar una permutación.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2ea0a-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2ea0a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ea0a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2ea0a-112">Remarks</span></span>

<span data-ttu-id="2ea0a-113">Una matriz de longitud cero es trivialmente una permutación.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-113">An array of length zero is trivially a permutation.</span></span>