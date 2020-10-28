---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733596"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="90fad-102">Operación DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="90fad-102">DrawRandomInt operation</span></span>

<span data-ttu-id="90fad-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="90fad-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="90fad-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90fad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90fad-105">Dibuja un entero aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="90fad-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="90fad-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="90fad-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="90fad-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90fad-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90fad-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="90fad-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="90fad-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90fad-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90fad-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="90fad-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="90fad-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90fad-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90fad-112">Un entero en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="90fad-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="90fad-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="90fad-113">Remarks</span></span>

<span data-ttu-id="90fad-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="90fad-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fad-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90fad-115">See Also</span></span>

- [<span data-ttu-id="90fad-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="90fad-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)