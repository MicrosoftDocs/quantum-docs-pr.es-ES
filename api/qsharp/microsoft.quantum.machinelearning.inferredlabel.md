---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732372"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="f4144-102">InferredLabel función)</span><span class="sxs-lookup"><span data-stu-id="f4144-102">InferredLabel function</span></span>

<span data-ttu-id="f4144-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f4144-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f4144-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4144-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4144-105">Dado una de probabilidad de clasificación y una diferencia, devuelve la etiqueta deducida de esa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="f4144-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="f4144-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4144-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="f4144-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4144-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4144-108">La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.</span><span class="sxs-lookup"><span data-stu-id="f4144-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="f4144-109">probabilidad: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4144-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4144-110">Una probabilidad de clasificación para un ejemplo determinado, que normalmente resulta de la estimación de la frecuencia de clasificación.</span><span class="sxs-lookup"><span data-stu-id="f4144-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="f4144-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4144-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4144-112">La etiqueta deducida de la probabilidad de clasificación dada.</span><span class="sxs-lookup"><span data-stu-id="f4144-112">The label inferred from the given classification probability.</span></span>