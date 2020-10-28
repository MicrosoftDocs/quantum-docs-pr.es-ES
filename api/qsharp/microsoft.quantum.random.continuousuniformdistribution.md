---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725811"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="0f6fa-102">ContinuousUniformDistribution función)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="0f6fa-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0f6fa-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f6fa-105">Devuelve una distribución uniforme en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="0f6fa-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="0f6fa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f6fa-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="0f6fa-107">min: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f6fa-108">Número real más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="0f6fa-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="0f6fa-109">máx.: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f6fa-110">Número real más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="0f6fa-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="0f6fa-111">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="0f6fa-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="0f6fa-112">Una distribución cuyos variates aleatorios son números reales en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="0f6fa-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f6fa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f6fa-113">Remarks</span></span>

<span data-ttu-id="0f6fa-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0f6fa-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f6fa-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f6fa-115">See Also</span></span>

- [<span data-ttu-id="0f6fa-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="0f6fa-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)