---
title: Clasificación básica con la biblioteca Quantum Machine Learning
description: 'Obtenga información sobre cómo ejecutar un clasificador secuencial Quantum escrito en Q # con la biblioteca Quantum Machine Learning de Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275789"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="5ee12-103">Clasificación básica: clasificación de datos con QDK</span><span class="sxs-lookup"><span data-stu-id="5ee12-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="5ee12-104">En esta guía de inicio rápido, obtendrá información sobre cómo ejecutar un clasificador secuencial de Quantum escrito en Q # con la biblioteca de Quantum Machine Learning de QDK.</span><span class="sxs-lookup"><span data-stu-id="5ee12-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="5ee12-105">En esta guía, usaremos el conjunto de caracteres de media luna con una estructura de clasificador definida en Q #.</span><span class="sxs-lookup"><span data-stu-id="5ee12-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ee12-106">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="5ee12-106">Prerequisites</span></span>

- <span data-ttu-id="5ee12-107">[Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="5ee12-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="5ee12-108">Cree un proyecto de Q # para un [programa host de Python](xref:microsoft.quantum.install.python) o un [programa host de C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="5ee12-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="5ee12-109">Programa host</span><span class="sxs-lookup"><span data-stu-id="5ee12-109">Host program</span></span>

<span data-ttu-id="5ee12-110">El programa host consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="5ee12-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="5ee12-111">Cargue el conjunto de DataSet y elija un conjunto de parámetros de inicio para el modelo.</span><span class="sxs-lookup"><span data-stu-id="5ee12-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="5ee12-112">Ejecute el entrenamiento para determinar los parámetros y la desviación del modelo.</span><span class="sxs-lookup"><span data-stu-id="5ee12-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="5ee12-113">Validar el modelo para determinar su precisión</span><span class="sxs-lookup"><span data-stu-id="5ee12-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="5ee12-114">Python con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5ee12-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="5ee12-115">Para ejecutarlo es el clasificador de preguntas y respuestas de Python, guarde el código siguiente como `host.py` .</span><span class="sxs-lookup"><span data-stu-id="5ee12-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="5ee12-116">Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5ee12-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="5ee12-117">A continuación, puede ejecutar el programa host de Python desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5ee12-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="5ee12-118">C# con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5ee12-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="5ee12-119">Para ejecutarlo es el clasificador de preguntas y respuestas de C#, guarde el código siguiente como `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="5ee12-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="5ee12-120">Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5ee12-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="5ee12-121">A continuación, puede ejecutar el programa host de C# desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5ee12-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="5ee12-122">C# con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5ee12-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="5ee12-123">Para ejecutar el nuevo programa de preguntas # desde C# en Visual Studio, modifique `Host.cs` para que incluya el siguiente código de c#.</span><span class="sxs-lookup"><span data-stu-id="5ee12-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="5ee12-124">Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5ee12-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="5ee12-125">Después, presione F5; el programa iniciará la ejecución y se mostrará una nueva ventana con los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="5ee12-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="5ee12-126">Q ( \# código de clasificador)</span><span class="sxs-lookup"><span data-stu-id="5ee12-126">Q\# classifier code</span></span>

<span data-ttu-id="5ee12-127">Ahora veamos cómo se definen las operaciones invocadas por el programa host en Q #.</span><span class="sxs-lookup"><span data-stu-id="5ee12-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="5ee12-128">Se guarda el código siguiente en un archivo denominado `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="5ee12-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="5ee12-129">Las funciones y operaciones más importantes definidas en el código anterior son:</span><span class="sxs-lookup"><span data-stu-id="5ee12-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="5ee12-130">`ClassifierStructure() : ControlledRotation[]`: en esta función se establece la estructura de nuestro modelo de circuito agregando las capas de las puertas controladas que se consideran.</span><span class="sxs-lookup"><span data-stu-id="5ee12-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="5ee12-131">Este paso es análogo a la declaración de capas de neuronas en un modelo de aprendizaje profundo secuencial.</span><span class="sxs-lookup"><span data-stu-id="5ee12-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="5ee12-132">`TrainHalfMoonModel() : (Double[], Double)`: esta operación es la parte principal del código y define el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5ee12-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="5ee12-133">Aquí se cargan los ejemplos del conjunto de DataSet incluido en la biblioteca, se establecen los parámetros de hiperparámetros y los parámetros iniciales para el entrenamiento y se inicia el entrenamiento mediante una llamada a la operación `TrainSequentialClassifier` incluida en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5ee12-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="5ee12-134">Genera los parámetros y la diferencia que determinan el clasificador.</span><span class="sxs-lookup"><span data-stu-id="5ee12-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="5ee12-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: esta operación define el proceso de validación para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5ee12-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="5ee12-136">Aquí se cargan los ejemplos de validación, el número de medidas por muestra y la tolerancia.</span><span class="sxs-lookup"><span data-stu-id="5ee12-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="5ee12-137">Genera el número de clasificaciones incorrectas en el lote elegido de ejemplos para la validación.</span><span class="sxs-lookup"><span data-stu-id="5ee12-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ee12-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5ee12-138">Next steps</span></span>

<span data-ttu-id="5ee12-139">En primer lugar, puede reproducirse con el código e intentar cambiar algunos parámetros para ver cómo afecta al entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5ee12-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="5ee12-140">A continuación, en el siguiente tutorial, [Diseñe su propio clasificador](xref:microsoft.quantum.libraries.machine-learning.design), aprenderá a definir la estructura del clasificador.</span><span class="sxs-lookup"><span data-stu-id="5ee12-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
