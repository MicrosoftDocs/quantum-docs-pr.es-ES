---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201774"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="af6de-102">EqualityFactR función)</span><span class="sxs-lookup"><span data-stu-id="af6de-102">EqualityFactR function</span></span>

<span data-ttu-id="af6de-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="af6de-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="af6de-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af6de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af6de-105">Valida que una variable de resultado clásico tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="af6de-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="af6de-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="af6de-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="af6de-107">real: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="af6de-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="af6de-108">Variable que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="af6de-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="af6de-109">esperado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="af6de-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="af6de-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="af6de-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="af6de-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="af6de-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="af6de-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="af6de-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af6de-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af6de-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

