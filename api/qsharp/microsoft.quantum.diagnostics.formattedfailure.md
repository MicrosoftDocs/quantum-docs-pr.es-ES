---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727203"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="46532-102">FormattedFailure función)</span><span class="sxs-lookup"><span data-stu-id="46532-102">FormattedFailure function</span></span>

<span data-ttu-id="46532-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="46532-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="46532-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46532-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46532-105">Función interna que se usa para generar un error con mensajes de error significativos.</span><span class="sxs-lookup"><span data-stu-id="46532-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="46532-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="46532-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="46532-107">real: ' t</span><span class="sxs-lookup"><span data-stu-id="46532-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="46532-108">se esperaba: ' t</span><span class="sxs-lookup"><span data-stu-id="46532-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="46532-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="46532-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="46532-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46532-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="46532-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="46532-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46532-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="46532-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="46532-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46532-113">Remarks</span></span>

<span data-ttu-id="46532-114">Esta función está pensada para ser emulada por los tiempos de ejecución de simulación, de modo que se permitan contradicciones con formato de reenvío.</span><span class="sxs-lookup"><span data-stu-id="46532-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>