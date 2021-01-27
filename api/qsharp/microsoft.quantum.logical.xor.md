---
uid: Microsoft.Quantum.Logical.Xor
title: XOR (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848452"
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