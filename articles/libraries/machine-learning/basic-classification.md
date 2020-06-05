---
title: Clasificación básica con la biblioteca Quantum Machine Learning
description: 'Obtenga información sobre cómo ejecutar un clasificador secuencial Quantum escrito en Q # con la biblioteca Quantum Machine Learning de Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422179"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Clasificación básica: clasificación de datos con QDK

En esta guía de inicio rápido, obtendrá información sobre cómo ejecutar un clasificador secuencial de Quantum escrito en Q # con la biblioteca de Quantum Machine Learning de QDK. 

En esta guía, usaremos el conjunto de caracteres de media luna con una estructura de clasificador definida en Q #.

## <a name="prerequisites"></a>Prerrequisitos

- [Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).
- Cree un proyecto de Q # para un [programa host de Python](xref:microsoft.quantum.install.python) o un [programa host de C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Programa host

El programa host consta de tres partes:

- Cargue el conjunto de DataSet y elija un conjunto de parámetros de inicio para el modelo.
- Ejecute el entrenamiento para determinar los parámetros y la desviación del modelo.
- Validar el modelo para determinar su precisión

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o la línea de comandos](#tab/tabid-python)

    Para ejecutarlo es el clasificador de preguntas y respuestas de Python, guarde el código siguiente como `host.py` . Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    A continuación, puede ejecutar el programa host de Python desde la línea de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o la línea de comandos](#tab/tabid-csharp)

    Para ejecutarlo es el clasificador de preguntas y respuestas de C#, guarde el código siguiente como `Host.cs` . Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    A continuación, puede ejecutar el programa host de C# desde la línea de comandos:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

    Para ejecutar el nuevo programa de preguntas # desde C# en Visual Studio, modifique `Host.cs` para que incluya el siguiente código de c#. Recuerde que también necesita el archivo Q # `Training.qs` que se explica más adelante en este tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Después, presione F5; el programa iniciará la ejecución y se mostrará una nueva ventana con los siguientes resultados: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q ( \# código de clasificador)

Ahora veamos cómo se definen las operaciones invocadas por el programa host en Q #.
Se guarda el código siguiente en un archivo denominado `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Las funciones y operaciones más importantes definidas en el código anterior son:

- `ClassifierStructure() : ControlledRotation[]`: en esta función se establece la estructura de nuestro modelo de circuito agregando las capas de las puertas controladas que se consideran. Este paso es análogo a la declaración de capas de neuronas en un modelo de aprendizaje profundo secuencial.
- `TrainHalfMoonModel() : (Double[], Double)`: esta operación es la parte principal del código y define el entrenamiento. Aquí se cargan los ejemplos del conjunto de DataSet incluido en la biblioteca, se establecen los parámetros de hiperparámetros y los parámetros iniciales para el entrenamiento y se inicia el entrenamiento mediante una llamada a la operación `TrainSequentialClassifier` incluida en la biblioteca. Genera los parámetros y la diferencia que determinan el clasificador.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: esta operación define el proceso de validación para evaluar el modelo. Aquí se cargan los ejemplos de validación, el número de medidas por muestra y la tolerancia. Genera el número de clasificaciones incorrectas en el lote elegido de ejemplos para la validación.

## <a name="next-steps"></a>Pasos siguientes

En primer lugar, puede reproducirse con el código e intentar cambiar algunos parámetros para ver cómo afecta al entrenamiento. A continuación, en el siguiente tutorial, [Diseñe su propio clasificador](xref:microsoft.quantum.libraries.machine-learning.design), aprenderá a definir la estructura del clasificador.
