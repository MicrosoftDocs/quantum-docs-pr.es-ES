---
uid: Microsoft.Quantum.Arrays.Unique
title: Función Unique
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220015"
---
# <a name="unique-function"></a><span data-ttu-id="3d918-102">Función Unique</span><span class="sxs-lookup"><span data-stu-id="3d918-102">Unique function</span></span>

<span data-ttu-id="3d918-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3d918-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3d918-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d918-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d918-105">Devuelve una nueva matriz que no tiene elementos adyacentes iguales.</span><span class="sxs-lookup"><span data-stu-id="3d918-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="3d918-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d918-106">Description</span></span>

<span data-ttu-id="3d918-107">Dada una matriz de elementos y una función para probar la igualdad, esta función devuelve una nueva matriz en la que se conserva el orden relativo de los elementos, pero todos los elementos adyacentes que son iguales se filtran por un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="3d918-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="3d918-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3d918-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="3d918-109">igual: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3d918-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3d918-110">Función que compara dos elementos que `a` se considera que son iguales que `b` si `equal(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="3d918-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="3d918-111">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="3d918-111">array : 'T[]</span></span>

<span data-ttu-id="3d918-112">Matriz que se va a filtrar para los elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="3d918-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="3d918-113">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="3d918-113">Output : 'T[]</span></span>

<span data-ttu-id="3d918-114">Matriz sin elementos adyacentes iguales.</span><span class="sxs-lookup"><span data-stu-id="3d918-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3d918-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3d918-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3d918-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="3d918-116">'T</span></span>

<span data-ttu-id="3d918-117">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="3d918-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d918-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d918-118">Remarks</span></span>

<span data-ttu-id="3d918-119">Si hay varios elementos que son iguales pero no próximos entre sí, habrá varias repeticiones en la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="3d918-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="3d918-120">Use esta función junto con `Sorted` para obtener una matriz con elementos únicos generales.</span><span class="sxs-lookup"><span data-stu-id="3d918-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>