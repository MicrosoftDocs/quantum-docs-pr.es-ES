---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197591"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="dbdfb-102">LexographicComparison función)</span><span class="sxs-lookup"><span data-stu-id="dbdfb-102">LexographicComparison function</span></span>

<span data-ttu-id="dbdfb-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dbdfb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dbdfb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbdfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbdfb-105">Dada una función de comparación, devuelve una nueva función que lexographically compara dos matrices.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="dbdfb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dbdfb-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="dbdfb-107">elementComparison: (' t, ' t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbdfb-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbdfb-108">Función que compara dos elementos `x` y `y` y devuelve si `x` es menor o igual que `y` .</span><span class="sxs-lookup"><span data-stu-id="dbdfb-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="dbdfb-109">Salida: (' t [], ' t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbdfb-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbdfb-110">Función que compara dos matrices `xs` y `ys` y devuelve si `xs` se produce antes o igual que en el `ys` orden de lexographical.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dbdfb-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dbdfb-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbdfb-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="dbdfb-112">'T</span></span>

<span data-ttu-id="dbdfb-113">Tipo de los elementos de las matrices que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbdfb-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbdfb-114">Remarks</span></span>

<span data-ttu-id="dbdfb-115">La comparación de lexographic entre dos matrices `xs` y `ys` se define mediante el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="dbdfb-116">Indicamos que dos elementos `x` y `y` son equivalentes si `elementComparison(x, y)` y `elementComparison(y, x)` son true.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="dbdfb-117">Ambas matrices se comparan elemento a elemento hasta el primer par de elementos que no son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="dbdfb-118">La matriz que contiene el elemento que se produce primero según `elementComparison` se dice que se produce primero en el orden de lexographical.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="dbdfb-119">Si no se encuentra ningún elemento no equivalente y una matriz es más larga que la otra, se dice que la matriz más corta se produce primero.</span><span class="sxs-lookup"><span data-stu-id="dbdfb-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbdfb-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbdfb-120">See Also</span></span>

- [<span data-ttu-id="dbdfb-121">Microsoft. Quantum. matrices. Sorted</span><span class="sxs-lookup"><span data-stu-id="dbdfb-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)