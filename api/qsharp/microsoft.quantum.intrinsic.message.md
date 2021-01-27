---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849372"
---
# <a name="message-function"></a><span data-ttu-id="7fbe1-102">Message (función)</span><span class="sxs-lookup"><span data-stu-id="7fbe1-102">Message function</span></span>

<span data-ttu-id="7fbe1-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7fbe1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7fbe1-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7fbe1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7fbe1-105">Registra un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7fbe1-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7fbe1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7fbe1-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="7fbe1-107">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7fbe1-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7fbe1-108">Mensaje que se va a informar.</span><span class="sxs-lookup"><span data-stu-id="7fbe1-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7fbe1-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fbe1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7fbe1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7fbe1-110">Remarks</span></span>

<span data-ttu-id="7fbe1-111">El comportamiento específico de esta función depende del simulador, pero en la mayoría de los casos el mensaje especificado se escribirá en la consola.</span><span class="sxs-lookup"><span data-stu-id="7fbe1-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>