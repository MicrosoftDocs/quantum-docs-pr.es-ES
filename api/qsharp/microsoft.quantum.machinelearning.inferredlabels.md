---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848407"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="1df39-102">InferredLabels función)</span><span class="sxs-lookup"><span data-stu-id="1df39-102">InferredLabels function</span></span>

<span data-ttu-id="1df39-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1df39-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1df39-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1df39-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1df39-105">Dada una matriz de probabilidades de clasificación y una diferencia, devuelve la etiqueta deducida de cada probabilidad.</span><span class="sxs-lookup"><span data-stu-id="1df39-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="1df39-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1df39-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="1df39-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1df39-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1df39-108">La diferencia entre dos clases, normalmente el resultado de entrenar un clasificador.</span><span class="sxs-lookup"><span data-stu-id="1df39-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="1df39-109">probabilidades: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1df39-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1df39-110">Matriz de probabilidades de clasificación para un conjunto de ejemplos, normalmente resultante de la estimación de frecuencias de clasificación.</span><span class="sxs-lookup"><span data-stu-id="1df39-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="1df39-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1df39-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1df39-112">La etiqueta deducida de cada probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="1df39-112">The label inferred from each classification probability.</span></span>