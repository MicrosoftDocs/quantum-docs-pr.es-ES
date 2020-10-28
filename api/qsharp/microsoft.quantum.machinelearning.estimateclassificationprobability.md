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
# <a name="estimateclassificationprobability-operation"></a>Operación EstimateClassificationProbability

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Dado un ejemplo y un clasificador secuencial, calcula la probabilidad de clasificación para ese ejemplo midiendo repetidamente la salida del clasificador en el ejemplo determinado.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia que se permite en la codificación del ejemplo en una operación de preparación del estado.


### <a name="model--sequentialmodel"></a>Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modelo secuencial que se va a utilizar para calcular la probabilidad de clasificación para el ejemplo determinado.


### <a name="sample--double"></a>ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vector de características para el ejemplo que se va a clasificar.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular la probabilidad de clasificación.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Una estimación de la probabilidad de clasificación para el ejemplo determinado.