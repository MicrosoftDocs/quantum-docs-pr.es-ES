---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operación TrainSequentialClassifier
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 97865965bef831eeb53245ba0c23d6bce54643ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847704"
---
# <a name="trainsequentialclassifier-operation"></a>Operación TrainSequentialClassifier

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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