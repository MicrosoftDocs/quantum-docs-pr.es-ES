---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193019"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="1726e-102">DiscreteUniformDistribution función)</span><span class="sxs-lookup"><span data-stu-id="1726e-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="1726e-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1726e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1726e-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1726e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1726e-105">Devuelve una distribución uniforme en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="1726e-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="1726e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1726e-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="1726e-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1726e-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1726e-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="1726e-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="1726e-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1726e-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1726e-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="1726e-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="1726e-111">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="1726e-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="1726e-112">Una distribución cuyos variates aleatorios son enteros en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="1726e-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="1726e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1726e-113">Remarks</span></span>

<span data-ttu-id="1726e-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="1726e-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1726e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1726e-115">See Also</span></span>

- [<span data-ttu-id="1726e-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="1726e-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)