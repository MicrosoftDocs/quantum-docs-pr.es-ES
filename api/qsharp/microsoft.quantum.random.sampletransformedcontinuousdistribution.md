---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operación SampleTransformedContinuousDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: 62f6f4ff372143228de007c98a23697022fcfd24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856099"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="6077b-102">Operación SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="6077b-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="6077b-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6077b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6077b-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6077b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6077b-105">Operación solo interna para el muestreo de distribuciones transformadas.</span><span class="sxs-lookup"><span data-stu-id="6077b-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="6077b-106">Solo se debe usar a través de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="6077b-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="6077b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6077b-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="6077b-108">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6077b-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="6077b-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="6077b-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="6077b-110">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6077b-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

