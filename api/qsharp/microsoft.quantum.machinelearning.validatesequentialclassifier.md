---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Operación ValidateSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731068"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="816a8-102">Operación ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="816a8-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="816a8-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="816a8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="816a8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="816a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="816a8-105">Valida un clasificador secuencial determinado con respecto a un conjunto determinado de muestras con etiqueta previa.</span><span class="sxs-lookup"><span data-stu-id="816a8-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="816a8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="816a8-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="816a8-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="816a8-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="816a8-108">Modelo secuencial que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="816a8-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="816a8-109">ejemplos: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="816a8-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="816a8-110">Los ejemplos que se van a usar para validar el modelo determinado.</span><span class="sxs-lookup"><span data-stu-id="816a8-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="816a8-111">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="816a8-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="816a8-112">Tolerancia de aproximación que se va a usar para codificar cada ejemplo como una entrada al clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="816a8-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="816a8-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="816a8-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="816a8-114">El número de medidas que se utilizarán para clasificar cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="816a8-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="816a8-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="816a8-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="816a8-116">La programación por la que se deben extraer los ejemplos del conjunto de validación.</span><span class="sxs-lookup"><span data-stu-id="816a8-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="816a8-117">Salida: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="816a8-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="816a8-118">Resultados de la validación especificada.</span><span class="sxs-lookup"><span data-stu-id="816a8-118">The results of the given validation.</span></span>