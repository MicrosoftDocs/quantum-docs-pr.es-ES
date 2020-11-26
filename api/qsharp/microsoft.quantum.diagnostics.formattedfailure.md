---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201706"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="37247-102">FormattedFailure función)</span><span class="sxs-lookup"><span data-stu-id="37247-102">FormattedFailure function</span></span>

<span data-ttu-id="37247-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="37247-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="37247-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37247-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37247-105">Función interna que se usa para generar un error con mensajes de error significativos.</span><span class="sxs-lookup"><span data-stu-id="37247-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="37247-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="37247-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="37247-107">real: ' t</span><span class="sxs-lookup"><span data-stu-id="37247-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="37247-108">se esperaba: ' t</span><span class="sxs-lookup"><span data-stu-id="37247-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="37247-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="37247-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="37247-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37247-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37247-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="37247-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37247-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="37247-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="37247-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37247-113">Remarks</span></span>

<span data-ttu-id="37247-114">Esta función está pensada para ser emulada por los tiempos de ejecución de simulación, de modo que se permitan contradicciones con formato de reenvío.</span><span class="sxs-lookup"><span data-stu-id="37247-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>