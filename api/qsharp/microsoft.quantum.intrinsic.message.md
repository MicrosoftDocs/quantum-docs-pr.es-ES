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
# <a name="message-function"></a><span data-ttu-id="7bb0b-102">Message (función)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-102">Message function</span></span>

<span data-ttu-id="7bb0b-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7bb0b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bb0b-105">Registra un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7bb0b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7bb0b-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="7bb0b-107">msg: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7bb0b-108">Mensaje que se va a informar.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7bb0b-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7bb0b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7bb0b-110">Remarks</span></span>

<span data-ttu-id="7bb0b-111">El comportamiento específico de esta función depende del simulador, pero en la mayoría de los casos el mensaje especificado se escribirá en la consola.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>