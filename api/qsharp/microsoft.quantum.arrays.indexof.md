---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221018"
---
# <a name="indexof-function"></a><span data-ttu-id="6c51d-102">IndexOf (función)</span><span class="sxs-lookup"><span data-stu-id="6c51d-102">IndexOf function</span></span>

<span data-ttu-id="6c51d-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6c51d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6c51d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c51d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c51d-105">Devuelve el primer índice del primer elemento de una matriz que satisface un predicado determinado.</span><span class="sxs-lookup"><span data-stu-id="6c51d-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="6c51d-106">Si no existe ningún elemento de este tipo, devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="6c51d-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="6c51d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c51d-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="6c51d-108">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6c51d-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6c51d-109">Función de predicado que actúa sobre los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6c51d-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="6c51d-110">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="6c51d-110">arr : 'T[]</span></span>

<span data-ttu-id="6c51d-111">Matriz en la que se va a buscar mediante el predicado especificado.</span><span class="sxs-lookup"><span data-stu-id="6c51d-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="6c51d-112">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c51d-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c51d-113">El índice más pequeño, `idx` tal que `predicate(arr[idx])` sea true, o-1 si no existe ese elemento.</span><span class="sxs-lookup"><span data-stu-id="6c51d-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6c51d-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6c51d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c51d-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="6c51d-115">'T</span></span>

