---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846289"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="69c8b-102">_SwapOrderToPermuteArray función)</span><span class="sxs-lookup"><span data-stu-id="69c8b-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="69c8b-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="69c8b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="69c8b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c8b-105">Devuelve los elementos de orden de una matriz que se deben intercambiar para producir una matriz ordenada.</span><span class="sxs-lookup"><span data-stu-id="69c8b-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="69c8b-106">Supone que los intercambios tienen lugar.</span><span class="sxs-lookup"><span data-stu-id="69c8b-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="69c8b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="69c8b-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="69c8b-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="69c8b-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="69c8b-109">Matriz con la permutación de los índices de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="69c8b-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="69c8b-110">Debería haber $n $ Elements, cada uno de los cuales es un entero único de $0 $ a $n-$1.</span><span class="sxs-lookup"><span data-stu-id="69c8b-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="69c8b-111">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="69c8b-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="69c8b-112">La tupla representa los dos índices que se van a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="69c8b-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="69c8b-113">Los swaps comienzan en el índice más bajo.</span><span class="sxs-lookup"><span data-stu-id="69c8b-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="69c8b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69c8b-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="69c8b-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69c8b-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="69c8b-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="69c8b-116">Psuedocode</span></span>

<span data-ttu-id="69c8b-117">for (index in 0.. length (newOrder)-1) {While newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="69c8b-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>