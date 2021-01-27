---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853342"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="4d6db-102">EqualityFactI función)</span><span class="sxs-lookup"><span data-stu-id="4d6db-102">EqualityFactI function</span></span>

<span data-ttu-id="4d6db-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4d6db-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4d6db-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d6db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d6db-105">Valida que una variable int clásica tiene el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="4d6db-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4d6db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4d6db-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="4d6db-107">real: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d6db-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d6db-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="4d6db-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="4d6db-109">se esperaba: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d6db-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d6db-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="4d6db-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4d6db-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4d6db-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4d6db-112">Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.</span><span class="sxs-lookup"><span data-stu-id="4d6db-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d6db-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d6db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

