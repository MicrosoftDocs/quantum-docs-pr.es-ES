---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operación DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192951"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="2fe80-102">Operación DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="2fe80-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="2fe80-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2fe80-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2fe80-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2fe80-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2fe80-105">Dibuja un número real aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="2fe80-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2fe80-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2fe80-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="2fe80-107">min: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fe80-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fe80-108">Número real más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="2fe80-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="2fe80-109">máx.: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fe80-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fe80-110">Número real más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="2fe80-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="2fe80-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fe80-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fe80-112">Un número real aleatorio en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="2fe80-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fe80-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2fe80-113">Remarks</span></span>

<span data-ttu-id="2fe80-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="2fe80-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe80-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fe80-115">See Also</span></span>

- [<span data-ttu-id="2fe80-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="2fe80-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)