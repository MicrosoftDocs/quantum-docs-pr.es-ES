---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730292"
---
# <a name="exclude-function"></a><span data-ttu-id="ef928-102">Exclude (función)</span><span class="sxs-lookup"><span data-stu-id="ef928-102">Exclude function</span></span>

<span data-ttu-id="ef928-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ef928-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ef928-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef928-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef928-105">Devuelve una matriz que contiene los elementos de otra matriz, excluidos los elementos de una lista determinada de índices.</span><span class="sxs-lookup"><span data-stu-id="ef928-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ef928-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef928-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="ef928-107">quitar: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ef928-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ef928-108">Matriz de índices que indican qué elementos se deben excluir de la salida.</span><span class="sxs-lookup"><span data-stu-id="ef928-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="ef928-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="ef928-109">array : 'T[]</span></span>

<span data-ttu-id="ef928-110">Matriz de la que se toman los valores de la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="ef928-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="ef928-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="ef928-111">Output : 'T[]</span></span>

<span data-ttu-id="ef928-112">Matriz de `output` tipo que `output[0]` es el primer elemento de `array` cuyo índice no aparece en `remove` , tal que `output[1]` es el segundo elemento de este tipo, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ef928-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ef928-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ef928-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ef928-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="ef928-114">'T</span></span>

<span data-ttu-id="ef928-115">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ef928-115">The type of the array elements.</span></span>