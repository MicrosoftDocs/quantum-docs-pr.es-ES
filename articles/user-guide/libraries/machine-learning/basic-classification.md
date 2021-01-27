---
title: Clasificación básica con la biblioteca Quantum Machine Learning
description: Obtenga información sobre cómo ejecutar un clasificador secuencial de Quantum escrito en Q# mediante la biblioteca quantum machine learning de Microsoft QDK.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fe686a87fbdc610badc0bbcbc0bf7b065e0bce9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854042"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="3429c-103">Clasificación básica: clasificación de datos con QDK</span><span class="sxs-lookup"><span data-stu-id="3429c-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="3429c-104">En esta guía de inicio rápido, obtendrá información sobre cómo ejecutar un clasificador secuencial de Quantum escrito en Q# mediante la biblioteca de quantum machine learning de QDK.</span><span class="sxs-lookup"><span data-stu-id="3429c-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="3429c-105">En esta guía, usaremos el conjunto de caracteres de media luna con una estructura de clasificador definida en Q# .</span><span class="sxs-lookup"><span data-stu-id="3429c-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3429c-106">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="3429c-106">Prerequisites</span></span>

- <span data-ttu-id="3429c-107">[Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="3429c-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="3429c-108">Cree un Q# proyecto para un [programa host de Python](xref:microsoft.quantum.install.python) o un [programa host de C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="3429c-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="3429c-109">Programa host</span><span class="sxs-lookup"><span data-stu-id="3429c-109">Host program</span></span>

<span data-ttu-id="3429c-110">El programa host consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="3429c-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="3429c-111">Cargue el conjunto de DataSet y elija un conjunto de parámetros de inicio para el modelo.</span><span class="sxs-lookup"><span data-stu-id="3429c-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="3429c-112">Ejecute el entrenamiento para determinar los parámetros y la desviación del modelo.</span><span class="sxs-lookup"><span data-stu-id="3429c-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="3429c-113">Validar el modelo para determinar su precisión</span><span class="sxs-lookup"><span data-stu-id="3429c-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="3429c-114">Python con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3429c-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="3429c-115">Para ejecutarlo es el Q# clasificador de Python, guarde el código siguiente como `host.py` .</span><span class="sxs-lookup"><span data-stu-id="3429c-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="3429c-116">Recuerde que también necesita el Q# archivo `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3429c-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="3429c-117">A continuación, puede ejecutar el programa host de Python desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="3429c-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="3429c-118">C# con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3429c-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="3429c-119">Para ejecutarlo, es el Q# clasificador de C#, guarde el código siguiente como `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="3429c-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="3429c-120">Recuerde que también necesita el Q# archivo `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3429c-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="3429c-121">A continuación, puede ejecutar el programa host de C# desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="3429c-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="3429c-122">C# con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3429c-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="3429c-123">Para ejecutar el nuevo Q# programa desde C# en Visual Studio, modifique `Host.cs` para que incluya el siguiente código de c#.</span><span class="sxs-lookup"><span data-stu-id="3429c-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="3429c-124">Recuerde que también necesita el Q# archivo `Training.qs` que se explica más adelante en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3429c-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="3429c-125">Presione F5 y el programa comenzará a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="3429c-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="3429c-126">Se mostrarán los siguientes resultados en una nueva ventana:</span><span class="sxs-lookup"><span data-stu-id="3429c-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="3429c-127">Q ( \# código de clasificador)</span><span class="sxs-lookup"><span data-stu-id="3429c-127">Q\# classifier code</span></span>

<span data-ttu-id="3429c-128">Ahora veamos cómo se definen las operaciones invocadas por el programa host en Q# .</span><span class="sxs-lookup"><span data-stu-id="3429c-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="3429c-129">Se guarda el código siguiente en un archivo denominado `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="3429c-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="3429c-130">Las funciones y operaciones más importantes definidas en el código anterior son:</span><span class="sxs-lookup"><span data-stu-id="3429c-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="3429c-131">`ClassifierStructure() : ControlledRotation[]` : en esta función se establece la estructura de nuestro modelo de circuito agregando las capas de las puertas controladas que se consideran.</span><span class="sxs-lookup"><span data-stu-id="3429c-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="3429c-132">Este paso es análogo a la declaración de capas de neuronas en un modelo de aprendizaje profundo secuencial.</span><span class="sxs-lookup"><span data-stu-id="3429c-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="3429c-133">`TrainHalfMoonModel() : (Double[], Double)` : esta operación es la parte principal del código y define el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="3429c-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="3429c-134">Aquí se cargan los ejemplos del conjunto de DataSet incluido en la biblioteca, se establecen los parámetros de hiperparámetros y los parámetros iniciales para el entrenamiento y se inicia el entrenamiento mediante una llamada a la operación `TrainSequentialClassifier` incluida en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3429c-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="3429c-135">Genera los parámetros y la diferencia que determinan el clasificador.</span><span class="sxs-lookup"><span data-stu-id="3429c-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="3429c-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : esta operación define el proceso de validación para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3429c-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="3429c-137">Aquí se cargan los ejemplos de validación, el número de medidas por muestra y la tolerancia.</span><span class="sxs-lookup"><span data-stu-id="3429c-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="3429c-138">Genera el número de clasificaciones incorrectas en el lote elegido de ejemplos para la validación.</span><span class="sxs-lookup"><span data-stu-id="3429c-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3429c-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3429c-139">Next steps</span></span>

<span data-ttu-id="3429c-140">En primer lugar, puede reproducirse con el código e intentar cambiar algunos parámetros para ver cómo afecta al entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="3429c-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="3429c-141">A continuación, en el siguiente tutorial, [Diseñe su propio clasificador](xref:microsoft.quantum.libraries.machine-learning.design), aprenderá a definir la estructura del clasificador.</span><span class="sxs-lookup"><span data-stu-id="3429c-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
