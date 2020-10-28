---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operación SampleTransformedContinuousDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733204"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="19149-102">Operación SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="19149-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="19149-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="19149-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="19149-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19149-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19149-105">Operación solo interna para el muestreo de distribuciones transformadas.</span><span class="sxs-lookup"><span data-stu-id="19149-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="19149-106">Solo se debe usar a través de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="19149-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="19149-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="19149-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="19149-108">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="19149-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="19149-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="19149-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="19149-110">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="19149-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

