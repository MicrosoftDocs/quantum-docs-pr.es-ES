---
uid: Microsoft.Quantum.Logical.Not
title: Not (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849087"
---
# <a name="not-function"></a>Not (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = not value;
let x = Not(value);
```