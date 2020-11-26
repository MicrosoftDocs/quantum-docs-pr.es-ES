---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210257"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="b3c88-102">CategoricalDistribution función)</span><span class="sxs-lookup"><span data-stu-id="b3c88-102">CategoricalDistribution function</span></span>

<span data-ttu-id="b3c88-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b3c88-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b3c88-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b3c88-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b3c88-105">Devuelve una distribución de categorías discretas, en la que se especifica explícitamente la probabilidad de cada una de las listas finitas de determinados resultados.</span><span class="sxs-lookup"><span data-stu-id="b3c88-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="b3c88-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b3c88-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="b3c88-107">sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b3c88-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b3c88-108">Probabilidades para cada resultado de la distribución por categorías.</span><span class="sxs-lookup"><span data-stu-id="b3c88-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="b3c88-109">Es posible que estas probabilidades no estén normalizadas, pero no deben ser negativas.</span><span class="sxs-lookup"><span data-stu-id="b3c88-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="b3c88-110">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="b3c88-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="b3c88-111">Índice `i` con probabilidad `probs[i] / sum` , donde `sum` es la suma de `probs` especificada por `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="b3c88-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>