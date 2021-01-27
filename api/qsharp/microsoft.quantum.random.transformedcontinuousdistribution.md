---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857767"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="ca673-102">TransformedContinuousDistribution función)</span><span class="sxs-lookup"><span data-stu-id="ca673-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="ca673-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ca673-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ca673-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ca673-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ca673-105">Dada una distribución continua, devuelve una nueva distribución que transforma el original por una función determinada.</span><span class="sxs-lookup"><span data-stu-id="ca673-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="ca673-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ca673-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="ca673-107">transformación: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ca673-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ca673-108">Función que transforma variates de la distribución original en la distribución transformada.</span><span class="sxs-lookup"><span data-stu-id="ca673-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="ca673-109">distribución: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ca673-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ca673-110">Distribución original que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="ca673-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="ca673-111">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ca673-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ca673-112">Nueva distribución relacionada con `distribution` la transformación proporcionada por `transform` .</span><span class="sxs-lookup"><span data-stu-id="ca673-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="ca673-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca673-113">Example</span></span>

<span data-ttu-id="ca673-114">Las dos distribuciones siguientes son idénticas:</span><span class="sxs-lookup"><span data-stu-id="ca673-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```