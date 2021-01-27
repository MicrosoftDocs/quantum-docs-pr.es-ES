---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848414"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="5ad58-102">InferredLabel función)</span><span class="sxs-lookup"><span data-stu-id="5ad58-102">InferredLabel function</span></span>

<span data-ttu-id="5ad58-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5ad58-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5ad58-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5ad58-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5ad58-105">Dado una de probabilidad de clasificación y una diferencia, devuelve la etiqueta deducida de esa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="5ad58-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="5ad58-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5ad58-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="5ad58-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5ad58-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5ad58-108">La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.</span><span class="sxs-lookup"><span data-stu-id="5ad58-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="5ad58-109">probabilidad: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5ad58-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5ad58-110">Una probabilidad de clasificación para un ejemplo determinado, que normalmente resulta de la estimación de la frecuencia de clasificación.</span><span class="sxs-lookup"><span data-stu-id="5ad58-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="5ad58-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ad58-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ad58-112">La etiqueta deducida de la probabilidad de clasificación dada.</span><span class="sxs-lookup"><span data-stu-id="5ad58-112">The label inferred from the given classification probability.</span></span>