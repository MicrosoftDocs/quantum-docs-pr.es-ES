---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731189"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="6d38a-102">_RunSingleTrainingEpoch operación</span><span class="sxs-lookup"><span data-stu-id="6d38a-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="6d38a-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6d38a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6d38a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d38a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d38a-105">Realice un tiempo de aprendizaje de clasificador secuencial en un subconjunto de muestras de datos.</span><span class="sxs-lookup"><span data-stu-id="6d38a-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="6d38a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6d38a-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="6d38a-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="6d38a-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="6d38a-108">Programación: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="6d38a-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="6d38a-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d38a-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d38a-110">El número de pasos de degradado que se van a realizar entre los puntos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="6d38a-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="6d38a-111">Para obtener la mejor precisión, establezca en 1.</span><span class="sxs-lookup"><span data-stu-id="6d38a-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="6d38a-112">opciones: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="6d38a-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="6d38a-113">Opciones que se van a usar en el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="6d38a-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="6d38a-114">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="6d38a-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="6d38a-115">Modelo secuencial que se va a entrenar.</span><span class="sxs-lookup"><span data-stu-id="6d38a-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="6d38a-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d38a-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d38a-117">El mejor número de clasificaciones incorrectas observadas en las épocas anteriores.</span><span class="sxs-lookup"><span data-stu-id="6d38a-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="6d38a-118">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="6d38a-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="6d38a-119">El menor número de clasificaciones incorrectas observadas hasta este tiempo.</span><span class="sxs-lookup"><span data-stu-id="6d38a-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="6d38a-120">Se encontró el nuevo modelo secuencial mejor.</span><span class="sxs-lookup"><span data-stu-id="6d38a-120">The new best sequential model found.</span></span>