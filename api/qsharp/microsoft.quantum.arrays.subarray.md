---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729997"
---
# <a name="subarray-function"></a><span data-ttu-id="1b306-102">Subarray (función)</span><span class="sxs-lookup"><span data-stu-id="1b306-102">Subarray function</span></span>

<span data-ttu-id="1b306-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1b306-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1b306-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b306-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b306-105">Toma una matriz y una lista de ubicaciones y genera una nueva matriz formada a partir de los elementos de la matriz original que coinciden con las ubicaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="1b306-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1b306-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b306-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="1b306-107">índices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1b306-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1b306-108">Una lista de enteros que se utiliza para definir la submatriz.</span><span class="sxs-lookup"><span data-stu-id="1b306-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="1b306-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="1b306-109">array : 'T[]</span></span>

<span data-ttu-id="1b306-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="1b306-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="1b306-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="1b306-111">Output : 'T[]</span></span>

<span data-ttu-id="1b306-112">Matriz `out` de elementos cuyos índices corresponden a la submatriz, de modo que `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="1b306-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b306-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1b306-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b306-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="1b306-114">'T</span></span>

<span data-ttu-id="1b306-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="1b306-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b306-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b306-116">Remarks</span></span>

<span data-ttu-id="1b306-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una lista de ubicaciones que `Int[]` definen la submatriz.</span><span class="sxs-lookup"><span data-stu-id="1b306-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="1b306-118">La construcción de la submatriz es un basado en la generación de una nueva copia en profundidad de la matriz determinada en lugar de mantener referencias.</span><span class="sxs-lookup"><span data-stu-id="1b306-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="1b306-119">Si es `Length(indices) < Length(array)` , esta función devolverá un subconjunto de `array` .</span><span class="sxs-lookup"><span data-stu-id="1b306-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="1b306-120">Por otro lado, si `indices` contiene elementos repetidos, los elementos correspondientes de también `array` se repetirán.</span><span class="sxs-lookup"><span data-stu-id="1b306-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="1b306-121">Si `indices` y `array` tienen la misma longitud, esta función proporciona permutaciones de `array` .</span><span class="sxs-lookup"><span data-stu-id="1b306-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>