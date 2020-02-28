---
title: Diseñar su propio clasificador con el QDK
description: Conozca los conceptos básicos para diseñar modelos de circuito para el clasificador centrado en el circuito de Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909728"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="add50-103">Diseñar su propio clasificador</span><span class="sxs-lookup"><span data-stu-id="add50-103">Design your own classifier</span></span>

<span data-ttu-id="add50-104">En esta guía aprenderá los conceptos básicos que se basan en el diseño de modelos de circuito para el clasificador centrado en el circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="add50-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="add50-105">Como en el aprendizaje profundo clásico, no hay ninguna regla general para elegir una arquitectura específica.</span><span class="sxs-lookup"><span data-stu-id="add50-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="add50-106">Dependiendo del problema, algunas arquitecturas funcionarán mejor que otras.</span><span class="sxs-lookup"><span data-stu-id="add50-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="add50-107">Pero hay algunos conceptos que pueden ser útiles al diseñar el circuito:</span><span class="sxs-lookup"><span data-stu-id="add50-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="add50-108">Un gran número de parámetros implica un modelo más flexible, que puede ser adecuado para dibujar límites de clasificación complicados, pero que también puede ser más susceptible al sobreajuste.</span><span class="sxs-lookup"><span data-stu-id="add50-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="add50-109">La inestabilidad de las puertas entre qubits es esencial para capturar las correlaciones entre las características de Quantum.</span><span class="sxs-lookup"><span data-stu-id="add50-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="add50-110">Cómo crear un clasificador con Q\#</span><span class="sxs-lookup"><span data-stu-id="add50-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="add50-111">Para crear un clasificador, vamos a concatenar rotaciones controladas por parametrizadas en nuestro modelo de circuito.</span><span class="sxs-lookup"><span data-stu-id="add50-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="add50-112">Para ello, podemos usar el tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definido en la biblioteca de Quantum machine learning.</span><span class="sxs-lookup"><span data-stu-id="add50-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="add50-113">Este tipo acepta cuatro argumentos que determinan: el índice del qubit de destino, la matriz de índices del control qubits, el eje de rotación y el índice del parámetro asociado en la matriz de parámetros que define el modelo.</span><span class="sxs-lookup"><span data-stu-id="add50-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="add50-114">Vamos a ver un ejemplo de un clasificador.</span><span class="sxs-lookup"><span data-stu-id="add50-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="add50-115">En el [ejemplo Half-lunas](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), podemos encontrar el clasificador siguiente definido en el archivo `Training.qs`.</span><span class="sxs-lookup"><span data-stu-id="add50-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="add50-116">Lo que estamos definiendo aquí es una función que devuelve una matriz de elementos `ControlledRotation`, que, junto con una matriz de parámetros, y una diferencia definirán nuestro [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span><span class="sxs-lookup"><span data-stu-id="add50-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="add50-117">Este tipo es fundamental en la biblioteca de Machine Learning Quantum y define el clasificador.</span><span class="sxs-lookup"><span data-stu-id="add50-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="add50-118">El circuito definido en la función anterior forma parte de un clasificador en el que cada muestra del conjunto de elementos contiene dos características.</span><span class="sxs-lookup"><span data-stu-id="add50-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="add50-119">Por lo tanto, solo necesitamos dos qubits.</span><span class="sxs-lookup"><span data-stu-id="add50-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="add50-120">La representación gráfica del circuito es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="add50-120">The graphical representation of the circuit is:</span></span>

 ![Ejemplo de modelo de circuito](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="add50-122">Usar las funciones de la biblioteca para escribir capas de puertas</span><span class="sxs-lookup"><span data-stu-id="add50-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="add50-123">Supongamos que tenemos un conjunto de elementos con 784 características por instancia, por ejemplo, imágenes de 28 × 28 píxeles como el conjunto de MNIST.</span><span class="sxs-lookup"><span data-stu-id="add50-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="add50-124">En este caso, el ancho del circuito es lo suficientemente grande como para que la escritura a mano de cada puerta individual sea una tarea posible pero no práctica.</span><span class="sxs-lookup"><span data-stu-id="add50-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="add50-125">Este es el motivo por el que la biblioteca de Quantum Machine Learning proporciona un conjunto de herramientas para generar automáticamente las capas de giros parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="add50-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="add50-126">Por ejemplo, la función [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) devuelve una matriz de rotaciones de un solo qubit sin control a lo largo de un eje determinado, con un giro para cada qubit en el registro, cada parametrizadas por un parámetro de modelo diferente.</span><span class="sxs-lookup"><span data-stu-id="add50-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="add50-127">Por ejemplo, `LocalRotationsLayer(4, X)` devuelve el siguiente conjunto de puertas:</span><span class="sxs-lookup"><span data-stu-id="add50-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Capa de rotación local](~/media/local_rotations_layer.PNG)

<span data-ttu-id="add50-129">Le recomendamos que explore el [referenece de API de la biblioteca Quantum machine learning](xref:microsoft.quantum.machinelearning) para detectar todas las herramientas disponibles para optimizar el diseño del circuito.</span><span class="sxs-lookup"><span data-stu-id="add50-129">We recommend you to explore the [API referenece of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="add50-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="add50-130">Next steps</span></span>

 <span data-ttu-id="add50-131">Pruebe diferentes estructuras en los ejemplos proporcionados por los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="add50-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="add50-132">¿Ve algún cambio en el rendimiento del modelo?</span><span class="sxs-lookup"><span data-stu-id="add50-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="add50-133">En el siguiente tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), aprenderá a cargar conjuntos de información para probar y explorar nuevas arquitecturas de clasificadores.</span><span class="sxs-lookup"><span data-stu-id="add50-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
