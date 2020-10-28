---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operación EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725960"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="8c6f1-102">Operación EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="8c6f1-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="8c6f1-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8c6f1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c6f1-105">Dado un ejemplo y un clasificador secuencial, calcula la probabilidad de clasificación para ese ejemplo midiendo repetidamente la salida del clasificador en el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="8c6f1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8c6f1-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="8c6f1-107">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8c6f1-108">Tolerancia que se permite en la codificación del ejemplo en una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="8c6f1-109">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="8c6f1-110">Modelo secuencial que se va a utilizar para calcular la probabilidad de clasificación para el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="8c6f1-111">ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8c6f1-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8c6f1-112">Vector de características para el ejemplo que se va a clasificar.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="8c6f1-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c6f1-114">Número de medidas que se van a usar para calcular la probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="8c6f1-115">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8c6f1-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8c6f1-116">Una estimación de la probabilidad de clasificación para el ejemplo determinado.</span><span class="sxs-lookup"><span data-stu-id="8c6f1-116">An estimate of the classification probability for the given sample.</span></span>