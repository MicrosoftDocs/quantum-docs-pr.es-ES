---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196368"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="043ea-102">InferredLabels función)</span><span class="sxs-lookup"><span data-stu-id="043ea-102">InferredLabels function</span></span>

<span data-ttu-id="043ea-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="043ea-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="043ea-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="043ea-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="043ea-105">Dada una matriz de probabilidades de clasificación y una diferencia, devuelve la etiqueta deducida de cada probabilidad.</span><span class="sxs-lookup"><span data-stu-id="043ea-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="043ea-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="043ea-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="043ea-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="043ea-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="043ea-108">La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.</span><span class="sxs-lookup"><span data-stu-id="043ea-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="043ea-109">probabilidades: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="043ea-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="043ea-110">Matriz de probabilidades de clasificación para un conjunto de ejemplos, normalmente resultante de la estimación de frecuencias de clasificación.</span><span class="sxs-lookup"><span data-stu-id="043ea-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="043ea-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="043ea-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="043ea-112">La etiqueta deducida de cada probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="043ea-112">The label inferred from each classification probability.</span></span>