---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197779"
---
# <a name="lessthani-function"></a>LessThanI función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si un número es menor que otro número.

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Primer valor que se va a comparar.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` es si y solo si `a` es estrictamente menor que `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```