---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operación DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733212"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="50ced-102">Operación DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="50ced-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="50ced-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="50ced-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="50ced-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50ced-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50ced-105">Dibuja un número real aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="50ced-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="50ced-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="50ced-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="50ced-107">min: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50ced-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50ced-108">Número real más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="50ced-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="50ced-109">máx.: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50ced-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50ced-110">Número real más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="50ced-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="50ced-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50ced-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50ced-112">Un número real aleatorio en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="50ced-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="50ced-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="50ced-113">Remarks</span></span>

<span data-ttu-id="50ced-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="50ced-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="50ced-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50ced-115">See Also</span></span>

- [<span data-ttu-id="50ced-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="50ced-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)