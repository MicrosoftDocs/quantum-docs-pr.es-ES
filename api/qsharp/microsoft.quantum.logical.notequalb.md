---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197388"
---
# <a name="notequalb-function"></a>NotEqualB función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si dos entradas no son iguales.

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>r: [bool](xref:microsoft.quantum.lang-ref.bool)

Primer valor que se va a comparar.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `a` no es igual a `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```