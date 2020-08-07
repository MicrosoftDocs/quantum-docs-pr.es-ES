---
title: Diseñar su propio clasificador con el QDK
description: Conozca los conceptos básicos para diseñar modelos de circuito para el clasificador centrado en el circuito de Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 60e694e9f7c2f01a6679ef960f5a7774c8bd6a62
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868954"
---
# <a name="design-your-own-classifier"></a>Diseño de su propio clasificador

En esta guía aprenderá los conceptos básicos que se basan en el diseño de modelos de circuito para el clasificador centrado en el circuito Quantum.

Como en el aprendizaje profundo clásico, no hay ninguna regla general para elegir una arquitectura específica. Dependiendo del problema, algunas arquitecturas funcionarán mejor que otras. Pero hay algunos conceptos que pueden ser útiles al diseñar el circuito:

- Un gran número de parámetros implica un modelo más flexible, que puede ser adecuado para dibujar límites de clasificación complicados, pero que también puede ser más susceptible al sobreajuste.

- La inestabilidad de las puertas entre qubits es esencial para capturar las correlaciones entre las características de Quantum.

## <a name="how-to-build-a-classifier-with-q"></a>Cómo compilar un clasificador con Q\#

Para crear un clasificador, vamos a concatenar rotaciones controladas por parametrizadas en nuestro modelo de circuito. Para ello, podemos usar el tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definido en la biblioteca Quantum machine learning. Este tipo acepta cuatro argumentos que determinan: el índice del qubit de destino, la matriz de índices del control qubits, el eje de rotación y el índice del parámetro asociado en la matriz de parámetros que define el modelo.

Vamos a ver un ejemplo de un clasificador. En el [ejemplo Half-lunas](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), podemos encontrar el clasificador siguiente definido en el archivo `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

Lo que estamos definiendo aquí es una función que devuelve una matriz de `ControlledRotation` elementos, que junto con una matriz de parámetros y una diferencia definirán nuestro [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) . Este tipo es fundamental en la biblioteca de Machine Learning Quantum y define el clasificador. El circuito definido en la función anterior forma parte de un clasificador en el que cada muestra del conjunto de elementos contiene dos características. Por lo tanto, solo necesitamos dos qubits. La representación gráfica del circuito es la siguiente:

 ![Ejemplo de modelo de circuito](~/media/circuit_model_1.PNG)

Tenga en cuenta que, de forma predeterminada, las operaciones de la biblioteca Quantum Machine Learning miden el último qubit del registro para estimar las probabilidades de clasificación. Tenga en cuenta este hecho al diseñar el circuito.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Usar las funciones de la biblioteca para escribir capas de puertas

Supongamos que tenemos un conjunto de elementos con 784 características por instancia, por ejemplo, imágenes de 28 × 28 píxeles como el conjunto de MNIST. En este caso, el ancho del circuito es lo suficientemente grande como para que la escritura a mano de cada puerta individual sea una tarea posible pero no práctica. Este es el motivo por el que la biblioteca de Quantum Machine Learning proporciona un conjunto de herramientas para generar automáticamente las capas de giros parametrizadas. Por ejemplo, la función [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) devuelve una matriz de rotaciones de un solo qubit sin control a lo largo de un eje determinado, con un giro para cada qubit en el registro, cada parametrizadas por un parámetro de modelo diferente. Por ejemplo, `LocalRotationsLayer(4, X)` devuelve el siguiente conjunto de puertas:

 ![Capa de rotación local](~/media/local_rotations_layer.PNG)

Le recomendamos que explore la [referencia de API de la biblioteca Quantum machine learning](xref:microsoft.quantum.machinelearning) para detectar todas las herramientas disponibles para optimizar el diseño del circuito.

## <a name="next-steps"></a>Pasos siguientes

 Pruebe diferentes estructuras en los ejemplos proporcionados por los ejemplos. ¿Ve algún cambio en el rendimiento del modelo? En el siguiente tutorial, obtendrá [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) información sobre cómo cargar conjuntos de información para probar y explorar nuevas arquitecturas de clasificadores.
