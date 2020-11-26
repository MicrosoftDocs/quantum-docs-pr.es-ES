---
uid: Microsoft.Quantum.Arrays.Filtered
title: Función filtrada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221273"
---
# <a name="filtered-function"></a><span data-ttu-id="3b00e-102">Función filtrada</span><span class="sxs-lookup"><span data-stu-id="3b00e-102">Filtered function</span></span>

<span data-ttu-id="3b00e-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3b00e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3b00e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b00e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b00e-105">Dada una matriz y un predicado definidos para los elementos de la matriz, devuelve una matriz que consta de los elementos que cumplen el predicado.</span><span class="sxs-lookup"><span data-stu-id="3b00e-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3b00e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3b00e-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="3b00e-107">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3b00e-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3b00e-108">Función de `'T` a un valor booleano que se usa para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="3b00e-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="3b00e-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="3b00e-109">array : 'T[]</span></span>

<span data-ttu-id="3b00e-110">Matriz de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="3b00e-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="3b00e-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="3b00e-111">Output : 'T[]</span></span>

<span data-ttu-id="3b00e-112">Matriz `'T[]` de elementos que satisfacen el predicado.</span><span class="sxs-lookup"><span data-stu-id="3b00e-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3b00e-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3b00e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b00e-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="3b00e-114">'T</span></span>

<span data-ttu-id="3b00e-115">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="3b00e-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b00e-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3b00e-116">Remarks</span></span>

<span data-ttu-id="3b00e-117">La función se define para tipos genéricos, es decir, cada vez que tenemos una matriz `'T[]` y un predicado, `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="3b00e-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>