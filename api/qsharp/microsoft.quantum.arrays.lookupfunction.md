---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730149"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="10533-102">LookupFunction función)</span><span class="sxs-lookup"><span data-stu-id="10533-102">LookupFunction function</span></span>

<span data-ttu-id="10533-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10533-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10533-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10533-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10533-105">Dada una matriz, devuelve una función que devuelve elementos de esa matriz.</span><span class="sxs-lookup"><span data-stu-id="10533-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="10533-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="10533-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="10533-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="10533-107">array : 'T[]</span></span>

<span data-ttu-id="10533-108">Matriz que se va a representar como una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="10533-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="10533-109">Salida: [int](xref:microsoft.quantum.lang-ref.int) -> ' t</span><span class="sxs-lookup"><span data-stu-id="10533-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="10533-110">Función `f` tal que `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="10533-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="10533-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="10533-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10533-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="10533-112">'T</span></span>

<span data-ttu-id="10533-113">Tipo de los elementos de la matriz que se representa como una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="10533-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="10533-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10533-114">Remarks</span></span>

<span data-ttu-id="10533-115">Esta función es principalmente útil para interoperar con funciones y operaciones que toman `Int -> 'T` funciones como argumentos.</span><span class="sxs-lookup"><span data-stu-id="10533-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="10533-116">Esto es común, por ejemplo, en la biblioteca de representación del generador, donde las funciones se usan para evitar la necesidad de registrar una matriz completa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="10533-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>