---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220780"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="fa611-102">LookupFunction función)</span><span class="sxs-lookup"><span data-stu-id="fa611-102">LookupFunction function</span></span>

<span data-ttu-id="fa611-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa611-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa611-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa611-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa611-105">Dada una matriz, devuelve una función que devuelve elementos de esa matriz.</span><span class="sxs-lookup"><span data-stu-id="fa611-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="fa611-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fa611-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="fa611-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="fa611-107">array : 'T[]</span></span>

<span data-ttu-id="fa611-108">Matriz que se va a representar como una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fa611-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="fa611-109">Salida: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="fa611-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="fa611-110">Función `f` tal que `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="fa611-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa611-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fa611-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa611-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="fa611-112">'T</span></span>

<span data-ttu-id="fa611-113">Tipo de los elementos de la matriz que se representa como una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fa611-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa611-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa611-114">Remarks</span></span>

<span data-ttu-id="fa611-115">Esta función es principalmente útil para interoperar con funciones y operaciones que toman `Int -> 'T` funciones como argumentos.</span><span class="sxs-lookup"><span data-stu-id="fa611-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="fa611-116">Esto es común, por ejemplo, en la biblioteca de representación del generador, donde las funciones se usan para evitar la necesidad de registrar una matriz completa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="fa611-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>