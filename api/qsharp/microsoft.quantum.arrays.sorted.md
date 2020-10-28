---
uid: Microsoft.Quantum.Arrays.Sorted
title: Función ordenada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730028"
---
# <a name="sorted-function"></a><span data-ttu-id="af61a-102">Función ordenada</span><span class="sxs-lookup"><span data-stu-id="af61a-102">Sorted function</span></span>

<span data-ttu-id="af61a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="af61a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="af61a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af61a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af61a-105">Dada una matriz, devuelve los elementos de esa matriz ordenados por una función de comparación determinada.</span><span class="sxs-lookup"><span data-stu-id="af61a-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="af61a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="af61a-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="af61a-107">comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="af61a-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="af61a-108">Función que compara dos elementos que `a` se considera que son menores o iguales que `b` si `comparison(a, b)` es `true` .</span><span class="sxs-lookup"><span data-stu-id="af61a-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="af61a-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="af61a-109">array : 'T[]</span></span>

<span data-ttu-id="af61a-110">Matriz que se va a ordenar.</span><span class="sxs-lookup"><span data-stu-id="af61a-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="af61a-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="af61a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af61a-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="af61a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af61a-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="af61a-113">'T</span></span>

<span data-ttu-id="af61a-114">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="af61a-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="af61a-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af61a-115">Remarks</span></span>

<span data-ttu-id="af61a-116">Se supone que la función `comparison` es transitiva, de modo que si `comparison(a, b)` y `comparison(b, c)` , `comparison(a, c)` se supone.</span><span class="sxs-lookup"><span data-stu-id="af61a-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="af61a-117">Si esta propiedad no contiene, la salida de esta función puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="af61a-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="af61a-118">Como es una función, los resultados son completamente determinstic, incluso cuando dos elementos se consideran iguales en `comparison` ; es decir, cuando `comparison(a, b)` y `comparison(b, a)` son ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="af61a-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="af61a-119">En concreto, se garantiza que la ordenación realizada por esta función es estable, de modo que si dos elementos `a` y `b` se producen en ese orden en `array` y se consideran iguales en `comparison` , `a` también aparecerán antes `b` en la salida.</span><span class="sxs-lookup"><span data-stu-id="af61a-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="af61a-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="af61a-120">For example:</span></span>

```Q#
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