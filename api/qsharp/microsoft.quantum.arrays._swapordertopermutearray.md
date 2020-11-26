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
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve los elementos de orden de una matriz que se deben intercambiar para producir una matriz ordenada.
Supone que los intercambios tienen lugar.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Entrada

### <a name="neworder--int"></a>newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz con la permutación de los índices de la nueva matriz. Debería haber $n $ Elements, cada uno de los cuales es un entero único de $0 $ a $n-$1.



## <a name="output--intint"></a>Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

La tupla representa los dos índices que se van a intercambiar. Los swaps comienzan en el índice más bajo.

## <a name="remarks"></a>Observaciones

## <a name="psuedocode"></a>Psuedocode

for (index in 0.. length (newOrder)-1) {While newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}