---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828748"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="d3a57-102">EqualityWithinToleranceFact función)</span><span class="sxs-lookup"><span data-stu-id="d3a57-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="d3a57-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d3a57-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d3a57-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3a57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3a57-105">Representa la afirmación de que un valor de punto flotante clásico tiene el valor esperado hasta una tolerancia absoluta determinada.</span><span class="sxs-lookup"><span data-stu-id="d3a57-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="d3a57-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3a57-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="d3a57-107">real: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3a57-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3a57-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="d3a57-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="d3a57-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3a57-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3a57-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="d3a57-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="d3a57-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3a57-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3a57-112">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="d3a57-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3a57-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3a57-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

