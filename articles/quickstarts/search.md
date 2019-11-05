---
title: 'Ejecución del algoritmo de búsqueda de Grover en Q#: Quantum Development Kit'
description: Compile un proyecto de Q# que demuestre el algoritmo de Grover, uno de los algoritmos cuánticos clásicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443943"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="7f429-103">Inicio rápido: Implementación del algoritmo de búsqueda de Grover en Q#</span><span class="sxs-lookup"><span data-stu-id="7f429-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="7f429-104">En este inicio rápido, puede aprender cómo compilar y ejecutar una búsqueda de Grover para acelerar la búsqueda de datos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="7f429-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="7f429-105">La búsqueda de Grover es uno de los algoritmos de computación cuántica más populares, y esta implementación de Q# relativamente pequeña da una idea de algunas de las ventajas de programar soluciones cuánticas con el lenguaje de programación cuántica Q# de alto nivel para expresar algoritmos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="7f429-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="7f429-106">Al final de la guía, verá la salida de la simulación que muestra cómo se ha encontrado correctamente una cadena específica entre una lista de entradas sin ordenar en una fracción del tiempo que se tardaría en buscar en toda la lista en un equipo clásico.</span><span class="sxs-lookup"><span data-stu-id="7f429-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="7f429-107">El algoritmo de Grover busca una lista de datos no estructurados para elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="7f429-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="7f429-108">Por ejemplo, puede responder a la siguiente pregunta: ¿Esta carta sacada de una baraja es un as de corazones?</span><span class="sxs-lookup"><span data-stu-id="7f429-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="7f429-109">El etiquetado del elemento específico se denomina _entrada marcada_.</span><span class="sxs-lookup"><span data-stu-id="7f429-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="7f429-110">Mediante el algoritmo de búsqueda de Grover, se garantiza que un equipo cuántico ejecute esta búsqueda en menos pasos que el número de elementos de la lista que está buscando, algo que no puede hacer ningún algoritmo clásico.</span><span class="sxs-lookup"><span data-stu-id="7f429-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="7f429-111">El aumento de velocidad en el caso de una baraja de cartas es insignificante; sin embargo, en listas que contienen millones o miles de millones de elementos, se vuelve significativo.</span><span class="sxs-lookup"><span data-stu-id="7f429-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="7f429-112">Puede compilar un algoritmo de búsqueda de Grover con unas pocas líneas de código.</span><span class="sxs-lookup"><span data-stu-id="7f429-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f429-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7f429-113">Prerequisites</span></span>

- <span data-ttu-id="7f429-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="7f429-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="7f429-115">¿Qué hace el algoritmo de búsqueda de Grover?</span><span class="sxs-lookup"><span data-stu-id="7f429-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="7f429-116">El algoritmo de Grover pregunta si un elemento de una lista es el que estamos buscando.</span><span class="sxs-lookup"><span data-stu-id="7f429-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="7f429-117">Lo hace mediante la construcción de una superposición cuántica de los índices de la lista con cada coeficiente (o amplitud de probabilidad), que representa la probabilidad de que ese índice específico sea el que está buscando.</span><span class="sxs-lookup"><span data-stu-id="7f429-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="7f429-118">En la base del algoritmo hay dos pasos que aumentan gradualmente el coeficiente del índice que estamos buscando, hasta que la amplitud de probabilidad de dicho coeficiente se aproxima a uno.</span><span class="sxs-lookup"><span data-stu-id="7f429-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="7f429-119">El número de aumentos incrementales es menor que el número de elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="7f429-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="7f429-120">Este es el motivo por el que el algoritmo de búsqueda de Grover ejecuta la búsqueda en menos pasos que cualquier algoritmo clásico.</span><span class="sxs-lookup"><span data-stu-id="7f429-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagrama funcional del algoritmo de búsqueda de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="7f429-122">Escritura del código</span><span class="sxs-lookup"><span data-stu-id="7f429-122">Write the code</span></span>

1. <span data-ttu-id="7f429-123">Con Quantum Development Kit, [cree un nuevo proyecto de Q#](xref:microsoft.quantum.howto.createproject) denominado `Grover` en el entorno de desarrollo que prefiera.</span><span class="sxs-lookup"><span data-stu-id="7f429-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="7f429-124">Agregue el siguiente código al archivo `Operations.qs` del proyecto nuevo:</span><span class="sxs-lookup"><span data-stu-id="7f429-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="7f429-125">Para definir la lista que estamos buscando, cree un nuevo archivo `Reflections.qs` y péguelo en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="7f429-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="7f429-126">La operación `ReflectAboutMarked` define la entrada marcada que está buscando: la cadena que alterna ceros y unos.</span><span class="sxs-lookup"><span data-stu-id="7f429-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="7f429-127">Este ejemplo se integra como parte del código de la entrada marcada y se puede extender a la búsqueda de diferentes entradas o generalizar para cualquier entrada.</span><span class="sxs-lookup"><span data-stu-id="7f429-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="7f429-128">A continuación, ejecute el programa de Q# para buscar el elemento marcado por `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="7f429-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="7f429-129">Python con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7f429-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="7f429-130">Para ejecutar el nuevo programa de Q# desde Python, guarde el código siguiente como `host.py`:</span><span class="sxs-lookup"><span data-stu-id="7f429-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="7f429-131">A continuación, puede ejecutar el programa host de Python desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="7f429-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="7f429-132">C# con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7f429-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="7f429-133">Para ejecutar el nuevo programa de Q# desde C#, modifique `Driver.cs` para incluir el siguiente código de C#:</span><span class="sxs-lookup"><span data-stu-id="7f429-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="7f429-134">A continuación, puede ejecutar el programa host de C# desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="7f429-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="7f429-135">C# con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="7f429-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="7f429-136">Para ejecutar el nuevo programa de Q# desde C# en Visual Studio, modifique `Driver.cs` para que incluya el código C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f429-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="7f429-137">Después, presione F5; el programa iniciará la ejecución y se mostrará una nueva ventana con los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="7f429-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="7f429-138">Se ha llamado solo cuatro veces a la operación `ReflectAboutMarked`, pero el programa de Q# fue capaz de encontrar la entrada "01010" entre $2^{5} = 32$ entradas posibles.</span><span class="sxs-lookup"><span data-stu-id="7f429-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f429-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7f429-139">Next steps</span></span>

<span data-ttu-id="7f429-140">Si ha disfrutado de este inicio rápido, eche un vistazo a algunos de los siguientes recursos para obtener más información sobre el uso de Q# para escribir sus propias aplicaciones cuánticas:</span><span class="sxs-lookup"><span data-stu-id="7f429-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="7f429-141">Volver a la guía Introducción a QDK</span><span class="sxs-lookup"><span data-stu-id="7f429-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="7f429-142">Prueba de un [ejemplo](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) más general del algoritmo de búsqueda de Grover</span><span class="sxs-lookup"><span data-stu-id="7f429-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="7f429-143">Más información sobre la búsqueda de Grover con Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="7f429-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="7f429-144">Obtenga más información acerca de la [amplificación de la amplitud](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la técnica de computación cuántica que está detrás del algoritmo de búsqueda de Grover.</span><span class="sxs-lookup"><span data-stu-id="7f429-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="7f429-145">Conceptos de computación cuántica</span><span class="sxs-lookup"><span data-stu-id="7f429-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="7f429-146">Ejemplos de Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="7f429-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
