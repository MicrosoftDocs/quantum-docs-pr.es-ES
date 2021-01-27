---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operación TrainSequentialClassifierAtModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857151"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="e0812-102">Operación TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="e0812-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="e0812-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e0812-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e0812-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e0812-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e0812-105">Dada la estructura de un clasificador secuencial, entrena el clasificador en un conjunto de entrenamiento con etiqueta determinado, empezando por un modelo determinado.</span><span class="sxs-lookup"><span data-stu-id="e0812-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="e0812-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e0812-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="e0812-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="e0812-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="e0812-108">Modelo secuencial que se va a usar como punto de partida para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="e0812-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="e0812-109">ejemplos: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="e0812-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="e0812-110">Un conjunto de datos de entrenamiento etiquetados que se usarán para realizar el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="e0812-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="e0812-111">opciones: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="e0812-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="e0812-112">Configuración que se va a usar al entrenar; vea @"microsoft.quantum.machinelearning.trainingoptions" y @"microsoft.quantum.machinelearning.defaulttrainingoptions" para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e0812-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="e0812-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e0812-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="e0812-114">Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento durante los pasos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="e0812-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="e0812-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e0812-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="e0812-116">Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento al seleccionar el punto de inicio que originó la mejor puntuación del clasificador.</span><span class="sxs-lookup"><span data-stu-id="e0812-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="e0812-117">Salida: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="e0812-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="e0812-118">Una parametrización del clasificador determinado y una diferencia entre las dos clases, que se corresponden con el mejor resultado de cada uno de los puntos de inicio especificados.</span><span class="sxs-lookup"><span data-stu-id="e0812-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="e0812-119">Número de errores observados en el mejor modelo clasificador.</span><span class="sxs-lookup"><span data-stu-id="e0812-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0812-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0812-120">See Also</span></span>

- [<span data-ttu-id="e0812-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="e0812-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="e0812-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="e0812-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)