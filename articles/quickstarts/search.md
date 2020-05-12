---
title: 'Ejecución del algoritmo de búsqueda de Grover en Q#: Quantum Development Kit'
description: Compile un proyecto de Q# que demuestre el algoritmo de Grover, uno de los algoritmos cuánticos clásicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686826"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Inicio rápido: Implementación del algoritmo de búsqueda de Grover en Q\#

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

1. Agregue el siguiente código al archivo `Program.qs` del proyecto nuevo:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Para definir la lista que estamos buscando, cree un nuevo archivo `Reflections.qs` y péguelo en el siguiente código:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    La operación `ReflectAboutMarked` define la entrada marcada que está buscando: la cadena que alterna ceros y unos. Este ejemplo se integra como parte del código de la entrada marcada y se puede extender a la búsqueda de diferentes entradas o generalizar para cualquier entrada.

1. A continuación, ejecute el programa de Q# para buscar el elemento marcado por `ReflectAboutMarked`.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Aplicaciones de línea de comandos de Q# con Visual Studio o Visual Studio Code

El ejecutable ejecutará la operación o función marcada con el atributo `@EntryPoint()` en un simulador o una calculadora de recursos, dependiendo de la configuración del proyecto y de las opciones de la línea de comandos.

En Visual Studio, solo tiene que presionar Ctrl+F5 para ejecutar el script.

En VS Code, escriba lo siguiente en el terminal para compilar `Program.qs` la primera vez:

```Command line
dotnet build
```

En las ejecuciones posteriores, no es necesario volver a compilarlo. Para ejecutarlo, escriba el siguiente comando y presione Entrar:

```Command line
dotnet run --no-build
```

Verá el mensaje siguiente en el terminal:

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

Esto se debe a que no especificó el número de cúbits que quería usar, por lo que el terminal le indica los comandos que hay disponibles para el ejecutable. Si queremos usar 5 cúbits, debemos escribir:

```Command line
dotnet run --n-qubits 5
```

Presione Entrar y verá la siguiente salida:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Pasos siguientes

Si ha disfrutado de este inicio rápido, eche un vistazo a algunos de los siguientes recursos para obtener más información sobre el uso de Q# para escribir sus propias aplicaciones cuánticas:

- [Volver a la guía Introducción a QDK](xref:microsoft.quantum.welcome)
- Prueba de un [ejemplo](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) más general del algoritmo de búsqueda de Grover
- [Más información sobre la búsqueda de Grover con Quantum Katas](xref:microsoft.quantum.overview.katas)
- Obtenga más información acerca de la [amplificación de la amplitud][amplitude-amplification], la técnica de computación cuántica que está detrás del algoritmo de búsqueda de Grover.
- [Conceptos de computación cuántica](xref:microsoft.quantum.concepts.intro)
- [Ejemplos de Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
