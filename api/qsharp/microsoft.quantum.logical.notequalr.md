---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848498"
---
# <a name="notequalr-function"></a>NotEqualR función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si dos entradas no son iguales.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--__invalidresult__"></a>r: __no <Result> válido__

Primer valor que se va a comparar.


### <a name="b--__invalidresult__"></a>b: __no <Result> válido__

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `a` no es igual a `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```