---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operación EstimateClassificationProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196470"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="4d38b-102">Operación EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="4d38b-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="4d38b-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4d38b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4d38b-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4d38b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4d38b-105">Dado un ejemplo y un clasificador secuencial, calcula la probabilidad de clasificación para ese ejemplo midiendo repetidamente la salida del clasificador en el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="4d38b-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="4d38b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4d38b-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="4d38b-107">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d38b-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d38b-108">Tolerancia que se permite en la codificación del ejemplo en una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="4d38b-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="4d38b-109">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="4d38b-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="4d38b-110">Modelo secuencial que se va a utilizar para calcular la probabilidad de clasificación para el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="4d38b-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="4d38b-111">ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4d38b-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4d38b-112">Vector de características para el ejemplo que se va a clasificar.</span><span class="sxs-lookup"><span data-stu-id="4d38b-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4d38b-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d38b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d38b-114">Número de medidas que se van a usar para calcular la probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="4d38b-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="4d38b-115">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d38b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d38b-116">Una estimación de la probabilidad de clasificación para el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="4d38b-116">An estimate of the classification probability for the given sample.</span></span>