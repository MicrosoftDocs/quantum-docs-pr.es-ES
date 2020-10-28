---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727233"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="e9f47-102">EqualityWithinToleranceFact función)</span><span class="sxs-lookup"><span data-stu-id="e9f47-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="e9f47-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e9f47-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e9f47-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9f47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9f47-105">Representa la afirmación de que un valor de punto flotante clásico tiene el valor esperado hasta una tolerancia absoluta determinada.</span><span class="sxs-lookup"><span data-stu-id="e9f47-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e9f47-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e9f47-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="e9f47-107">real: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9f47-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9f47-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="e9f47-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="e9f47-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9f47-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9f47-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="e9f47-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e9f47-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9f47-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9f47-112">Tolerancia absoluta en la diferencia entre real y expected.</span><span class="sxs-lookup"><span data-stu-id="e9f47-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9f47-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9f47-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

