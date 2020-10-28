---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swapd (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729988"
---
# <a name="swapped-function"></a>Swapd (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Aplica un intercambio de dos elementos en una matriz.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="firstindex--int"></a>firstIndex: [int](xref:microsoft.quantum.lang-ref.int)

Índice del primer elemento que se va a intercambiar.


### <a name="secondindex--int"></a>secondIndex: [int](xref:microsoft.quantum.lang-ref.int)

Índice del segundo elemento que se va a intercambiar.


### <a name="arr--t"></a>ARR: ' t []

Matriz con los elementos que se van a intercambiar.



## <a name="output--t"></a>Salida: ' t []

Matriz con el intercambio en contexto aplicado.

## <a name="example"></a>Ejemplo: 

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

