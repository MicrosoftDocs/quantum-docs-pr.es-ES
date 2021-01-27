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

## <a name="example"></a>Ejemplo

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Observaciones

## <a name="psuedocode"></a>Psuedocode

for (index in 0.. length (newOrder)-1) {While newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}