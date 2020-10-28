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
# <a name="validatesequentialclassifier-operation"></a>Operación ValidateSequentialClassifier

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Valida un clasificador secuencial determinado con respecto a un conjunto determinado de muestras con etiqueta previa.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Entrada

### <a name="model--sequentialmodel"></a>Modelo: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modelo secuencial que se va a validar.


### <a name="samples--labeledsample"></a>ejemplos: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Los ejemplos que se van a usar para validar el modelo determinado.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia de aproximación que se va a usar para codificar cada ejemplo como una entrada al clasificador secuencial.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

El número de medidas que se utilizarán para clasificar cada ejemplo.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

La programación por la que se deben extraer los ejemplos del conjunto de validación.



## <a name="output--validationresults"></a>Salida: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Resultados de la validación especificada.