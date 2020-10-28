---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729877"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Configura [](https://nuget.org/packages/)


Desplaza la representación bit a bit de un número a la izquierda de un número determinado de bits.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Número cuya representación bit a bit se va a desplazar a la izquierda (más significativa).


### <a name="amount--int"></a>amount: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits por el que `value` se va a desplazar a la izquierda.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor de `value` , desplazado a la izquierda por `amount` bits.

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```