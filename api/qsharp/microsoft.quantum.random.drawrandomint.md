---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192917"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="672df-102">Operación DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="672df-102">DrawRandomInt operation</span></span>

<span data-ttu-id="672df-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="672df-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="672df-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="672df-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="672df-105">Dibuja un entero aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="672df-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="672df-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="672df-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="672df-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="672df-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="672df-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="672df-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="672df-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="672df-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="672df-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="672df-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="672df-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="672df-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="672df-112">Un entero en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="672df-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="672df-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="672df-113">Remarks</span></span>

<span data-ttu-id="672df-114">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="672df-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="672df-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="672df-115">See Also</span></span>

- [<span data-ttu-id="672df-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="672df-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)