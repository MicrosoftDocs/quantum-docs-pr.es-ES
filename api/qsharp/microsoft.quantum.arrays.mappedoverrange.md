---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730132"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="1c919-102">MappedOverRange función)</span><span class="sxs-lookup"><span data-stu-id="1c919-102">MappedOverRange function</span></span>

<span data-ttu-id="1c919-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1c919-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1c919-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c919-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c919-105">Dado un intervalo y una función que toma un entero como entrada, devuelve una nueva matriz que consta de las imágenes de los valores de intervalo de la función.</span><span class="sxs-lookup"><span data-stu-id="1c919-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1c919-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c919-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="1c919-107">asignador: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="1c919-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="1c919-108">Función de `Int` a `'T` que se utiliza para asignar valores de intervalo.</span><span class="sxs-lookup"><span data-stu-id="1c919-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="1c919-109">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1c919-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="1c919-110">Un intervalo de enteros.</span><span class="sxs-lookup"><span data-stu-id="1c919-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="1c919-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="1c919-111">Output : 'T[]</span></span>

<span data-ttu-id="1c919-112">Matriz `'T[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="1c919-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1c919-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1c919-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c919-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="1c919-114">'T</span></span>

<span data-ttu-id="1c919-115">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="1c919-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c919-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c919-116">Remarks</span></span>

<span data-ttu-id="1c919-117">La función se define para tipos genéricos, es decir, cada vez que se tiene una función, `mapper: Int -> 'T` se pueden asignar los valores del intervalo y generar una matriz de tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="1c919-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c919-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c919-118">See Also</span></span>

- [<span data-ttu-id="1c919-119">Microsoft. Quantum. arrays. alpped</span><span class="sxs-lookup"><span data-stu-id="1c919-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)