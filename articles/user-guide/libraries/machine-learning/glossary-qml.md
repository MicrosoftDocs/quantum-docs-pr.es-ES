---
title: Glosario de la biblioteca de aprendizaje automático de Quantum
description: Glosario de términos de aprendizaje automático Quantum
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 476e93e3737dee6ad8f3a97e8ffbcfb9b0012ee1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691508"
---
# <a name="quantum-machine-learning-glossary"></a>Glosario de Machine Learning Quantum

El entrenamiento de un clasificador de Quantum centrado en circuitos es un proceso con muchas partes móviles que requieren la misma cantidad de calibrado (o un poco mayor) de calibración por prueba y error como formación de clasificadores tradicionales. Aquí se definen los principales conceptos e ingredientes de este proceso de entrenamiento.

## <a name="trainingtesting-schedules"></a>Programaciones de entrenamiento y pruebas

En el contexto del entrenamiento del clasificador, una *programación* describe un subconjunto de muestras de datos en un conjunto de entrenamiento o de prueba global. Normalmente, una programación se define como una colección de índices de ejemplo.

## <a name="parameterbias-scores"></a>Puntuaciones de parámetros/sesgo

Dado un vector de parámetro candidato y una diferencia del clasificador, su *puntuación de validación* se mide en relación con las programaciones de validación seleccionadas y se expresa mediante un número de clasificaciones incorrectas contadas en todos los ejemplos de las programaciones.

## <a name="hyperparameters"></a>Hiperparámetros

El proceso de entrenamiento del modelo se rige por ciertos valores preestablecidos denominados *hiperparámetros* :

### <a name="learning-rate"></a>Velocidad de aprendizaje

Es uno de los hiperparámetros de clave. Define cuánta estimación de degradado de estocástico actual afecta a la actualización del parámetro. El tamaño del delta de actualización de parámetros es proporcional a la velocidad de aprendizaje. Los valores de velocidad de aprendizaje más pequeños conducen a una evolución de parámetros más lenta y una convergencia más lenta, pero los valores excesivamente grandes de LR pueden romper la convergencia como el descenso del degradado nunca se confirma en un mínimo local determinado. Aunque el algoritmo de entrenamiento ajusta de forma adaptable la velocidad de aprendizaje en cierta medida, es importante seleccionar un buen valor inicial. Un valor inicial predeterminado habitual para la velocidad de aprendizaje es 0,1. La selección del mejor valor de velocidad de aprendizaje es una buena idea (vea, por ejemplo, la sección 4,3 de Goodfellow et al., "aprendizaje profundo", MIT Press, 2017).

### <a name="minibatch-size"></a>Tamaño de minilote

Define el número de muestras de datos que se usan para una única estimación del degradado estocástico. Los valores más grandes del tamaño de minilote generalmente conducen a una convergencia más sólida y más monotónica, pero pueden ralentizar el proceso de entrenamiento, ya que el costo de una estimación de degradado es proporcional al tamaño de MiniMatch. Un valor predeterminado habitual para el tamaño de minilote es 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Tiempo de entrenamiento, tolerancia, gridlocks

"Tiempo" hace referencia a un paso completo a través de los datos de entrenamiento programados.
El número máximo de tiempo por un subproceso de entrenamiento (consulte a continuación) debe estar limitado. El subproceso de entrenamiento se define para finalizar (con los mejores parámetros de candidato conocidos) cuando se ha ejecutado el número máximo de tiempos. Sin embargo, este entrenamiento terminaría antes cuando la tasa de errores de clasificación en la programación de la validación cae por debajo de una tolerancia seleccionada. Supongamos, por ejemplo, que la tolerancia de clasificación incorrecta es 0,01 (1%); si en el conjunto de validación de 2000 ejemplos vemos menos de 20 clasificaciones incorrectas, se ha logrado el nivel de tolerancia. Un subproceso de entrenamiento también finaliza prematuramente si la puntuación de validación del modelo candidato no ha mostrado ninguna mejora respecto a varias duraciones consecutivas (un Gridlock). La lógica para la terminación de Gridlock está codificada actualmente.

### <a name="measurements-count"></a>Recuento de medidas

La estimación de las puntuaciones de entrenamiento y validación y los componentes del degradado estocástico en un dispositivo Quantum se calcula para calcular las superposiciones de estado de Quantum que requieren varias mediciones del observables adecuado. El número de medidas se debe escalar como $O (1/\ épsilon ^ 2) $ donde $ \epsilon $ es el error de estimación deseado.
Como regla general, el número de mediciones iniciales podría ser aproximadamente $1/\ mbox {Tolerance} ^ 2 $ (consulte la definición de tolerancia en el párrafo anterior). Es necesario revisar el recuento de medidas hacia arriba si el descenso del degradado parece ser demasiado errático y convergencia demasiado difícil de lograr.

### <a name="training-threads"></a>Entrenamiento de subprocesos

La función de probabilidad, que es la utilidad de entrenamiento del clasificador, es muy rara vez convexa, lo que significa que normalmente tiene una gran cantidad de optimación local en el espacio de parámetros que puede diferir significativamente en la calidad. Dado que el proceso SGD puede converger solo en un óptimo específico, es importante explorar varios vectores de parámetro de inicio. Una práctica común en el aprendizaje automático es inicializar los vectores iniciales de forma aleatoria. La Q# API de entrenamiento acepta una matriz arbitraria de tales vectores de inicio, pero el código subyacente los explora secuencialmente. En un equipo multinúcleo o de hecho en cualquier arquitectura de computación en paralelo, es aconsejable realizar varias llamadas a Q# la API de entrenamiento en paralelo con inicializaciones de parámetros diferentes en las llamadas.

#### <a name="how-to-modify-the-hyperparameters"></a>Cómo modificar los hiperparámetros

En la biblioteca QML, la mejor manera de modificar los hiperparámetros es invalidar los valores predeterminados del UDT [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) . Para ello, se llama con la función [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) y se aplica el operador `w/` para invalidar los valores predeterminados. Por ejemplo, para usar medidas 100.000 y una velocidad de aprendizaje de 0,01:

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
