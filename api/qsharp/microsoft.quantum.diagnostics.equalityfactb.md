---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727245"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="a96a9-102">EqualityFactB función)</span><span class="sxs-lookup"><span data-stu-id="a96a9-102">EqualityFactB function</span></span>

<span data-ttu-id="a96a9-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a96a9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a96a9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a96a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a96a9-105">Valida que una variable de bool clásico tenga el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="a96a9-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a96a9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a96a9-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="a96a9-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a96a9-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a96a9-108">Variable que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="a96a9-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="a96a9-109">se esperaba: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a96a9-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a96a9-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="a96a9-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="a96a9-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a96a9-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a96a9-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="a96a9-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a96a9-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a96a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

