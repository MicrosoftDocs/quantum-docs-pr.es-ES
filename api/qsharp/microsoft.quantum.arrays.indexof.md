---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730220"
---
# <a name="indexof-function"></a><span data-ttu-id="170a7-102">IndexOf (función)</span><span class="sxs-lookup"><span data-stu-id="170a7-102">IndexOf function</span></span>

<span data-ttu-id="170a7-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="170a7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="170a7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="170a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="170a7-105">Devuelve el primer índice del primer elemento de una matriz que satisface un predicado determinado.</span><span class="sxs-lookup"><span data-stu-id="170a7-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="170a7-106">Si no existe ningún elemento de este tipo, devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="170a7-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="170a7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="170a7-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="170a7-108">predicado: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="170a7-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="170a7-109">Función de predicado que actúa sobre los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="170a7-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="170a7-110">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="170a7-110">arr : 'T[]</span></span>

<span data-ttu-id="170a7-111">Matriz en la que se va a buscar mediante el predicado especificado.</span><span class="sxs-lookup"><span data-stu-id="170a7-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="170a7-112">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="170a7-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="170a7-113">El índice más pequeño, `idx` tal que `predicate(arr[idx])` sea true, o-1 si no existe ese elemento.</span><span class="sxs-lookup"><span data-stu-id="170a7-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="170a7-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="170a7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="170a7-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="170a7-115">'T</span></span>

