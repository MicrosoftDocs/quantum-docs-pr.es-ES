---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Tipo definido por el usuario TrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842784"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="c9219-102">Tipo definido por el usuario TrainingOptions</span><span class="sxs-lookup"><span data-stu-id="c9219-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="c9219-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c9219-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c9219-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c9219-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c9219-105">Colección de opciones que se va a utilizar para entrenar clasificadores de Quantum.</span><span class="sxs-lookup"><span data-stu-id="c9219-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="c9219-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="c9219-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="c9219-107">LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9219-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9219-108">Velocidad de aprendizaje por la que se deben cambiar los degradados al actualizar los parámetros del modelo durante los pasos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="c9219-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="c9219-109">Tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9219-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9219-110">Tolerancia de aproximación que se va a usar al preparar ejemplos como Estados de Quantum.</span><span class="sxs-lookup"><span data-stu-id="c9219-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="c9219-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9219-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9219-112">Número de muestras que se van a usar en cada minilote de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="c9219-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="c9219-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9219-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9219-114">Número de veces que se va a medir cada resultado de la clasificación para calcular la probabilidad de clasificación.</span><span class="sxs-lookup"><span data-stu-id="c9219-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="c9219-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9219-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9219-116">Número máximo de tiempos para entrenar cada modelo.</span><span class="sxs-lookup"><span data-stu-id="c9219-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="c9219-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9219-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9219-118">Número máximo de veces que se permite que una época de entrenamiento se detenga (aproximadamente el degradado de cero) antes de que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="c9219-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="c9219-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9219-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9219-120">La cantidad para cambiar el tamaño de los modelos detenidas antes de volver a intentar una actualización.</span><span class="sxs-lookup"><span data-stu-id="c9219-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="c9219-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9219-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9219-122">El número de pasos de degradado que se van a realizar entre los puntos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="c9219-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="c9219-123">Para obtener la mejor precisión, establezca en 1.</span><span class="sxs-lookup"><span data-stu-id="c9219-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="c9219-124">VerboseMessage: [](xref:microsoft.quantum.lang-ref.string) -> [unidad](xref:microsoft.quantum.lang-ref.unit) de cadena</span><span class="sxs-lookup"><span data-stu-id="c9219-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="c9219-125">Función que se puede utilizar para proporcionar comentarios detallados.</span><span class="sxs-lookup"><span data-stu-id="c9219-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9219-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9219-126">Remarks</span></span>

<span data-ttu-id="c9219-127">Este UDT no se debe crear directamente, sino que se debe especificar llamando a @"microsoft.quantum.machinelearning.defaulttrainingoptions" y, a continuación, utilizando el `w/` operador para reemplazar los valores predeterminados diferentes.</span><span class="sxs-lookup"><span data-stu-id="c9219-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="c9219-128">Por ejemplo, para usar medidas 100.000 y como máximo 8 tiempos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="c9219-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="c9219-129">Referencias</span><span class="sxs-lookup"><span data-stu-id="c9219-129">References</span></span>

- [<span data-ttu-id="c9219-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="c9219-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)