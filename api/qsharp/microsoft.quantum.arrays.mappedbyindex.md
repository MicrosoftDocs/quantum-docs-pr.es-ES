---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845666"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="402bb-102">MappedByIndex función)</span><span class="sxs-lookup"><span data-stu-id="402bb-102">MappedByIndex function</span></span>

<span data-ttu-id="402bb-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="402bb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="402bb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="402bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="402bb-105">Dada una matriz y una función que se define para los elementos indizados de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.</span><span class="sxs-lookup"><span data-stu-id="402bb-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="402bb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="402bb-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="402bb-107">asignador: ([int](xref:microsoft.quantum.lang-ref.int), ' t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="402bb-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="402bb-108">Función de `(Int, 'T)` a `'U` que se usa para asignar elementos y sus índices.</span><span class="sxs-lookup"><span data-stu-id="402bb-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="402bb-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="402bb-109">array : 'T[]</span></span>

<span data-ttu-id="402bb-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="402bb-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="402bb-111">Salida: ' U []</span><span class="sxs-lookup"><span data-stu-id="402bb-111">Output : 'U[]</span></span>

<span data-ttu-id="402bb-112">Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="402bb-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="402bb-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="402bb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="402bb-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="402bb-114">'T</span></span>

<span data-ttu-id="402bb-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="402bb-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="402bb-116">' U</span><span class="sxs-lookup"><span data-stu-id="402bb-116">'U</span></span>

<span data-ttu-id="402bb-117">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="402bb-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="402bb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="402bb-118">Example</span></span>

<span data-ttu-id="402bb-119">Las dos líneas siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="402bb-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="402bb-120">y</span><span class="sxs-lookup"><span data-stu-id="402bb-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="402bb-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="402bb-121">See Also</span></span>

- [<span data-ttu-id="402bb-122">Microsoft. Quantum. arrays. alpped</span><span class="sxs-lookup"><span data-stu-id="402bb-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)