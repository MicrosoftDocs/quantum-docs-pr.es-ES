---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198013"
---
# <a name="equalr-function"></a>Equalr (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si dos entradas son iguales.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--__invalidresult__"></a>r: __no <Result> válido__

Primer valor que se va a comparar.


### <a name="b--__invalidresult__"></a>b: __no <Result> válido__

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `a` es igual a `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```