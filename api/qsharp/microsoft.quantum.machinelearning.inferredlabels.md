---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732349"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="96861-102">InferredLabels función)</span><span class="sxs-lookup"><span data-stu-id="96861-102">InferredLabels function</span></span>

<span data-ttu-id="96861-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="96861-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="96861-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96861-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96861-105">Dada una matriz de probabilidades de clasificación y una diferencia, devuelve la etiqueta deducida de cada probabilidad.</span><span class="sxs-lookup"><span data-stu-id="96861-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="96861-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96861-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="96861-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96861-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96861-108">La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.</span><span class="sxs-lookup"><span data-stu-id="96861-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="96861-109">probabilidades: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="96861-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="96861-110">Matriz de probabilidades de clasificación para un conjunto de ejemplos, normalmente resultante de la estimación de frecuencias de clasificación.</span><span class="sxs-lookup"><span data-stu-id="96861-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="96861-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="96861-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="96861-112">La etiqueta deducida de cada probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="96861-112">The label inferred from each classification probability.</span></span>