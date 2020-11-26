---
uid: Microsoft.Quantum.Arrays.Count
title: Count, función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221562"
---
# <a name="count-function"></a><span data-ttu-id="351ca-102">Count, función</span><span class="sxs-lookup"><span data-stu-id="351ca-102">Count function</span></span>

<span data-ttu-id="351ca-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="351ca-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="351ca-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="351ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="351ca-105">Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve el número de elementos de una matriz que consta de los elementos que cumplen el predicado.</span><span class="sxs-lookup"><span data-stu-id="351ca-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="351ca-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="351ca-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="351ca-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="351ca-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="351ca-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="351ca-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="351ca-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="351ca-109">array : 'T[]</span></span>

<span data-ttu-id="351ca-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="351ca-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="351ca-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="351ca-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="351ca-112">Número de elementos de `array` que satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="351ca-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="351ca-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="351ca-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="351ca-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="351ca-114">'T</span></span>

<span data-ttu-id="351ca-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="351ca-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="351ca-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="351ca-116">Remarks</span></span>

<span data-ttu-id="351ca-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="351ca-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>