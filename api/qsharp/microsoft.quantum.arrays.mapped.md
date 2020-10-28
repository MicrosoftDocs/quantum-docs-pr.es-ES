---
uid: Microsoft.Quantum.Arrays.Mapped
title: Función asignada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730156"
---
# <a name="mapped-function"></a><span data-ttu-id="9ece0-102">Función asignada</span><span class="sxs-lookup"><span data-stu-id="9ece0-102">Mapped function</span></span>

<span data-ttu-id="9ece0-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9ece0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9ece0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ece0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ece0-105">Dada una matriz y una función que se define para los elementos de la matriz, devuelve una nueva matriz que consta de las imágenes de la matriz original en la función.</span><span class="sxs-lookup"><span data-stu-id="9ece0-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="9ece0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9ece0-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="9ece0-107">Mapper: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="9ece0-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="9ece0-108">Función de `'T` a `'U` que se usa para asignar elementos.</span><span class="sxs-lookup"><span data-stu-id="9ece0-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="9ece0-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="9ece0-109">array : 'T[]</span></span>

<span data-ttu-id="9ece0-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="9ece0-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="9ece0-111">Salida: ' U []</span><span class="sxs-lookup"><span data-stu-id="9ece0-111">Output : 'U[]</span></span>

<span data-ttu-id="9ece0-112">Matriz `'U[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="9ece0-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9ece0-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9ece0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ece0-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="9ece0-114">'T</span></span>

<span data-ttu-id="9ece0-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="9ece0-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="9ece0-116">' U</span><span class="sxs-lookup"><span data-stu-id="9ece0-116">'U</span></span>

<span data-ttu-id="9ece0-117">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="9ece0-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ece0-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ece0-118">Remarks</span></span>

<span data-ttu-id="9ece0-119">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y una función, `mapper: 'T -> 'U` podemos asignar los elementos de la matriz y generar una nueva matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="9ece0-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>