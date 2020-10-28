---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730140"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="338b4-102">MappedByIndex función)</span><span class="sxs-lookup"><span data-stu-id="338b4-102">MappedByIndex function</span></span>

<span data-ttu-id="338b4-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="338b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="338b4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="338b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="338b4-105">Dada una matriz y una función que se define para los elementos indizados de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.</span><span class="sxs-lookup"><span data-stu-id="338b4-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="338b4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="338b4-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="338b4-107">asignador: ([int](xref:microsoft.quantum.lang-ref.int), ' t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="338b4-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="338b4-108">Función de `(Int, 'T)` a `'U` que se usa para asignar elementos y sus índices.</span><span class="sxs-lookup"><span data-stu-id="338b4-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="338b4-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="338b4-109">array : 'T[]</span></span>

<span data-ttu-id="338b4-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="338b4-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="338b4-111">Salida: ' U []</span><span class="sxs-lookup"><span data-stu-id="338b4-111">Output : 'U[]</span></span>

<span data-ttu-id="338b4-112">Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="338b4-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="338b4-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="338b4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="338b4-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="338b4-114">'T</span></span>

<span data-ttu-id="338b4-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="338b4-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="338b4-116">' U</span><span class="sxs-lookup"><span data-stu-id="338b4-116">'U</span></span>

<span data-ttu-id="338b4-117">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="338b4-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="338b4-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="338b4-118">See Also</span></span>

- [<span data-ttu-id="338b4-119">Microsoft. Quantum. arrays. alpped</span><span class="sxs-lookup"><span data-stu-id="338b4-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)