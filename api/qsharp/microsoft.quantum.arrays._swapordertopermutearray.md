---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221715"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="8958c-102">_SwapOrderToPermuteArray función)</span><span class="sxs-lookup"><span data-stu-id="8958c-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="8958c-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8958c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8958c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8958c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8958c-105">Devuelve los elementos de orden de una matriz que se deben intercambiar para producir una matriz ordenada.</span><span class="sxs-lookup"><span data-stu-id="8958c-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="8958c-106">Supone que los intercambios tienen lugar.</span><span class="sxs-lookup"><span data-stu-id="8958c-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="8958c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8958c-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="8958c-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8958c-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8958c-109">Matriz con la permutación de los índices de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="8958c-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="8958c-110">Debería haber $n $ Elements, cada uno de los cuales es un entero único de $0 $ a $n-$1.</span><span class="sxs-lookup"><span data-stu-id="8958c-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="8958c-111">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8958c-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="8958c-112">La tupla representa los dos índices que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="8958c-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="8958c-113">Los swaps comienzan en el índice más bajo.</span><span class="sxs-lookup"><span data-stu-id="8958c-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="8958c-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8958c-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="8958c-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="8958c-115">Psuedocode</span></span>

<span data-ttu-id="8958c-116">for (index in 0.. length (newOrder)-1) {While newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="8958c-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>