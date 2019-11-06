---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2a098d89f13278d7137bf182a184a74afb9393be
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462873"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalación de Microsoft Quantum Development Kit (QDK)

Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica. Microsoft Quantum Development Kit consta de:

- El lenguaje de programación Q#
- Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#
- Una aplicación host (escrita en Python o en un lenguaje .NET) que ejecuta operaciones cuánticas escritas en Q#
- Herramientas para facilitar el desarrollo

Según el entorno de desarrollo elegido hay diferentes pasos de instalación. Elija el entorno en las secciones siguientes.

## <a name="develop-with-python"></a>Desarrollo con Python

El paquete qsharp de Python facilita la simulación de operaciones y funciones desde Python. IQ# (pronunciado i-q-sharp) es una extensión usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK de .NET Core 3.0 o posterior](https://www.microsoft.com/net/download)

1. Instalar el paquete `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Instalar el paquete `qsharp`

    ```bash
    pip install qsharp
    ```

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Ejecute el programa:

        ```bash
        python hello_world.py
        ```

    - Compruebe el resultado. El programa debe generar las siguientes líneas:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Desarrollo con cuadernos de Jupyter Notebook

Los cuadernos de Jupyter Notebook son muy apreciados en entornos académicos, laboratorios científicos y programación colaborativa en línea, y ofrecen ejecución de código in-situ (ahora con código Q#), además de instrucciones, notas y otro contenido.  Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.

IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.


1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3.0 o posterior](https://www.microsoft.com/net/download)

1. Instalar el paquete `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Ejecute el siguiente comando para iniciar el servidor de cuadernos:

        ```bash
        jupyter notebook
        ```

    - Vaya a la dirección URL que aparece en la línea de comandos. Por ejemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Ejecute esta celda del cuaderno:

        ![Celda de cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        Debe aparecer `SayHello` en la salida de la celda. Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q# y la salida del cuaderno es el nombre de las operaciones que encuentra.


    - En una nueva celda, simule la ejecución en un equipo cuántico de la operación que acaba de crear con el magic `%simulate`:

        ![Celda de cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Verá el mensaje en pantalla junto con el resultado de la operación invocada (en este caso, vacía).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Desarrollo con C# en Windows mediante Visual Studio

Visual Studio ofrece un entorno completo para desarrollar programas de Q#, con excelentes características como la finalización de código y el resaltado de la sintaxis, que guían al desarrollador durante la creación de sus aplicaciones.  La extensión de Visual Studio para Q# contiene plantillas para los proyectos y archivos de Q#, así como el resaltado de la sintaxis y compatibilidad con IntelliSense.


1. Requisitos previos

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.

1. Instale la extensión de Visual Studio para Q#.

    - Descargue la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Agregue la extensión a Visual Studio.

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Creación de una aplicación de Q#

        - Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.
        - Escriba `Q#` en el cuadro de búsqueda.
        - Seleccione **Q# Application** (Aplicación de Q#)
        - Seleccione **Siguiente**.
        - Elija un nombre y una ubicación para su aplicación.
        - Seleccione **Crear**

    - Inspección del proyecto

        Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.

    - Ejecución de la aplicación

        - Seleccione **Depurar** -> **Iniciar sin depurar**
        - Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.

> [!NOTE]
> * Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  

## <a name="develop-with-c-using-visual-studio-code"></a>Desarrollo con C# en Visual Studio Code

Visual Studio Code (VS Code) ofrece un entorno completo para desarrollar programas de Q# en numerosos entornos informáticos (incluidos Windows Linux y Mac), con excelentes características como la finalización de código y el resaltado de la sintaxis, que guían al desarrollador durante la creación de sus aplicaciones.  La extensión de VS Code para Q# incluye resaltado de la sintaxis y fragmentos de código de Q#.

1. Requisitos previos

   - [Código de VS](https://code.visualstudio.com/download)
   - [SDK de .NET Core 3.0 o posterior](https://www.microsoft.com/net/download)

1. Instale la extensión de VS Code para Quantum.

    - Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Instale las plantillas de proyecto de Quantum:

   - Vaya a **Ver** -> **Paleta de comandos**.
   - Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto)

    Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Cree un nuevo proyecto:

        - Vaya a **Ver** -> **Paleta de comandos**.
        - Seleccione **Q#: Crear nuevo proyecto**
        - Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.
        - Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.

    - Ejecute la aplicación:

        - Vaya a **Depurar** -> **Iniciar sin depurar**.
        - Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.

> [!NOTE]
> * > * No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code. Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Desarrollo con C# mediante la herramienta de línea de comandos `dotnet`

Por supuesto, también puede compilar y ejecutar programas de Q# desde la línea de comandos, simplemente instalando las plantillas de proyecto del SDK de .NET Core y QDK. 

1. Requisitos previos

    - [SDK de .NET Core 3.0 o posterior](https://www.microsoft.com/net/download)

1. Instale las plantillas de proyecto de Quantum para .NET.

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Creación de una aplicación

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Vaya al nuevo directorio de la aplicación.

       ```bash
       cd runSayHello
       ```

    Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).

    - Ejecución de la aplicación

        ```bash
        dotnet run
        ```

        Debería ver la siguiente salida: `Hello quantum world!`.

## <a name="whats-next"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).
