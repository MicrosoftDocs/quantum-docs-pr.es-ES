---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726459"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="d668e-102">TransformedContinuousDistribution función)</span><span class="sxs-lookup"><span data-stu-id="d668e-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="d668e-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d668e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d668e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d668e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d668e-105">Dada una distribución continua, devuelve una nueva distribución que transforma el original por una función determinada.</span><span class="sxs-lookup"><span data-stu-id="d668e-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="d668e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d668e-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="d668e-107">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d668e-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d668e-108">Función que transforma variates de la distribución original en la distribución transformada.</span><span class="sxs-lookup"><span data-stu-id="d668e-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="d668e-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="d668e-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="d668e-110">Distribución original que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="d668e-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="d668e-111">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="d668e-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="d668e-112">Nueva distribución relacionada con `distribution` la transformación proporcionada por `transform` .</span><span class="sxs-lookup"><span data-stu-id="d668e-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>