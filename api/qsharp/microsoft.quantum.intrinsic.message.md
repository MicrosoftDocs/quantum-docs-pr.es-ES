---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726668"
---
# <a name="message-function"></a>Message (función)

Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Configura [](https://nuget.org/packages/)


Registra un mensaje.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="msg--string"></a>msg: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a informar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

El comportamiento específico de esta función depende del simulador, pero en la mayoría de los casos el mensaje especificado se escribirá en la consola.