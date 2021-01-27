---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operación DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851137"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="5a638-102">Operación DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="5a638-102">DrawRandomInt operation</span></span>

<span data-ttu-id="5a638-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5a638-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5a638-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5a638-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5a638-105">Dibuja un entero aleatorio en un intervalo inclusivo determinado.</span><span class="sxs-lookup"><span data-stu-id="5a638-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5a638-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5a638-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="5a638-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a638-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a638-108">Entero más pequeño que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="5a638-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="5a638-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a638-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a638-110">Entero más grande que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="5a638-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="5a638-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a638-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a638-112">Un entero en el intervalo inclusivo de `min` a `max` con probabilidad uniforme.</span><span class="sxs-lookup"><span data-stu-id="5a638-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="5a638-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a638-113">Example</span></span>

<span data-ttu-id="5a638-114">El siguiente fragmento de código de Q # revierte aleatoriamente un dado de seis lados:</span><span class="sxs-lookup"><span data-stu-id="5a638-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="5a638-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a638-115">Remarks</span></span>

<span data-ttu-id="5a638-116">Se produce un error si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="5a638-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a638-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a638-117">See Also</span></span>

- [<span data-ttu-id="5a638-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="5a638-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)