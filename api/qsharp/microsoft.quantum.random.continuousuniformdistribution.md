---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842312"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="33904-102">ContinuousUniformDistribution función)</span><span class="sxs-lookup"><span data-stu-id="33904-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="33904-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="33904-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="33904-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="33904-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="33904-105">Devuelve una distribución uniforme en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="33904-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="33904-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="33904-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="33904-107">min: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33904-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33904-108">Número real más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="33904-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="33904-109">máx.: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33904-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33904-110">Número real más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="33904-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="33904-111">Salida: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="33904-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="33904-112">Una distribución cuyos variates aleatorios son números reales en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="33904-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="33904-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33904-113">Example</span></span>

<span data-ttu-id="33904-114">El siguiente fragmento de código de Q # dibuja aleatoriamente un ángulo entre $0 $ y $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="33904-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="33904-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33904-115">Remarks</span></span>

<span data-ttu-id="33904-116">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="33904-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="33904-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33904-117">See Also</span></span>

- [<span data-ttu-id="33904-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="33904-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)