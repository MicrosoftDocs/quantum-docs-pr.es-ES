---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853360"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="614c8-102">EqualityFactC función)</span><span class="sxs-lookup"><span data-stu-id="614c8-102">EqualityFactC function</span></span>

<span data-ttu-id="614c8-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="614c8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="614c8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="614c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="614c8-105">Valida que un número complejo tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="614c8-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="614c8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="614c8-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="614c8-107">real: [complejo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="614c8-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="614c8-108">Valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="614c8-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="614c8-109">esperado: [complejo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="614c8-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="614c8-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="614c8-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="614c8-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="614c8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="614c8-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="614c8-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="614c8-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="614c8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

