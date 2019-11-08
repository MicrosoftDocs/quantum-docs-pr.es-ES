---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799164"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0c56f-102">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="0c56f-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0c56f-103">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="0c56f-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="0c56f-104">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="0c56f-104">The QDK consists of:</span></span>

- <span data-ttu-id="0c56f-105">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="0c56f-105">the Q# programming language</span></span>
- <span data-ttu-id="0c56f-106">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="0c56f-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="0c56f-107">Una aplicación host (escrita en Python o en un lenguaje .NET) que ejecuta operaciones cuánticas escritas en Q#</span><span class="sxs-lookup"><span data-stu-id="0c56f-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="0c56f-108">Herramientas para facilitar el desarrollo</span><span class="sxs-lookup"><span data-stu-id="0c56f-108">tools to facilitate your development</span></span>

<span data-ttu-id="0c56f-109">Según el entorno de desarrollo elegido hay diferentes pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="0c56f-110">Elija el entorno en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0c56f-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="0c56f-111">Desarrollo con Python</span><span class="sxs-lookup"><span data-stu-id="0c56f-111">Develop with Python</span></span>

<span data-ttu-id="0c56f-112">El paquete qsharp de Python facilita la simulación de operaciones y funciones desde Python.</span><span class="sxs-lookup"><span data-stu-id="0c56f-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="0c56f-113">IQ# (pronunciado i-q-sharp) es una extensión usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="0c56f-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="0c56f-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c56f-114">Pre-requisites</span></span>

    - <span data-ttu-id="0c56f-115">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0c56f-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="0c56f-116">El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="0c56f-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="0c56f-117">SDK de .NET Core 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="0c56f-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="0c56f-118">Instalar el paquete `qsharp`</span><span class="sxs-lookup"><span data-stu-id="0c56f-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="0c56f-119">Instalar el paquete `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0c56f-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="0c56f-120">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c56f-121">Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:</span><span class="sxs-lookup"><span data-stu-id="0c56f-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="0c56f-122">Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="0c56f-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="0c56f-123">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="0c56f-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="0c56f-124">Compruebe el resultado.</span><span class="sxs-lookup"><span data-stu-id="0c56f-124">Verify the output.</span></span> <span data-ttu-id="0c56f-125">El programa debe generar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="0c56f-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="0c56f-126">Desarrollo con cuadernos de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="0c56f-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="0c56f-127">Los cuadernos de Jupyter Notebook son muy apreciados en entornos académicos, laboratorios científicos y programación colaborativa en línea, y ofrecen ejecución de código in-situ (ahora con código Q#), además de instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="0c56f-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="0c56f-128">Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.</span><span class="sxs-lookup"><span data-stu-id="0c56f-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="0c56f-129">IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="0c56f-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="0c56f-130">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c56f-130">Pre-requisites</span></span>

    - <span data-ttu-id="0c56f-131">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0c56f-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="0c56f-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="0c56f-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="0c56f-133">SDK de .NET Core 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="0c56f-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="0c56f-134">Instalar el paquete `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0c56f-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="0c56f-135">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c56f-136">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="0c56f-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="0c56f-137">Vaya a la dirección URL que aparece en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0c56f-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="0c56f-138">Por ejemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="0c56f-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="0c56f-139">Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="0c56f-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="0c56f-140">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="0c56f-140">Run this cell of the notebook:</span></span>

        ![Celda de cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="0c56f-142">Debe aparecer `SayHello` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="0c56f-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="0c56f-143">Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q# y la salida del cuaderno es el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="0c56f-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="0c56f-144">En una nueva celda, simule la ejecución en un equipo cuántico de la operación que acaba de crear con el magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="0c56f-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Celda de cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="0c56f-146">Verá el mensaje en pantalla junto con el resultado de la operación invocada (en este caso, vacía).</span><span class="sxs-lookup"><span data-stu-id="0c56f-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="0c56f-147">Desarrollo con C# en Windows mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c56f-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="0c56f-148">Visual Studio ofrece un entorno completo para desarrollar programas de Q#, con excelentes características como la finalización de código y el resaltado de la sintaxis, que guían al desarrollador durante la creación de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0c56f-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="0c56f-149">La extensión de Visual Studio para Q# contiene plantillas para los proyectos y archivos de Q#, así como el resaltado de la sintaxis y compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0c56f-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="0c56f-150">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c56f-150">Pre-requisites</span></span>

    - <span data-ttu-id="0c56f-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="0c56f-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="0c56f-152">Instale la extensión de Visual Studio para Q#.</span><span class="sxs-lookup"><span data-stu-id="0c56f-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="0c56f-153">Descargue la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="0c56f-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="0c56f-154">Agregue la extensión a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c56f-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="0c56f-155">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c56f-156">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="0c56f-156">Create a new Q# application</span></span>

        - <span data-ttu-id="0c56f-157">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0c56f-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="0c56f-158">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0c56f-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="0c56f-159">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="0c56f-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="0c56f-160">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c56f-160">Select **Next**</span></span>
        - <span data-ttu-id="0c56f-161">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="0c56f-162">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="0c56f-162">Select **Create**</span></span>

    - <span data-ttu-id="0c56f-163">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="0c56f-163">Inspect the project</span></span>

        <span data-ttu-id="0c56f-164">Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="0c56f-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="0c56f-165">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0c56f-165">Run the application</span></span>

        - <span data-ttu-id="0c56f-166">Seleccione **Depurar** -> **Iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="0c56f-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="0c56f-167">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="0c56f-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="0c56f-168">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0c56f-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="0c56f-169">Desarrollo con C# en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c56f-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="0c56f-170">Visual Studio Code (VS Code) ofrece un entorno completo para desarrollar programas de Q# en numerosos entornos informáticos (incluidos Windows Linux y Mac), con excelentes características como la finalización de código y el resaltado de la sintaxis, que guían al desarrollador durante la creación de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0c56f-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="0c56f-171">La extensión de VS Code para Q# incluye resaltado de la sintaxis y fragmentos de código de Q#.</span><span class="sxs-lookup"><span data-stu-id="0c56f-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="0c56f-172">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c56f-172">Pre-requisites</span></span>

   - [<span data-ttu-id="0c56f-173">Código de VS</span><span class="sxs-lookup"><span data-stu-id="0c56f-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="0c56f-174">SDK de .NET Core 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="0c56f-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="0c56f-175">Instale la extensión de VS Code para Quantum.</span><span class="sxs-lookup"><span data-stu-id="0c56f-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="0c56f-176">Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="0c56f-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="0c56f-177">Instale las plantillas de proyecto de Quantum:</span><span class="sxs-lookup"><span data-stu-id="0c56f-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="0c56f-178">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="0c56f-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="0c56f-179">Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto)</span><span class="sxs-lookup"><span data-stu-id="0c56f-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="0c56f-180">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0c56f-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="0c56f-181">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c56f-182">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="0c56f-182">Create a new project:</span></span>

        - <span data-ttu-id="0c56f-183">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="0c56f-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="0c56f-184">Seleccione **Q#: Crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="0c56f-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="0c56f-185">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="0c56f-186">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c56f-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="0c56f-187">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0c56f-187">Run the application:</span></span>

        - <span data-ttu-id="0c56f-188">Vaya a **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="0c56f-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="0c56f-189">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="0c56f-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="0c56f-190">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="0c56f-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="0c56f-191">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="0c56f-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="0c56f-192">Desarrollo con C# mediante la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="0c56f-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="0c56f-193">Por supuesto, también puede compilar y ejecutar programas de Q# desde la línea de comandos, simplemente instalando las plantillas de proyecto del SDK de .NET Core y QDK.</span><span class="sxs-lookup"><span data-stu-id="0c56f-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="0c56f-194">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c56f-194">Pre-requisites</span></span>

    - [<span data-ttu-id="0c56f-195">SDK de .NET Core 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="0c56f-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="0c56f-196">Instale las plantillas de proyecto de Quantum para .NET.</span><span class="sxs-lookup"><span data-stu-id="0c56f-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="0c56f-197">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0c56f-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="0c56f-198">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c56f-199">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="0c56f-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="0c56f-200">Vaya al nuevo directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c56f-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="0c56f-201">Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="0c56f-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="0c56f-202">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0c56f-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="0c56f-203">Debería ver la siguiente salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="0c56f-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="0c56f-204">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0c56f-204">What's next?</span></span>

<span data-ttu-id="0c56f-205">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="0c56f-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
