---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727232"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="2a6aa-102">EqualityFactR función)</span><span class="sxs-lookup"><span data-stu-id="2a6aa-102">EqualityFactR function</span></span>

<span data-ttu-id="2a6aa-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2a6aa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2a6aa-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a6aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a6aa-105">Valida que una variable de resultado clásico tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="2a6aa-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2a6aa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2a6aa-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="2a6aa-107">real: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="2a6aa-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="2a6aa-108">Variable que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="2a6aa-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="2a6aa-109">esperado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="2a6aa-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="2a6aa-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="2a6aa-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2a6aa-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2a6aa-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2a6aa-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="2a6aa-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a6aa-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a6aa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

