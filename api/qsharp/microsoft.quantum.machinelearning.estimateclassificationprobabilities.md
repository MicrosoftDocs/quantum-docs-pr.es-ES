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
# <a name="estimateclassificationprobabilities-operation"></a>Operación EstimateClassificationProbabilities

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado un conjunto de ejemplos y un clasificador secuencial, calcula la probabilidad de clasificación para esos ejemplos midiendo repetidamente la salida del clasificador en cada ejemplo.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia que se permite en la codificación del ejemplo en una operación de preparación del estado.


### <a name="model--sequentialmodel"></a>Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modelo secuencial que se va a utilizar para calcular las probabilidades de clasificación para los ejemplos proporcionados.


### <a name="samples--double"></a>ejemplos: [Double](xref:microsoft.quantum.lang-ref.double)[] []

Matriz de vectores de características para cada muestra que se va a clasificar.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular la probabilidad de clasificación.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de estimaciones de la probabilidad de clasificación para cada ejemplo determinado.