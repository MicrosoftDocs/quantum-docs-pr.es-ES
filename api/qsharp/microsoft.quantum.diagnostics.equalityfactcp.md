---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727244"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="ea12c-102">EqualityFactCP función)</span><span class="sxs-lookup"><span data-stu-id="ea12c-102">EqualityFactCP function</span></span>

<span data-ttu-id="ea12c-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ea12c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ea12c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea12c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea12c-105">Valida que un número complejo tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="ea12c-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ea12c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea12c-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="ea12c-107">real: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ea12c-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ea12c-108">Valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="ea12c-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="ea12c-109">se esperaba: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ea12c-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ea12c-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="ea12c-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ea12c-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ea12c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ea12c-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="ea12c-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea12c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea12c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

