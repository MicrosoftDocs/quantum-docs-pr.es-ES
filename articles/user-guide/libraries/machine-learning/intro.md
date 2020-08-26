---
title: Biblioteca de aprendizaje automático cuántico
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 65b0aa6a7f385765933d4d89ce34901f77cf76ec
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863101"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introducción a Quantum Machine Learning

## <a name="framework-and-goals"></a>Marco de trabajo y objetivos

La codificación Quantum y el procesamiento de la información son una alternativa eficaz a los clasificadores de Quantum de aprendizaje automático clásico. En concreto, nos permite codificar los datos de registros Quantum que son concisos en relación con el número de características, con lo que se emplea sistemáticamente el nivel de Quantum como recurso computacional y se emplea la medida Quantum para la inferencia de clases.
El clasificador de Quantum centrados en circuitos es una solución Quantum relativamente sencilla que combina la codificación de datos con un circuito de Quantum de inenredo/disentangling rápido seguido de la medida para deducir las etiquetas de clase de las muestras de datos.
El objetivo es garantizar la caracterización clásica y el almacenamiento de los circuitos de asunto, así como el entrenamiento híbrido/clásico de los parámetros del circuito, incluso en el caso de los espacios de características muy grandes.

## <a name="classifier-architecture"></a>Arquitectura de clasificador

La clasificación es una tarea de aprendizaje automático supervisada, en la que el objetivo es deducir las etiquetas de clase $ \{ Y_1, y_2, \ldots y_d \} $ de ciertas muestras de datos. El "conjunto de datos de entrenamiento" es una colección de ejemplos $ \mathcal{D} = \{ (x, y)} $ con etiquetas preasignadas conocidas. Aquí $x $ es una muestra de datos y $y $ es su etiqueta conocida denominada "etiqueta de entrenamiento".
En cierto modo similares a los métodos tradicionales, la clasificación Quantum consta de tres pasos:
- codificación de datos
- preparación de un estado de clasificador
- medida debido a la naturaleza probabilística de la medición, estos tres pasos deben repetirse varias veces. Tanto la codificación como la informática del estado de clasificador se realizan por medio de *circuitos Quantum*. Aunque el circuito de codificación está normalmente controlado por datos y sin parámetros, el circuito clasificador contiene un conjunto suficiente de parámetros que se pueden aprender. 

En la solución propuesta, el circuito clasificador se compone de rotaciones de un solo qubit y rotaciones controladas por dos qubit. Los parámetros que se pueden aprender aquí son los ángulos de rotación. Se sabe que las puertas de rotación y rotación controlada son *universales* para el cálculo de Quantum, lo que significa que cualquier matriz de peso unitario se puede descomponer en un circuito suficientemente largo que conste de dichas puertas.

En la versión propuesta, solo se admite un circuito seguido de una estimación de una sola frecuencia.
Por lo tanto, la solución es un Quantum análogo de una máquina de vectores de soporte con un kernel Polinómico de bajo nivel.

![Perceptrón multinivel frente a clasificador centrado en circuito](~/media/DLvsQCC.png)

Un sencillo diseño de clasificadores de quantums puede compararse con una solución de máquina de vectores de soporte (SVM) tradicional. La inferencia de una muestra de datos $x $ en el caso de SVM se realiza con un formato de kernel óptimo $ \sum \ alpha_j k (x_j, x) $, donde $k $ es una determinada función de kernel.

Por el contrario, un clasificador de Quantum usa el $p de predicción (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) x 〉 $, que es similar en el espíritu pero técnicamente bastante diferente. Por lo tanto, cuando se utiliza una codificación de amplitud sencilla, $p (y │ x, U (\theta)) $ es una forma cuadrática en las amplitudes de $x $, pero los coeficientes de este formulario ya no se aprenden de forma independiente; en su lugar, se agregan a partir de los elementos de la matriz del $U del circuito (\theta) $, que normalmente tiene significativamente menos parámetros que se pueden aprender $ \theta $ que la dimensión del vector $x $. El grado Polinómico de $p (y │ x, U (\theta)) $ en las características originales se puede aumentar a $2 ^ l $ mediante el uso de una codificación de producto Quantum en $l $ copias de $x $.

Nuestra arquitectura explora circuitos relativamente superficiales que, por tanto, deben estar en *rápida* para capturar todas las correlaciones entre las características de datos en todos los intervalos. En la ilustración siguiente se muestra un ejemplo del componente de circuito de inestabilidad de rápida utilidad. Aunque un circuito con esta geometría consta solo de $3 n + 1 $ portones, la matriz de peso unitario que calcula garantiza una comunicación cruzada significativa entre las características de $2 ^ n $.

![Golpee rápidamente el circuito Quantum en 5 qubits (con dos capas cíclicas).](~/media/5-qubit-qccc.png)

El circuito del ejemplo anterior consta de 6 puertas de qubit única $ (G_1, \ldots G_5; G_ {16} ) $ y 10 2-qubits Gates $ (G_6, \ldots, G_ {15} ) $. Suponiendo que cada una de las puertas se define con un parámetro más aprendido, tenemos 16 parámetros que se van a aprender, mientras que la dimensión del espacio Hilbert de 5-qubit es 32. Esta geometría de circuito se puede generalizar fácilmente a cualquier $n registro $-qubit, cuando $n $ es impar, produciendo circuitos con $3 n + 1 $ Parameters para el espacio de características $2 ^ n $-dimensional.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Aprendizaje clasificador como una tarea de aprendizaje supervisado

El entrenamiento de un modelo clasificador implica buscar valores óptimos de sus parámetros operativos, de modo que maximicen la probabilidad media de deducir las etiquetas de entrenamiento correctas en los ejemplos de entrenamiento.
Aquí nos referimos a nosotros solo con la clasificación de dos niveles, es decir, el caso de $d = $2 y solo dos clases con las etiquetas $y _ 1, y_2 $.

> [!NOTE]
> Una manera de generalizar nuestros métodos a un número arbitrario de clases es reemplazar qubits con qudits, es decir, las unidades de Quantum con Estados de $d $ Basis y la medición bidireccional con $d medida de $-Way.

### <a name="likelihood-as-the-training-goal"></a>Probabilidad como objetivo de entrenamiento

Dado un circuito de Quantum más aprendido $U (\theta) $, donde $ \theta $ es un vector de parámetros y que denota la medida final de $M $, la probabilidad media de la inferencia de etiqueta correcta es $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = Y_1 | U (\theta) x) + \ sum_ {(x y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ Where $P (M = y | z) $ es la probabilidad de medir $y $ en el estado de Quantum $z $.
En este caso, basta con comprender que la función de probabilidad $ \mathcal{L} (\theta) $ es fluida en $ \theta $ y su derivado en cualquier $ \ theta_j $ se puede calcular esencialmente en el mismo protocolo Quantum que se usa para calcular la función de probabilidad. Esto permite optimizar $ \mathcal{L} (\theta) $ por descenso de gradiente.

### <a name="classifier-bias-and-training-score"></a>Puntuación del clasificador y puntuación de entrenamiento

Dados algunos valores intermedios (o finales) de los parámetros en $ \theta $, es necesario identificar un único valor real $b $ know como clasificación del *clasificador* para realizar la inferencia. La regla de inferencia de etiqueta funciona de la siguiente manera: 
- En un ejemplo $x $ se le asigna la etiqueta $y _2 $ si y solo si $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1) (de lo contrario, se le asigna etiqueta $y _ 1 $)

Claramente $b $ debe estar en el intervalo $ (-0.5, + 0.5) $ para que sea significativo.

Un caso de entrenamiento $ (x, y) \en \mathcal{D} $ se considera una *clasificación* incorrecta dada la diferencia $b $ si la etiqueta deducida para $x $ como por RULE1 es realmente diferente de $y $. El número total de clasificaciones incorrectas es la *puntuación de entrenamiento* del clasificador dada la diferencia $b $. La diferencia de clasificador *óptima* $b $ minimiza la puntuación de entrenamiento. Es fácil ver eso, según las estimaciones de probabilidad precalculadas $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, la diferencia de clasificador óptima se puede encontrar mediante la búsqueda binaria en el intervalo $ (-0.5, + 0.5) $ mediante la realización de un máximo de $ \ log_2 (| \mathcal{D} |) $ Steps.

### <a name="reference"></a>Referencia

Esta información debe ser suficiente para empezar a reproducir con el código. Sin embargo, si desea obtener más información sobre este modelo, lea la propuesta original: [ *' clasificadores de Quantum centrados en circuitos ', María Schuld, Alex Bocharov, KRYSTA Svore y Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

Además del ejemplo de código que verá en los pasos siguientes, también puede empezar a explorar la clasificación de Quantum en [este tutorial](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/QuantumClassification) . 
