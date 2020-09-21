---
title: Ejecutar el algoritmo de búsqueda de Grover en Q# el kit de desarrollo de Quantum
description: Compile un Q# proyecto que muestre el algoritmo de Grover, uno de los algoritmos de Quantum canónicos.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86c6a651a117b788eb4c8fdd805ead7ab8f54dd7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834812"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="d3ffe-103">Tutorial: Implementación del algoritmo de búsqueda de Grover en Q\#</span><span class="sxs-lookup"><span data-stu-id="d3ffe-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="d3ffe-104">En este tutorial, puede aprender cómo compilar y ejecutar una búsqueda de Grover para acelerar la búsqueda de datos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="d3ffe-105">La búsqueda de Grover es uno de los algoritmos de cálculo de Quantum más populares, y esta implementación relativamente pequeña Q# ofrece una idea de algunas de las ventajas de la programación de soluciones Quantum con un lenguaje de programación Quantum de alto nivel Q# para expresar los algoritmos Quantum.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="d3ffe-106">Al final de la guía, verá la salida de la simulación que muestra cómo se ha encontrado correctamente una cadena específica entre una lista de entradas sin ordenar en una fracción del tiempo que se tardaría en buscar en toda la lista en un equipo clásico.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="d3ffe-107">El algoritmo de Grover busca una lista de datos no estructurados para elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="d3ffe-108">Por ejemplo, puede responder a la siguiente pregunta: ¿Esta carta sacada de una baraja es un as de corazones?</span><span class="sxs-lookup"><span data-stu-id="d3ffe-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="d3ffe-109">El etiquetado del elemento específico se denomina _entrada marcada_.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="d3ffe-110">Mediante el algoritmo de búsqueda de Grover, se garantiza que un equipo cuántico ejecute esta búsqueda en menos pasos que el número de elementos de la lista que está buscando, algo que no puede hacer ningún algoritmo clásico.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="d3ffe-111">El aumento de velocidad en el caso de una baraja de cartas es insignificante; sin embargo, en listas que contienen millones o miles de millones de elementos, se vuelve significativo.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="d3ffe-112">Puede compilar un algoritmo de búsqueda de Grover con unas pocas líneas de código.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3ffe-113">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="d3ffe-113">Prerequisites</span></span>

- <span data-ttu-id="d3ffe-114">[Kit de desarrollo de Microsoft Quantum][install].</span><span class="sxs-lookup"><span data-stu-id="d3ffe-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="d3ffe-115">¿Qué hace el algoritmo de búsqueda de Grover?</span><span class="sxs-lookup"><span data-stu-id="d3ffe-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="d3ffe-116">El algoritmo de Grover pregunta si un elemento de una lista es el que estamos buscando.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="d3ffe-117">Lo hace mediante la construcción de una superposición cuántica de los índices de la lista con cada coeficiente (o amplitud de probabilidad), que representa la probabilidad de que ese índice específico sea el que está buscando.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="d3ffe-118">En la base del algoritmo hay dos pasos que aumentan gradualmente el coeficiente del índice que estamos buscando, hasta que la amplitud de probabilidad de dicho coeficiente se aproxima a uno.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="d3ffe-119">El número de aumentos incrementales es menor que el número de elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="d3ffe-120">Este es el motivo por el que el algoritmo de búsqueda de Grover ejecuta la búsqueda en menos pasos que cualquier algoritmo clásico.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagrama funcional del algoritmo de búsqueda de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="d3ffe-122">Escritura del código</span><span class="sxs-lookup"><span data-stu-id="d3ffe-122">Write the code</span></span>

1. <span data-ttu-id="d3ffe-123">Con el kit de desarrollo de Quantum, [cree un nuevo Q# proyecto para la aplicación](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="d3ffe-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="d3ffe-124">Asigne al proyecto el nombre `Grover`.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="d3ffe-125">Agregue el siguiente código al archivo `Program.qs` del proyecto nuevo:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="d3ffe-126">Para definir la lista que estamos buscando, cree un nuevo archivo `Reflections.qs` y péguelo en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="d3ffe-127">La operación `ReflectAboutMarked` define la entrada marcada que está buscando: la cadena que alterna ceros y unos.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="d3ffe-128">Este ejemplo se integra como parte del código de la entrada marcada y se puede extender a la búsqueda de diferentes entradas o generalizar para cualquier entrada.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="d3ffe-129">A continuación, ejecute el nuevo Q# programa para buscar el elemento marcado por `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="d3ffe-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="d3ffe-130">Q# aplicaciones con Visual Studio o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d3ffe-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="d3ffe-131">El programa ejecutará la operación o función marcada con el `@EntryPoint()` atributo en un simulador o estimador de recursos, en función de la configuración del proyecto y las opciones de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-131">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="d3ffe-132">En Visual Studio, simplemente presione Ctrl + F5 para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-132">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="d3ffe-133">En VS Code, escriba lo siguiente en el terminal para compilar `Program.qs` la primera vez:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="d3ffe-134">En las ejecuciones posteriores, no es necesario volver a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="d3ffe-135">Para ejecutarlo, escriba el siguiente comando y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="d3ffe-136">Verá el mensaje siguiente en el terminal:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="d3ffe-137">Esto se debe a que no especificó el número de qubits que deseaba usar, por lo que el terminal muestra los comandos disponibles para el programa ejecutable.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal shows you the commands available for the executable program.</span></span> <span data-ttu-id="d3ffe-138">Si queremos usar 5 qubits, debemos escribir:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-138">If we want to use 5 qubits, we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="d3ffe-139">Presione Entrar y verá la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="d3ffe-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d3ffe-140">Next steps</span></span>

<span data-ttu-id="d3ffe-141">Si disfrutase de este tutorial, consulte algunos de los recursos siguientes para obtener más información sobre cómo puede usar Q# para escribir sus propias aplicaciones Quantum:</span><span class="sxs-lookup"><span data-stu-id="d3ffe-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="d3ffe-142">Volver a la guía Introducción a QDK</span><span class="sxs-lookup"><span data-stu-id="d3ffe-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="d3ffe-143">Prueba de un [ejemplo](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) más general del algoritmo de búsqueda de Grover</span><span class="sxs-lookup"><span data-stu-id="d3ffe-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="d3ffe-144">Más información sobre la búsqueda de Grover con Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="d3ffe-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="d3ffe-145">Obtenga más información acerca de la [amplificación de la amplitud][amplitude-amplification], la técnica de computación cuántica que está detrás del algoritmo de búsqueda de Grover.</span><span class="sxs-lookup"><span data-stu-id="d3ffe-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="d3ffe-146">Conceptos de computación cuántica</span><span class="sxs-lookup"><span data-stu-id="d3ffe-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="d3ffe-147">Ejemplos del kit de desarrollo de Microsoft Quantum</span><span class="sxs-lookup"><span data-stu-id="d3ffe-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
