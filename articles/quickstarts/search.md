---
title: 'Ejecución del algoritmo de búsqueda de Grover en Q#: Quantum Development Kit'
description: Compile un proyecto de Q# que demuestre el algoritmo de Grover, uno de los algoritmos cuánticos clásicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906957"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Inicio rápido: Implementación del algoritmo de búsqueda de Grover en Q#

En este inicio rápido, puede aprender cómo compilar y ejecutar una búsqueda de Grover para acelerar la búsqueda de datos no estructurados.  La búsqueda de Grover es uno de los algoritmos de computación cuántica más populares, y esta implementación de Q# relativamente pequeña da una idea de algunas de las ventajas de programar soluciones cuánticas con el lenguaje de programación cuántica Q# de alto nivel para expresar algoritmos cuánticos.  Al final de la guía, verá la salida de la simulación que muestra cómo se ha encontrado correctamente una cadena específica entre una lista de entradas sin ordenar en una fracción del tiempo que se tardaría en buscar en toda la lista en un equipo clásico.

El algoritmo de Grover busca una lista de datos no estructurados para elementos específicos. Por ejemplo, puede responder a la siguiente pregunta: ¿Esta carta sacada de una baraja es un as de corazones? El etiquetado del elemento específico se denomina _entrada marcada_.

Mediante el algoritmo de búsqueda de Grover, se garantiza que un equipo cuántico ejecute esta búsqueda en menos pasos que el número de elementos de la lista que está buscando, algo que no puede hacer ningún algoritmo clásico. El aumento de velocidad en el caso de una baraja de cartas es insignificante; sin embargo, en listas que contienen millones o miles de millones de elementos, se vuelve significativo.

Puede compilar un algoritmo de búsqueda de Grover con unas pocas líneas de código.

## <a name="prerequisites"></a>Prerrequisitos

- Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>¿Qué hace el algoritmo de búsqueda de Grover?

El algoritmo de Grover pregunta si un elemento de una lista es el que estamos buscando. Lo hace mediante la construcción de una superposición cuántica de los índices de la lista con cada coeficiente (o amplitud de probabilidad), que representa la probabilidad de que ese índice específico sea el que está buscando.

En la base del algoritmo hay dos pasos que aumentan gradualmente el coeficiente del índice que estamos buscando, hasta que la amplitud de probabilidad de dicho coeficiente se aproxima a uno.

El número de aumentos incrementales es menor que el número de elementos de la lista. Este es el motivo por el que el algoritmo de búsqueda de Grover ejecuta la búsqueda en menos pasos que cualquier algoritmo clásico.

![Diagrama funcional del algoritmo de búsqueda de Grover](~/media/grover.png)

## <a name="write-the-code"></a>Escritura del código

1. Con Quantum Development Kit, [cree un nuevo proyecto de Q#](xref:microsoft.quantum.howto.createproject) denominado `Grover` en el entorno de desarrollo que prefiera.

1. Agregue el siguiente código al archivo `Operations.qs` del proyecto nuevo:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Para definir la lista que estamos buscando, cree un nuevo archivo `Reflections.qs` y péguelo en el siguiente código:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    La operación `ReflectAboutMarked` define la entrada marcada que está buscando: la cadena que alterna ceros y unos. Este ejemplo se integra como parte del código de la entrada marcada y se puede extender a la búsqueda de diferentes entradas o generalizar para cualquier entrada.

1. A continuación, ejecute el programa de Q# para buscar el elemento marcado por `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o la línea de comandos](#tab/tabid-python)

    Para ejecutar el nuevo programa de Q# desde Python, guarde el código siguiente como `host.py`:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    A continuación, puede ejecutar el programa host de Python desde la línea de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o la línea de comandos](#tab/tabid-csharp)

    Para ejecutar el nuevo programa de Q# desde C#, modifique `Driver.cs` para incluir el siguiente código de C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    A continuación, puede ejecutar el programa host de C# desde la línea de comandos:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

    Para ejecutar el nuevo programa de Q# desde C# en Visual Studio, modifique `Driver.cs` para que incluya el código C# siguiente:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Después, presione F5; el programa iniciará la ejecución y se mostrará una nueva ventana con los siguientes resultados: 

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

    Se ha llamado solo cuatro veces a la operación `ReflectAboutMarked`, pero el programa de Q# fue capaz de encontrar la entrada "01010" entre $2^{5} = 32$ entradas posibles.

## <a name="next-steps"></a>Pasos siguientes

Si ha disfrutado de este inicio rápido, eche un vistazo a algunos de los siguientes recursos para obtener más información sobre el uso de Q# para escribir sus propias aplicaciones cuánticas:

- [Volver a la guía Introducción a QDK](xref:microsoft.quantum.welcome)
- Prueba de un [ejemplo](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) más general del algoritmo de búsqueda de Grover
- [Más información sobre la búsqueda de Grover con Quantum Katas](xref:microsoft.quantum.overview.katas)
- Obtenga más información acerca de la [amplificación de la amplitud](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la técnica de computación cuántica que está detrás del algoritmo de búsqueda de Grover.
- [Conceptos de computación cuántica](xref:microsoft.quantum.concepts.intro)
- [Ejemplos de Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
