---
uid: Microsoft.Quantum.Arrays.Mapped
title: Función asignada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220746"
---
# <a name="mapped-function"></a><span data-ttu-id="1b3e6-102">Función asignada</span><span class="sxs-lookup"><span data-stu-id="1b3e6-102">Mapped function</span></span>

<span data-ttu-id="1b3e6-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1b3e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1b3e6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b3e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b3e6-105">Dada una matriz y una función que se define para los elementos de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.</span><span class="sxs-lookup"><span data-stu-id="1b3e6-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="1b3e6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b3e6-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="1b3e6-107">Mapper: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="1b3e6-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="1b3e6-108">Función de `'T` a `'U` que se usa para asignar elementos.</span><span class="sxs-lookup"><span data-stu-id="1b3e6-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="1b3e6-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="1b3e6-109">array : 'T[]</span></span>

<span data-ttu-id="1b3e6-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="1b3e6-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="1b3e6-111">Salida: ' U []</span><span class="sxs-lookup"><span data-stu-id="1b3e6-111">Output : 'U[]</span></span>

<span data-ttu-id="1b3e6-112">Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="1b3e6-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b3e6-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1b3e6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b3e6-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="1b3e6-114">'T</span></span>

<span data-ttu-id="1b3e6-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="1b3e6-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="1b3e6-116">' U</span><span class="sxs-lookup"><span data-stu-id="1b3e6-116">'U</span></span>

<span data-ttu-id="1b3e6-117">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="1b3e6-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b3e6-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b3e6-118">Remarks</span></span>

<span data-ttu-id="1b3e6-119">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `mapper: 'T -> 'U` podemos asignar los elementos de la matriz y generar una nueva matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="1b3e6-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>