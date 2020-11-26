---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226271"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="8fd43-102">TransformedContinuousDistribution función)</span><span class="sxs-lookup"><span data-stu-id="8fd43-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="8fd43-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8fd43-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8fd43-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8fd43-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8fd43-105">Dada una distribución continua, devuelve una nueva distribución que transforma el original por una función determinada.</span><span class="sxs-lookup"><span data-stu-id="8fd43-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="8fd43-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8fd43-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="8fd43-107">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8fd43-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8fd43-108">Función que transforma variates de la distribución original en la distribución transformada.</span><span class="sxs-lookup"><span data-stu-id="8fd43-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="8fd43-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8fd43-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8fd43-110">Distribución original que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="8fd43-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="8fd43-111">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8fd43-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8fd43-112">Nueva distribución relacionada con `distribution` la transformación proporcionada por `transform` .</span><span class="sxs-lookup"><span data-stu-id="8fd43-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>