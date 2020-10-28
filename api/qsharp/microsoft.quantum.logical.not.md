---
uid: Microsoft.Quantum.Logical.Not
title: Not (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725997"
---
# <a name="not-function"></a>Not (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Configura [](https://nuget.org/packages/)


Devuelve la negación booleana de un valor.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="value--bool"></a>valor: [bool](xref:microsoft.quantum.lang-ref.bool)

Valor que se va a negar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `value` es `false` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let x = not value;
let x = Not(value);
```