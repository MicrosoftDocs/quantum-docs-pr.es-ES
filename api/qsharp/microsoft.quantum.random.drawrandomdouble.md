---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operación DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847626"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="ab7a6-102">Operación DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="ab7a6-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="ab7a6-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ab7a6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ab7a6-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ab7a6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ab7a6-105">Dibuja un número real aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="ab7a6-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="ab7a6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ab7a6-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ab7a6-107">min: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab7a6-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab7a6-108">Número real más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="ab7a6-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ab7a6-109">máx.: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab7a6-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab7a6-110">Número real más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="ab7a6-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="ab7a6-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab7a6-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab7a6-112">Un número real aleatorio en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="ab7a6-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="ab7a6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab7a6-113">Example</span></span>

<span data-ttu-id="ab7a6-114">El siguiente fragmento de código de Q # dibuja aleatoriamente un ángulo entre $0 $ y $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="ab7a6-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="ab7a6-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ab7a6-115">Remarks</span></span>

<span data-ttu-id="ab7a6-116">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="ab7a6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab7a6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab7a6-117">See Also</span></span>

- [<span data-ttu-id="ab7a6-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ab7a6-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)