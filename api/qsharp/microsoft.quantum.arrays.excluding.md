---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exclusión de función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 6585e619834a96953c9eae2d36a8ebe0a11dbda0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221324"
---
# <a name="excluding-function"></a><span data-ttu-id="9d674-102">Exclusión de función</span><span class="sxs-lookup"><span data-stu-id="9d674-102">Excluding function</span></span>

<span data-ttu-id="9d674-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9d674-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9d674-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d674-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d674-105">Devuelve una matriz que contiene los elementos de otra matriz, excluidos los elementos de una lista determinada de índices.</span><span class="sxs-lookup"><span data-stu-id="9d674-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9d674-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d674-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="9d674-107">quitar: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9d674-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9d674-108">Matriz de índices que indican qué elementos se deben excluir de la salida.</span><span class="sxs-lookup"><span data-stu-id="9d674-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="9d674-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="9d674-109">array : 'T[]</span></span>

<span data-ttu-id="9d674-110">Matriz de la que se toman los valores de la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="9d674-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="9d674-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="9d674-111">Output : 'T[]</span></span>

<span data-ttu-id="9d674-112">Matriz de `output` tipo que `output[0]` es el primer elemento de `array` cuyo índice no aparece en `remove` , tal que `output[1]` es el segundo elemento de este tipo, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9d674-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9d674-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9d674-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d674-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="9d674-114">'T</span></span>

<span data-ttu-id="9d674-115">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9d674-115">The type of the array elements.</span></span>