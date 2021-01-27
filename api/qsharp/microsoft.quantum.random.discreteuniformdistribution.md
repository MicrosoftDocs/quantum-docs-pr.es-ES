---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853715"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="0d714-102">DiscreteUniformDistribution función)</span><span class="sxs-lookup"><span data-stu-id="0d714-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="0d714-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0d714-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0d714-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0d714-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0d714-105">Devuelve una distribución uniforme en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="0d714-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="0d714-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d714-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="0d714-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d714-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d714-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="0d714-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="0d714-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d714-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d714-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="0d714-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="0d714-111">Salida: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="0d714-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="0d714-112">Una distribución cuyos variates aleatorios son enteros en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="0d714-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="0d714-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d714-113">Example</span></span>

<span data-ttu-id="0d714-114">El siguiente fragmento de código de Q # revierte aleatoriamente un dado de seis lados:</span><span class="sxs-lookup"><span data-stu-id="0d714-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="0d714-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d714-115">Remarks</span></span>

<span data-ttu-id="0d714-116">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0d714-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d714-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d714-117">See Also</span></span>

- [<span data-ttu-id="0d714-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="0d714-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)