---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732541"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="aaa25-102">CategoricalDistribution función)</span><span class="sxs-lookup"><span data-stu-id="aaa25-102">CategoricalDistribution function</span></span>

<span data-ttu-id="aaa25-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="aaa25-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="aaa25-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aaa25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aaa25-105">Devuelve una distribución de categorías discretas, en la que se especifica explícitamente la probabilidad de cada una de las listas finitas de determinados resultados.</span><span class="sxs-lookup"><span data-stu-id="aaa25-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="aaa25-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aaa25-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="aaa25-107">sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aaa25-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="aaa25-108">Probabilidades para cada resultado de la distribución por categorías.</span><span class="sxs-lookup"><span data-stu-id="aaa25-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="aaa25-109">Es posible que estas probabilidades no estén normalizadas, pero no deben ser negativas.</span><span class="sxs-lookup"><span data-stu-id="aaa25-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="aaa25-110">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="aaa25-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="aaa25-111">Índice `i` con probabilidad `probs[i] / sum` , donde `sum` es la suma de `probs` especificada por `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="aaa25-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>