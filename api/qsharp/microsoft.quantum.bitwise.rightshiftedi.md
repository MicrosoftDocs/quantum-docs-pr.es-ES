---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845251"
---
# <a name="rightshiftedi-function"></a>RightShiftedI función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```