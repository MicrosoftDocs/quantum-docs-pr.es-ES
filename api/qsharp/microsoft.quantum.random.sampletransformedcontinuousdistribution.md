---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operación SampleTransformedContinuousDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: f9f2b3cbbb4423f267758976cd066abbfec93a77
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192696"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="60737-102">Operación SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="60737-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="60737-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="60737-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="60737-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="60737-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="60737-105">Operación solo interna para el muestreo de distribuciones transformadas.</span><span class="sxs-lookup"><span data-stu-id="60737-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="60737-106">Solo se debe usar a través de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="60737-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="60737-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="60737-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="60737-108">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60737-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="60737-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="60737-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="60737-110">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60737-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

