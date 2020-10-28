---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operación TrainSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726615"
---
# <a name="trainsequentialclassifier-operation"></a>Operación TrainSequentialClassifier

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Dada la estructura de un clasificador secuencial, entrena el clasificador en un conjunto de entrenamiento con etiqueta determinado.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Entrada

### <a name="models--sequentialmodel"></a>modelos: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Matriz de modelos que se va a usar como punto de partida durante el entrenamiento.


### <a name="samples--labeledsample"></a>ejemplos: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Un conjunto de datos de entrenamiento etiquetados que se usarán para realizar el entrenamiento.


### <a name="options--trainingoptions"></a>opciones: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Configuración que se va a usar al entrenar; vea @"microsoft.quantum.machinelearning.trainingoptions" y @"microsoft.quantum.machinelearning.defaulttrainingoptions" para obtener más detalles.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento durante los pasos de entrenamiento.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Programación de muestreo que se va a usar al seleccionar muestras de los datos de entrenamiento al seleccionar el punto de inicio que originó la mejor puntuación del clasificador.



## <a name="output--sequentialmodelint"></a>Salida: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- Una parametrización del clasificador determinado y una diferencia entre las dos clases, que se corresponden con el mejor resultado de cada uno de los puntos de inicio especificados.
- Número de errores observados en el mejor modelo clasificador.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)