---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201808"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="419b4-102">EqualityFactL función)</span><span class="sxs-lookup"><span data-stu-id="419b4-102">EqualityFactL function</span></span>

<span data-ttu-id="419b4-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="419b4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="419b4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="419b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="419b4-105">Valida que una variable BigInt clásica tenga el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="419b4-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="419b4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="419b4-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="419b4-107">real: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="419b4-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="419b4-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="419b4-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="419b4-109">se esperaba: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="419b4-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="419b4-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="419b4-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="419b4-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="419b4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="419b4-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="419b4-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="419b4-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="419b4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

