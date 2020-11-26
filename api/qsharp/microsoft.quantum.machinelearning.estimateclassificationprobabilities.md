---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operación EstimateClassificationProbabilities
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211906"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="a35a7-102">Operación EstimateClassificationProbabilities</span><span class="sxs-lookup"><span data-stu-id="a35a7-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="a35a7-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a35a7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a35a7-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a35a7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a35a7-105">Dado un conjunto de ejemplos y un clasificador secuencial, calcula la probabilidad de clasificación para esos ejemplos midiendo repetidamente la salida del clasificador en cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a35a7-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="a35a7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a35a7-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a35a7-107">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a35a7-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a35a7-108">Tolerancia que se permite en la codificación del ejemplo en una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="a35a7-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="a35a7-109">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a35a7-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="a35a7-110">Modelo secuencial que se va a utilizar para calcular las probabilidades de clasificación para los ejemplos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="a35a7-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="a35a7-111">ejemplos: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="a35a7-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="a35a7-112">Matriz de vectores de características para cada muestra que se va a clasificar.</span><span class="sxs-lookup"><span data-stu-id="a35a7-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="a35a7-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a35a7-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a35a7-114">Número de medidas que se van a usar para calcular la probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="a35a7-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="a35a7-115">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a35a7-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a35a7-116">Matriz de estimaciones de la probabilidad de clasificación para cada ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="a35a7-116">An array of estimates of the classification probability for each given sample.</span></span>