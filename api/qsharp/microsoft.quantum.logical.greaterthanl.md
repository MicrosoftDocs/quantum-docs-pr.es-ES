---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197983"
---
# <a name="greaterthanl-function"></a>GreaterThanL función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si un número es mayor que otro número.

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Primer valor que se va a comparar.


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` es si y solo si `a` es estrictamente mayor que `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```