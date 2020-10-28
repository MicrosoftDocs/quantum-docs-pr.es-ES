---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUALI (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726080"
---
# <a name="equali-function"></a>EQUALI (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Configura [](https://nuget.org/packages/)


Devuelve true si y solo si dos entradas son iguales.

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Primer valor que se va a comparar.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `a` es igual a `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```