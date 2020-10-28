---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730965"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="2d9b0-102">DiscreteUniformDistribution función)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="2d9b0-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2d9b0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d9b0-105">Devuelve una distribución uniforme en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="2d9b0-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="2d9b0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2d9b0-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="2d9b0-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d9b0-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="2d9b0-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="2d9b0-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d9b0-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="2d9b0-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="2d9b0-111">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="2d9b0-112">Una distribución cuyos variates aleatorios son enteros en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="2d9b0-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d9b0-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d9b0-113">Remarks</span></span>

<span data-ttu-id="2d9b0-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="2d9b0-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d9b0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d9b0-115">See Also</span></span>

- [<span data-ttu-id="2d9b0-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="2d9b0-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)