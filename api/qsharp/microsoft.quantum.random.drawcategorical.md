---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operación DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193002"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="66378-102">Operación DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="66378-102">DrawCategorical operation</span></span>

<span data-ttu-id="66378-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="66378-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="66378-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="66378-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="66378-105">Dibuja un ejemplo aleatorio a partir de una distribución de categorías especificada por una lista de probablities.</span><span class="sxs-lookup"><span data-stu-id="66378-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="66378-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="66378-106">Description</span></span>

<span data-ttu-id="66378-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="66378-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="66378-108">Los elementos de matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="66378-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="66378-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="66378-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="66378-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="66378-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="66378-111">sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="66378-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="66378-112">Una matriz de números de punto flotante proporcional a la probabilidad de seleccionar cada índice.</span><span class="sxs-lookup"><span data-stu-id="66378-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="66378-113">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66378-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66378-114">Un entero $i $ con probabilidad $ \Pr (i) = p_i/\ sum_i p_i $, donde $p _i $ es el elemento $i $ TH de `probs` .</span><span class="sxs-lookup"><span data-stu-id="66378-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="66378-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66378-115">See Also</span></span>

- [<span data-ttu-id="66378-116">Microsoft. Quantum. random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="66378-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)