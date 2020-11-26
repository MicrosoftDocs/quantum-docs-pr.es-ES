---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Tipo definido por el usuario TrainingOptions
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196130"
---
# <a name="trainingoptions-user-defined-type"></a>Tipo definido por el usuario TrainingOptions

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Colección de opciones que se va a utilizar para entrenar clasificadores de Quantum.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Elementos con nombre

### <a name="learningrate--double"></a>LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)

Velocidad de aprendizaje por la que se deben cambiar los degradados al actualizar los parámetros del modelo durante los pasos de entrenamiento.
### <a name="tolerance--double"></a>Tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia de aproximación que se va a usar al preparar ejemplos como Estados de Quantum.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Número de muestras que se van a usar en cada minilote de entrenamiento.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de veces que se va a medir cada resultado de la clasificación para calcular la probabilidad de clasificación.
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de tiempos para entrenar cada modelo.
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

Número máximo de veces que se permite que una época de entrenamiento se detenga (aproximadamente el degradado de cero) antes de que se produzca un error.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)

La cantidad para cambiar el tamaño de los modelos detenidas antes de volver a intentar una actualización.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

El número de pasos de degradado que se van a realizar entre los puntos de puntuación.
Para obtener la mejor precisión, establezca en 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [String](xref:microsoft.quantum.lang-ref.string) -> [unidad](xref:microsoft.quantum.lang-ref.unit) de cadena

Función que se puede utilizar para proporcionar comentarios detallados.

## <a name="remarks"></a>Observaciones

Este UDT no se debe crear directamente, sino que se debe especificar llamando a @"microsoft.quantum.machinelearning.defaulttrainingoptions" y, a continuación, utilizando el `w/` operador para reemplazar los valores predeterminados diferentes.

Por ejemplo, para usar medidas 100.000 y como máximo 8 tiempos de entrenamiento:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Referencias

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)