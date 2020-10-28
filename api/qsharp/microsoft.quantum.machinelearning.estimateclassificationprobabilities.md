---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operación EstimateClassificationProbabilities
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725966"
---
# <a name="estimateclassificationprobabilities-operation"></a>Operación EstimateClassificationProbabilities

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


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