---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829168"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="eba2a-102">EqualityFactCP función)</span><span class="sxs-lookup"><span data-stu-id="eba2a-102">EqualityFactCP function</span></span>

<span data-ttu-id="eba2a-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="eba2a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="eba2a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eba2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eba2a-105">Valida que un número complejo tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="eba2a-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="eba2a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eba2a-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="eba2a-107">real: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="eba2a-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="eba2a-108">Valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="eba2a-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="eba2a-109">se esperaba: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="eba2a-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="eba2a-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="eba2a-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="eba2a-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="eba2a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="eba2a-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="eba2a-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eba2a-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eba2a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

