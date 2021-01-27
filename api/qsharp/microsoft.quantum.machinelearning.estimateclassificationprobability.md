---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operación EstimateClassificationProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853936"
---
# <a name="estimateclassificationprobability-operation"></a>Operación EstimateClassificationProbability

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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