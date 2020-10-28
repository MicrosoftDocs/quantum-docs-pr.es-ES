---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729820"
---
# <a name="rightshiftedl-function"></a>RightShiftedL función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Configura [](https://nuget.org/packages/)


Desplaza la representación bit a bit de un número a la derecha un número determinado de bits.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Entrada

### <a name="value--bigint"></a>valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Número cuya representación bit a bit se va a desplazar a la derecha (menos significativa).


### <a name="amount--int"></a>amount: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits por el que `value` se va a desplazar a la derecha.



## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Valor de `value` , desplazado a la derecha por `amount` bits.

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```