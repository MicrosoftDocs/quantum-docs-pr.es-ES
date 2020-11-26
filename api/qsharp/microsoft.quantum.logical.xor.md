---
uid: Microsoft.Quantum.Logical.Xor
title: XOR (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197099"
---
# <a name="xor-function"></a>XOR (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve la disyunción exclusiva booleana de dos valores.

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>r: [bool](xref:microsoft.quantum.lang-ref.bool)

Primer valor que se va a considerar.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Segundo valor que se va a considerar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` es si y solo si exactamente uno de `a` y `b` es `true` .