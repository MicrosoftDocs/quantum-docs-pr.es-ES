---
title: Aprenda a crear un proyecto de preguntas y respuestas con el kit de desarrollo de Quantum (QDK)
description: 'Inicialice un proyecto para el desarrollo de Quantum con QDK y Q # en el entorno de desarrollo que prefiera.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444181"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Creación de un proyecto de Q # en el entorno de desarrollo

Obtenga información sobre cómo crear un proyecto de Q # con el QDK.

Un proyecto de Q # contiene archivos de preguntas y respuestas que contienen código Quantum, así como un programa host para ejecutar el programa Quantum. Puede escribir el programa host en lenguajes .NET como C#, o en Python. También puede ejecutar el código de preguntas y respuestas en un cuaderno de Jupyter Notebook con el kernel de IQ #.

Elija el entorno de desarrollo y el idioma en las secciones siguientes:

* [Python](#create-a-python-project)
* [Jupyter Notebooks](#create-a-jupyter-notebook-project)
* [C#con Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#con VS Code](#create-a-c-project-using-vs-code)
* [C#con la línea de comandos](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Creación de un proyecto de Python

1. Requisitos previos

     * El [Kit de desarrollo de Quantum para Python](xref:microsoft.quantum.install#develop-with-python)

1. Cree una carpeta para el proyecto y vaya a esa carpeta.

1. Cree un archivo de preguntas y respuestas llamado `Operation.qs`y agréguele su código de preguntas y respuestas. Por ejemplo:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Cree un archivo de host de Python llamado `host.py` para llamar a la operación Q #. Por ejemplo:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Ejecute el programa:

    ```bash
    python host.py
    ```

1. Compruebe el resultado. El programa debe generar las siguientes líneas:

    ```bash
    Hello from quantum world!
    0
    ```

Ahora puede continuar desarrollando el programa Quantum.

## <a name="create-a-jupyter-notebook-project"></a>Creación de un proyecto de Jupyter Notebook

1. Requisitos previos

    * El [Kit de desarrollo de Quantum para cuadernos de Jupyter Notebook](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Ejecute el siguiente comando para iniciar el servidor de Notebook:

    ```bash
    jupyter notebook
    ```

1. Vaya a la dirección URL que se muestra en la línea de comandos. Por ejemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Aparece una página Jupyter en el explorador. En la pestaña **archivos** , seleccione **nuevo** > **Q #** para crear un cuaderno de Jupyter Notebook con un kernel de preguntas y respuestas. Agregue el código siguiente a la primera celda del cuaderno:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Seleccione **celda** > **Ejecutar celdas** para ejecutar el Bloc de notas. `SayHello` aparecerán pronto en el resultado de la celda:

    ![Jupyter Notebook Cell with Q # Code](~/media/install-guide-jupyter.png)

    Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q # y el Bloc de notas da como resultado el nombre de las operaciones que encuentra.

1. En una nueva celda, simule la ejecución en un equipo Quantum de la operación que acaba de crear con la `%simulate` mágica:

    ![Celda del cuaderno de Jupyter con% simulación mágica](~/media/install-guide-jupyter-simulate.png)

    Debería ver el mensaje impreso en la pantalla junto con el resultado de la operación invocada (en este caso, vacía).

Ahora puede agregar otras operaciones de Q # para continuar con el desarrollo de Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Creación de C# un proyecto en Windows con Visual Studio

1. Requisitos previos

    * El [Kit de desarrollo de Quantum para Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Creación de una nueva aplicación de Q #

    * Ir al **archivo** -> **nuevo** **proyecto** de -> 
    * Escriba `Q#` en el cuadro de búsqueda
    * Seleccionar **aplicación de Q #**
    * Seleccione **Siguiente**.
    * Elegir un nombre y una ubicación para la aplicación
    * Seleccione **Crear**

1. Inspeccionar el proyecto

    Debería ver que se han creado dos archivos: `Driver.cs`, que es la C# aplicación host; y `Operation.qs`, que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.

1. Ejecución de la aplicación

    * Seleccione **Depurar** -> **iniciar sin depurar**
    * Debería ver el texto `Hello quantum world!` imprimir en una ventana de consola.

Ahora puede continuar con el desarrollo de Quantum con Visual Studio.

> [!NOTE]
> * Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en la solución deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  

## <a name="create-a-c-project-using-vs-code"></a>Crear un C# proyecto mediante vs Code

1. Requisitos previos

    * El [Kit de desarrollo de Quantum para vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Cree un nuevo proyecto:

    * Ir a **vista** -> **paleta de comandos**
    * Seleccione **Q #: crear nuevo proyecto**
    * Vaya a la ubicación en el sistema de archivos donde desea crear la aplicación.
    * Haga clic en el botón **abrir nuevo proyecto...** cuando se haya creado el proyecto.

1. Ejecute la aplicación:

    * Ir a **Depurar** -> **iniciar sin depurar**
    * Debería ver el siguiente texto en la ventana de salida `Hello quantum world!`

Ahora puede continuar con el desarrollo de Quantum mediante Visual Studio Code.

> [!NOTE]
> * Las áreas de trabajo con varias carpetas raíz no se admiten actualmente en la extensión de Visual Studio Code. Si tiene varios proyectos dentro de un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Crear un C# proyecto mediante la herramienta de línea de comandos `dotnet`

1. Requisitos previos

    * El [Kit de desarrollo de Quantum para la línea de comandos](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Creación de una aplicación

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Navegue hasta el nuevo directorio de la aplicación

    ```bash
    cd <project name>
    ```

    Debería ver que se han creado dos archivos, junto con los archivos de proyecto de la aplicación: un archivo de preguntas y respuestas (`Operation.qs`) C# y un archivo de host (`Driver.cs`).

1. Ejecución de la aplicación

    ```bash
    dotnet run
    ```

    Debería ver el siguiente resultado: `Hello quantum world!`

Ahora continúa con el desarrollo de Quantum mediante herramientas de línea de comandos.

## <a name="whats-next"></a>¿Qué es lo próximo?

Ahora que ha creado un proyecto en su entorno preferido, puede continuar con el desarrollo de Quantum.
