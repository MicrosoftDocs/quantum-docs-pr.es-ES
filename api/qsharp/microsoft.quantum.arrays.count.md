---
uid: Microsoft.Quantum.Arrays.Count
title: Count, función
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730372"
---
# <a name="count-function"></a><span data-ttu-id="94205-102">Count, función</span><span class="sxs-lookup"><span data-stu-id="94205-102">Count function</span></span>

<span data-ttu-id="94205-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="94205-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="94205-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94205-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94205-105">Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve el número de elementos de una matriz que consta de los elementos que cumplen el predicado.</span><span class="sxs-lookup"><span data-stu-id="94205-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="94205-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="94205-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="94205-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94205-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94205-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="94205-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="94205-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="94205-109">array : 'T[]</span></span>

<span data-ttu-id="94205-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="94205-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="94205-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94205-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94205-112">Número de elementos de `array` que satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="94205-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94205-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="94205-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94205-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="94205-114">'T</span></span>

<span data-ttu-id="94205-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="94205-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="94205-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94205-116">Remarks</span></span>

<span data-ttu-id="94205-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="94205-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>