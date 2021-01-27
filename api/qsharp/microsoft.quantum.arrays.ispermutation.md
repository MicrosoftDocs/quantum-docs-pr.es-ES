---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848090"
---
# <a name="ispermutation-function"></a><span data-ttu-id="92ae3-102">IsPermutation función)</span><span class="sxs-lookup"><span data-stu-id="92ae3-102">IsPermutation function</span></span>

<span data-ttu-id="92ae3-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="92ae3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="92ae3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92ae3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92ae3-105">Devuelve true si y solo si una matriz determinada representa una permutación.</span><span class="sxs-lookup"><span data-stu-id="92ae3-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="92ae3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="92ae3-106">Description</span></span>

<span data-ttu-id="92ae3-107">Dada una matriz `array` de longitud `n` , devuelve true solo si cada entero de `0` hasta `n - 1` aparece exactamente una vez en `array` , por `array` lo que se puede interpretar como una permutación en `n` los elementos.</span><span class="sxs-lookup"><span data-stu-id="92ae3-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="92ae3-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="92ae3-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="92ae3-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="92ae3-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="92ae3-110">Matriz que puede o no representar una permutación.</span><span class="sxs-lookup"><span data-stu-id="92ae3-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="92ae3-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="92ae3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="92ae3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92ae3-112">Example</span></span>

<span data-ttu-id="92ae3-113">El siguiente código de r # imprime el mensaje "todos los diagnósticos se completaron correctamente":</span><span class="sxs-lookup"><span data-stu-id="92ae3-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="92ae3-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="92ae3-114">Remarks</span></span>

<span data-ttu-id="92ae3-115">Una matriz de longitud cero es trivialmente una permutación.</span><span class="sxs-lookup"><span data-stu-id="92ae3-115">An array of length zero is trivially a permutation.</span></span>