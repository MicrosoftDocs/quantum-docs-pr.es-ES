---
title: Aprenda a instalar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035307"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b6580-102">Instalación de Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b6580-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b6580-103">Aprenda a instalar Microsoft Quantum Development Kit (QDK), para que pueda dar sus primeros pasos en la programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="b6580-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="b6580-104">Microsoft Quantum Development Kit consta de:</span><span class="sxs-lookup"><span data-stu-id="b6580-104">The QDK consists of:</span></span>

- <span data-ttu-id="b6580-105">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="b6580-105">the Q# programming language</span></span>
- <span data-ttu-id="b6580-106">Un conjunto de bibliotecas que contienen las funcionalidades complejas de Q#</span><span class="sxs-lookup"><span data-stu-id="b6580-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="b6580-107">Una aplicación host (escrita en Python o en un lenguaje .NET) que ejecuta operaciones cuánticas escritas en Q#</span><span class="sxs-lookup"><span data-stu-id="b6580-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="b6580-108">Herramientas para facilitar el desarrollo</span><span class="sxs-lookup"><span data-stu-id="b6580-108">tools to facilitate your development</span></span>

<span data-ttu-id="b6580-109">Según el entorno de desarrollo elegido hay diferentes pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="b6580-110">Elija el entorno en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="b6580-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="b6580-111">Desarrollo con Python</span><span class="sxs-lookup"><span data-stu-id="b6580-111">Develop with Python</span></span>

1. <span data-ttu-id="b6580-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6580-112">Pre-requisites</span></span>

    - <span data-ttu-id="b6580-113">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b6580-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b6580-114">El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="b6580-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b6580-115">SDK de .NET Core 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b6580-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b6580-116">Instale el paquete `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="b6580-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b6580-117">Instalar el paquete `qsharp`</span><span class="sxs-lookup"><span data-stu-id="b6580-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="b6580-118">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b6580-119">Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:</span><span class="sxs-lookup"><span data-stu-id="b6580-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="b6580-120">Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="b6580-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="b6580-121">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="b6580-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="b6580-122">Compruebe el resultado.</span><span class="sxs-lookup"><span data-stu-id="b6580-122">Verify the output.</span></span> <span data-ttu-id="b6580-123">El programa debe generar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="b6580-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="b6580-124">Desarrollo con cuadernos de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b6580-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="b6580-125">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6580-125">Pre-requisites</span></span>

    - <span data-ttu-id="b6580-126">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b6580-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b6580-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b6580-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b6580-128">SDK de .NET Core 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b6580-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b6580-129">Instale el paquete `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="b6580-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b6580-130">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b6580-131">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="b6580-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="b6580-132">Vaya a la dirección URL que aparece en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b6580-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="b6580-133">Por ejemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="b6580-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="b6580-134">Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="b6580-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="b6580-135">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="b6580-135">Run this cell of the notebook:</span></span>

        ![Celda de cuaderno de Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="b6580-137">Debe aparecer `SayHello` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="b6580-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="b6580-138">Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q# y la salida del cuaderno es el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="b6580-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="b6580-139">Desarrollo con C# en Windows mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6580-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="b6580-140">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6580-140">Pre-requisites</span></span>

    - <span data-ttu-id="b6580-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="b6580-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="b6580-142">Instale la extensión de Visual Studio para Q#.</span><span class="sxs-lookup"><span data-stu-id="b6580-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b6580-143">Descargue la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="b6580-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="b6580-144">Agregue la extensión a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6580-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="b6580-145">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b6580-146">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="b6580-146">Create a new Q# application</span></span>

        - <span data-ttu-id="b6580-147">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b6580-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="b6580-148">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b6580-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="b6580-149">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="b6580-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="b6580-150">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b6580-150">Select **Next**</span></span>
        - <span data-ttu-id="b6580-151">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6580-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="b6580-152">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="b6580-152">Select **Create**</span></span>

    - <span data-ttu-id="b6580-153">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="b6580-153">Inspect the project</span></span>

        <span data-ttu-id="b6580-154">Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b6580-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="b6580-155">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b6580-155">Run the application</span></span>

        - <span data-ttu-id="b6580-156">Seleccione **Depurar** -> **Iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="b6580-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b6580-157">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="b6580-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="b6580-158">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="b6580-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="b6580-159">Desarrollo con C# mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b6580-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="b6580-160">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6580-160">Pre-requisites</span></span>

   - [<span data-ttu-id="b6580-161">Código de VS</span><span class="sxs-lookup"><span data-stu-id="b6580-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="b6580-162">SDK de .NET Core 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b6580-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b6580-163">Instale la extensión de VS Code para Quantum.</span><span class="sxs-lookup"><span data-stu-id="b6580-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b6580-164">Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="b6580-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="b6580-165">Instale las plantillas de proyecto de Quantum:</span><span class="sxs-lookup"><span data-stu-id="b6580-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="b6580-166">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="b6580-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b6580-167">Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto)</span><span class="sxs-lookup"><span data-stu-id="b6580-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="b6580-168">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="b6580-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b6580-169">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b6580-170">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="b6580-170">Create a new project:</span></span>

        - <span data-ttu-id="b6580-171">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="b6580-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="b6580-172">Seleccione **Q#: Crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="b6580-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="b6580-173">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6580-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="b6580-174">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6580-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="b6580-175">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b6580-175">Run the application:</span></span>

        - <span data-ttu-id="b6580-176">Vaya a **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="b6580-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b6580-177">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b6580-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="b6580-178">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b6580-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b6580-179">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="b6580-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b6580-180">Desarrollo con C# mediante la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="b6580-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="b6580-181">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6580-181">Pre-requisites</span></span>

    - [<span data-ttu-id="b6580-182">SDK de .NET Core 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b6580-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b6580-183">Instale las plantillas de proyecto de Quantum para .NET.</span><span class="sxs-lookup"><span data-stu-id="b6580-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="b6580-184">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="b6580-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b6580-185">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6580-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b6580-186">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="b6580-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="b6580-187">Vaya al nuevo directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6580-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="b6580-188">Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="b6580-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="b6580-189">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b6580-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="b6580-190">Debería ver la siguiente salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b6580-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="b6580-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b6580-191">What's next?</span></span>

<span data-ttu-id="b6580-192">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="b6580-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
