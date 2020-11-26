---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199019"
---
# <a name="message-function"></a><span data-ttu-id="f3397-102">Message (función)</span><span class="sxs-lookup"><span data-stu-id="f3397-102">Message function</span></span>

<span data-ttu-id="f3397-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f3397-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f3397-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f3397-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f3397-105">Registra un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3397-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f3397-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f3397-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="f3397-107">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f3397-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f3397-108">Mensaje que se va a informar.</span><span class="sxs-lookup"><span data-stu-id="f3397-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3397-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3397-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f3397-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3397-110">Remarks</span></span>

<span data-ttu-id="f3397-111">El comportamiento específico de esta función depende del simulador, pero en la mayoría de los casos el mensaje especificado se escribirá en la consola.</span><span class="sxs-lookup"><span data-stu-id="f3397-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>