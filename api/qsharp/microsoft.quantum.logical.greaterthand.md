---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726057"
---
# <a name="greaterthand-function"></a>GreaterThanD función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Configura [](https://nuget.org/packages/)


Devuelve true si y solo si un número es mayor que otro número.

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--double"></a>r: [Double](xref:microsoft.quantum.lang-ref.double)

Primer valor que se va a comparar.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` es si y solo si `a` es estrictamente mayor que `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```