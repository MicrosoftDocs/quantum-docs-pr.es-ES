---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845430"
---
# <a name="subarray-function"></a><span data-ttu-id="3dac9-102">Subarray (función)</span><span class="sxs-lookup"><span data-stu-id="3dac9-102">Subarray function</span></span>

<span data-ttu-id="3dac9-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3dac9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3dac9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dac9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dac9-105">Toma una matriz y una lista de ubicaciones y genera una nueva matriz formada a partir de los elementos de la matriz original que coinciden con las ubicaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="3dac9-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3dac9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3dac9-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="3dac9-107">índices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3dac9-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3dac9-108">Una lista de enteros que se utiliza para definir la submatriz.</span><span class="sxs-lookup"><span data-stu-id="3dac9-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="3dac9-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="3dac9-109">array : 'T[]</span></span>

<span data-ttu-id="3dac9-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="3dac9-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="3dac9-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="3dac9-111">Output : 'T[]</span></span>

<span data-ttu-id="3dac9-112">Matriz `out` de elementos cuyos índices corresponden a la submatriz, de modo que `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="3dac9-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3dac9-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3dac9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3dac9-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="3dac9-114">'T</span></span>

<span data-ttu-id="3dac9-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="3dac9-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="3dac9-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3dac9-116">Remarks</span></span>

<span data-ttu-id="3dac9-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una lista de ubicaciones que `Int[]` definen la submatriz.</span><span class="sxs-lookup"><span data-stu-id="3dac9-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="3dac9-118">La construcción de la submatriz es un basado en la generación de una nueva copia en profundidad de la matriz determinada en lugar de mantener referencias.</span><span class="sxs-lookup"><span data-stu-id="3dac9-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="3dac9-119">Si es `Length(indices) < Length(array)` , esta función devolverá un subconjunto de `array` .</span><span class="sxs-lookup"><span data-stu-id="3dac9-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="3dac9-120">Por otro lado, si `indices` contiene elementos repetidos, los elementos correspondientes de también `array` se repetirán.</span><span class="sxs-lookup"><span data-stu-id="3dac9-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="3dac9-121">Si `indices` y `array` tienen la misma longitud, esta función proporciona permutaciones de `array` .</span><span class="sxs-lookup"><span data-stu-id="3dac9-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>