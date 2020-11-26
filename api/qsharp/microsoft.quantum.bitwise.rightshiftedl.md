---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219522"
---
# <a name="rightshiftedl-function"></a>RightShiftedL función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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