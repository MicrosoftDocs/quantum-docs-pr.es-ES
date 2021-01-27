---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845650"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="0a23e-102">MappedOverRange función)</span><span class="sxs-lookup"><span data-stu-id="0a23e-102">MappedOverRange function</span></span>

<span data-ttu-id="0a23e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0a23e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0a23e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a23e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a23e-105">Dado un intervalo y una función que toma un entero como entrada, devuelve una nueva matriz que consta de las imágenes de los valores de intervalo de la función.</span><span class="sxs-lookup"><span data-stu-id="0a23e-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0a23e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0a23e-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="0a23e-107">asignador: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="0a23e-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="0a23e-108">Función de `Int` a `'T` que se utiliza para asignar valores de intervalo.</span><span class="sxs-lookup"><span data-stu-id="0a23e-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="0a23e-109">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0a23e-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0a23e-110">Un intervalo de enteros.</span><span class="sxs-lookup"><span data-stu-id="0a23e-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="0a23e-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="0a23e-111">Output : 'T[]</span></span>

<span data-ttu-id="0a23e-112">Matriz `'T[]` de elementos que se asignan mediante la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="0a23e-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a23e-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0a23e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a23e-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="0a23e-114">'T</span></span>

<span data-ttu-id="0a23e-115">El tipo de resultado de la `mapper` función.</span><span class="sxs-lookup"><span data-stu-id="0a23e-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="0a23e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a23e-116">Example</span></span>

<span data-ttu-id="0a23e-117">En este ejemplo se suma 1 a un intervalo de números pares:</span><span class="sxs-lookup"><span data-stu-id="0a23e-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="0a23e-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0a23e-118">Remarks</span></span>

<span data-ttu-id="0a23e-119">La función se define para tipos genéricos, es decir, cada vez que se tiene una función, `mapper: Int -> 'T` se pueden asignar los valores del intervalo y generar una matriz de tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="0a23e-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a23e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a23e-120">See Also</span></span>

- [<span data-ttu-id="0a23e-121">Microsoft. Quantum. arrays. alpped</span><span class="sxs-lookup"><span data-stu-id="0a23e-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)