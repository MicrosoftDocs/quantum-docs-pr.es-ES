---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729821"
---
# <a name="rightshiftedi-function"></a>RightShiftedI función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Configura [](https://nuget.org/packages/)


Desplaza la representación bit a bit de un número a la derecha un número determinado de bits.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Número cuya representación bit a bit se va a desplazar a la derecha (menos significativa).


### <a name="amount--int"></a>amount: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits por el que `value` se va a desplazar a la derecha.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor de `value` , desplazado a la derecha por `amount` bits.

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```