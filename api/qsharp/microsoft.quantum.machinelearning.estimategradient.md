---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operación EstimateGradient
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211855"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="84772-102">Operación EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="84772-102">EstimateGradient operation</span></span>

<span data-ttu-id="84772-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84772-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="84772-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84772-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="84772-105">Calcula el degradado de entrenamiento para un clasificador secuencial en un modelo determinado y para una entrada codificada determinada.</span><span class="sxs-lookup"><span data-stu-id="84772-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="84772-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="84772-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="84772-107">Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="84772-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="84772-108">Modelo secuencial cuyo degradado se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="84772-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="84772-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="84772-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="84772-110">Entrada al clasificador secuencial, codificada en una operación de preparación del estado.</span><span class="sxs-lookup"><span data-stu-id="84772-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="84772-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84772-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84772-112">Número de medidas que se van a usar para calcular el degradado.</span><span class="sxs-lookup"><span data-stu-id="84772-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="84772-113">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="84772-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="84772-114">Estimación del degradado de entrenamiento en los parámetros de entrada y de modelo dados.</span><span class="sxs-lookup"><span data-stu-id="84772-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="84772-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84772-115">Remarks</span></span>

<span data-ttu-id="84772-116">Esta operación usa una prueba de Hadamard y la técnica de cambio de parámetros conjuntamente para calcular el degradado.</span><span class="sxs-lookup"><span data-stu-id="84772-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>