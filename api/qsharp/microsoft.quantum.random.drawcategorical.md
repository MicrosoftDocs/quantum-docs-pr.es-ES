---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operación DrawCategorical
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851151"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="27fed-102">Operación DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="27fed-102">DrawCategorical operation</span></span>

<span data-ttu-id="27fed-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="27fed-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="27fed-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="27fed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="27fed-105">Dibuja un ejemplo aleatorio a partir de una distribución de categorías especificada por una lista de probablities.</span><span class="sxs-lookup"><span data-stu-id="27fed-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="27fed-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="27fed-106">Description</span></span>

<span data-ttu-id="27fed-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="27fed-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="27fed-108">Los elementos de matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="27fed-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="27fed-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="27fed-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="27fed-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="27fed-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="27fed-111">sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="27fed-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="27fed-112">Una matriz de números de punto flotante proporcional a la probabilidad de seleccionar cada índice.</span><span class="sxs-lookup"><span data-stu-id="27fed-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="27fed-113">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27fed-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27fed-114">Un entero $i $ con probabilidad $ \Pr (i) = p_i/\ sum_i p_i $, donde $p _i $ es el elemento $i $ TH de `probs` .</span><span class="sxs-lookup"><span data-stu-id="27fed-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="27fed-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27fed-115">See Also</span></span>

- [<span data-ttu-id="27fed-116">Microsoft. Quantum. random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="27fed-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)