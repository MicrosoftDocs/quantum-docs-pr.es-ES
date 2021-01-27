---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842344"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="1a64b-102">CategoricalDistribution función)</span><span class="sxs-lookup"><span data-stu-id="1a64b-102">CategoricalDistribution function</span></span>

<span data-ttu-id="1a64b-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1a64b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1a64b-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1a64b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1a64b-105">Devuelve una distribución de categorías discretas, en la que se especifica explícitamente la probabilidad de cada una de las listas finitas de determinados resultados.</span><span class="sxs-lookup"><span data-stu-id="1a64b-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="1a64b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1a64b-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="1a64b-107">sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a64b-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1a64b-108">Probabilidades para cada resultado de la distribución por categorías.</span><span class="sxs-lookup"><span data-stu-id="1a64b-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="1a64b-109">Es posible que estas probabilidades no estén normalizadas, pero no deben ser negativas.</span><span class="sxs-lookup"><span data-stu-id="1a64b-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="1a64b-110">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="1a64b-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="1a64b-111">Índice `i` con probabilidad `probs[i] / sum` , donde `sum` es la suma de `probs` especificada por `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="1a64b-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="1a64b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a64b-112">Example</span></span>

<span data-ttu-id="1a64b-113">El siguiente código de Q # mostrará 0 con probabilidad de 30% y 1 con probabilidad 70%:</span><span class="sxs-lookup"><span data-stu-id="1a64b-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```