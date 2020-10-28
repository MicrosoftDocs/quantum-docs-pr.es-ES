---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operación TrainSequentialClassifierAtModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: b9e30e4e5bc23f56d9119083045967caff28f13a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731076"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="df45b-102">Operación TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="df45b-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="df45b-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="df45b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="df45b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df45b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df45b-105">Dada la estructura de un clasificador secuencial, entrena el clasificador en un conjunto de entrenamiento con etiqueta determinado, empezando por un modelo determinado.</span><span class="sxs-lookup"><span data-stu-id="df45b-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="df45b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="df45b-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="df45b-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="df45b-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="df45b-108">Modelo secuencial que se va a usar como punto de partida para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="df45b-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="df45b-109">ejemplos: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="df45b-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="df45b-110">Un conjunto de datos de entrenamiento etiquetados que se usarán para realizar el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="df45b-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="df45b-111">opciones: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="df45b-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="df45b-112">Configuración que se va a usar al entrenar; vea @"microsoft.quantum.machinelearning.trainingoptions" y @"microsoft.quantum.machinelearning.defaulttrainingoptions" para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="df45b-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="df45b-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="df45b-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="df45b-114">Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento durante los pasos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="df45b-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="df45b-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="df45b-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="df45b-116">Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento al seleccionar el punto de inicio que originó la mejor puntuación del clasificador.</span><span class="sxs-lookup"><span data-stu-id="df45b-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="df45b-117">Salida: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="df45b-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="df45b-118">Una parametrización del clasificador determinado y una diferencia entre las dos clases, que se corresponden con el mejor resultado de cada uno de los puntos de inicio especificados.</span><span class="sxs-lookup"><span data-stu-id="df45b-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="df45b-119">Número de errores observados en el mejor modelo clasificador.</span><span class="sxs-lookup"><span data-stu-id="df45b-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="df45b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df45b-120">See Also</span></span>

- [<span data-ttu-id="df45b-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="df45b-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="df45b-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="df45b-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)