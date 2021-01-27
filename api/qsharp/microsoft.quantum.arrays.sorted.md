---
uid: Microsoft.Quantum.Arrays.Sorted
title: Función ordenada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845440"
---
# <a name="sorted-function"></a><span data-ttu-id="1157a-102">Función ordenada</span><span class="sxs-lookup"><span data-stu-id="1157a-102">Sorted function</span></span>

<span data-ttu-id="1157a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1157a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1157a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1157a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1157a-105">Dada una matriz, devuelve los elementos de esa matriz ordenados por una función de comparación determinada.</span><span class="sxs-lookup"><span data-stu-id="1157a-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1157a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1157a-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="1157a-107">comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1157a-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1157a-108">Función que compara dos elementos que `a` se considera que son menores o iguales que `b` si `comparison(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="1157a-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="1157a-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="1157a-109">array : 'T[]</span></span>

<span data-ttu-id="1157a-110">Matriz que se va a ordenar.</span><span class="sxs-lookup"><span data-stu-id="1157a-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="1157a-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="1157a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1157a-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1157a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1157a-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="1157a-113">'T</span></span>

<span data-ttu-id="1157a-114">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="1157a-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="1157a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1157a-115">Example</span></span>

<span data-ttu-id="1157a-116">El siguiente fragmento de código ordena una matriz de enteros para que se produzca en orden ascendente:</span><span class="sxs-lookup"><span data-stu-id="1157a-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="1157a-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1157a-117">Remarks</span></span>

<span data-ttu-id="1157a-118">Se supone que la función `comparison` es transitiva, de modo que si `comparison(a, b)` y `comparison(b, c)` , `comparison(a, c)` se supone.</span><span class="sxs-lookup"><span data-stu-id="1157a-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="1157a-119">Si esta propiedad no contiene, la salida de esta función puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="1157a-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="1157a-120">Como es una función, los resultados son completamente determinstic, incluso cuando dos elementos se consideran iguales en `comparison` ; es decir, cuando `comparison(a, b)` y `comparison(b, a)` son ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="1157a-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="1157a-121">En concreto, se garantiza que la ordenación realizada por esta función es estable, de modo que si dos elementos `a` y `b` se producen en ese orden en `array` y se consideran iguales en `comparison` , `a` también aparecerán antes `b` en la salida.</span><span class="sxs-lookup"><span data-stu-id="1157a-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="1157a-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1157a-122">For example:</span></span>

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```