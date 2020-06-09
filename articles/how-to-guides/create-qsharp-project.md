---
title: Aprenda a crear un proyecto de preguntas y respuestas con el kit de desarrollo de Quantum (QDK)
description: 'Inicialice un proyecto para el desarrollo de Quantum con QDK y Q # en el entorno de desarrollo que prefiera.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578218"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="5296a-103">Creación de un proyecto de Q # en el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="5296a-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="5296a-104">Obtenga información sobre cómo crear un proyecto de Q # con el QDK.</span><span class="sxs-lookup"><span data-stu-id="5296a-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="5296a-105">Un proyecto de Q # contiene archivos de preguntas y respuestas que contienen código Quantum, así como un programa host para ejecutar el programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="5296a-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="5296a-106">Puede escribir el programa host en lenguajes .NET como C# o en Python.</span><span class="sxs-lookup"><span data-stu-id="5296a-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="5296a-107">También puede ejecutar el código de preguntas y respuestas en un Jupyter Notebook mediante el kernel de IQ #.</span><span class="sxs-lookup"><span data-stu-id="5296a-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="5296a-108">Elija el entorno de desarrollo y el idioma en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5296a-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="5296a-109">Python</span><span class="sxs-lookup"><span data-stu-id="5296a-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="5296a-110">Cuadernos de Jupyter Notebook de Q#</span><span class="sxs-lookup"><span data-stu-id="5296a-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="5296a-111">C# con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5296a-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="5296a-112">C# con VS Code</span><span class="sxs-lookup"><span data-stu-id="5296a-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="5296a-113">C# con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5296a-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="5296a-114">Creación de un proyecto de Python</span><span class="sxs-lookup"><span data-stu-id="5296a-114">Create a Python project</span></span>

1. <span data-ttu-id="5296a-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5296a-115">Pre-requisites</span></span>

     * <span data-ttu-id="5296a-116">Instalación del [Kit de desarrollo de Quantum para Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="5296a-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="5296a-117">Cree una carpeta para el proyecto y vaya a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="5296a-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="5296a-118">Cree un archivo de preguntas y respuestas denominado `Operation.qs` y agréguele su código de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="5296a-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="5296a-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5296a-119">For example:</span></span>

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

1. <span data-ttu-id="5296a-120">Cree un archivo de host de Python llamado `host.py` para llamar a la operación Q #.</span><span class="sxs-lookup"><span data-stu-id="5296a-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="5296a-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5296a-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="5296a-122">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="5296a-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="5296a-123">Compruebe el resultado.</span><span class="sxs-lookup"><span data-stu-id="5296a-123">Verify the output.</span></span> <span data-ttu-id="5296a-124">El programa debe generar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="5296a-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="5296a-125">Ahora puede continuar desarrollando el programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="5296a-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="5296a-126">Creación de un proyecto de Jupyter Notebook de preguntas #</span><span class="sxs-lookup"><span data-stu-id="5296a-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="5296a-127">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5296a-127">Pre-requisites</span></span>

    * <span data-ttu-id="5296a-128">Instalación del [Kit de desarrollo de Quantum para cuadernos de Jupyter Notebook](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="5296a-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="5296a-129">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="5296a-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="5296a-130">Vaya a la dirección URL que aparece en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5296a-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="5296a-131">Por ejemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="5296a-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="5296a-132">Aparece una página Jupyter en el explorador.</span><span class="sxs-lookup"><span data-stu-id="5296a-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="5296a-133">En la pestaña **archivos** , seleccione **nuevo**  >  **q #** para crear un Jupyter Notebook con un kernel de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="5296a-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="5296a-134">Agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="5296a-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="5296a-135">Seleccione **celda**  >  **Ejecutar celdas** para ejecutar el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="5296a-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="5296a-136">`SayHello`aparecerá pronto en el resultado de la celda:</span><span class="sxs-lookup"><span data-stu-id="5296a-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter Notebook celda con código de Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="5296a-138">Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q # y el Bloc de notas da como resultado el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="5296a-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="5296a-139">En una nueva celda, simule la ejecución en un equipo cuántico de la operación que acaba de crear con el magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="5296a-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter Notebook celda con% de simulación mágica](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="5296a-141">Verá el mensaje en pantalla junto con el resultado de la operación invocada (en este caso, vacía).</span><span class="sxs-lookup"><span data-stu-id="5296a-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="5296a-142">Ahora puede agregar otras operaciones de Q # para continuar con el desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="5296a-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="5296a-143">Creación de un proyecto de C# en Windows con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5296a-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="5296a-144">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5296a-144">Pre-requisites</span></span>

    * <span data-ttu-id="5296a-145">Instalación [de la extensión de Quantum Development Kit para Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="5296a-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="5296a-146">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="5296a-146">Create a new Q# application</span></span>

    * <span data-ttu-id="5296a-147">Ir a **archivo**  ->  **nuevo**  ->  **proyecto**</span><span class="sxs-lookup"><span data-stu-id="5296a-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="5296a-148">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5296a-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="5296a-149">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="5296a-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="5296a-150">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5296a-150">Select **Next**</span></span>
    * <span data-ttu-id="5296a-151">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5296a-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="5296a-152">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="5296a-152">Select **Create**</span></span>

1. <span data-ttu-id="5296a-153">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="5296a-153">Inspect the project</span></span>

    <span data-ttu-id="5296a-154">Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="5296a-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="5296a-155">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5296a-155">Run the application</span></span>

    * <span data-ttu-id="5296a-156">Seleccione **depurar**  ->  **iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="5296a-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="5296a-157">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="5296a-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="5296a-158">Ahora puede continuar con el desarrollo de Quantum con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5296a-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="5296a-159">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="5296a-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="5296a-160">Cree un proyecto de C# mediante VS Code</span><span class="sxs-lookup"><span data-stu-id="5296a-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="5296a-161">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5296a-161">Pre-requisites</span></span>

    * <span data-ttu-id="5296a-162">Instalación [de la extensión de Quantum Development Kit para vs Code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="5296a-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="5296a-163">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="5296a-163">Create a new project:</span></span>

    * <span data-ttu-id="5296a-164">Ir a **Ver**  ->  **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="5296a-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="5296a-165">Seleccione **Q #: crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="5296a-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="5296a-166">Seleccionar **aplicación de consola independiente**</span><span class="sxs-lookup"><span data-stu-id="5296a-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="5296a-167">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5296a-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="5296a-168">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5296a-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="5296a-169">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="5296a-169">Run the application:</span></span>

    * <span data-ttu-id="5296a-170">Ir a **terminal**  ->  **New** terminal</span><span class="sxs-lookup"><span data-stu-id="5296a-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="5296a-171">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="5296a-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="5296a-172">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="5296a-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="5296a-173">Ahora puede continuar con el desarrollo de Quantum mediante Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5296a-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="5296a-174">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5296a-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="5296a-175">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="5296a-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5296a-176">Crear un proyecto de C# mediante la `dotnet` herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5296a-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="5296a-177">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5296a-177">Pre-requisites</span></span>

    * <span data-ttu-id="5296a-178">Instalación del [Kit de desarrollo de Quantum para la línea de comandos](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="5296a-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="5296a-179">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="5296a-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="5296a-180">Vaya al nuevo directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5296a-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="5296a-181">Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="5296a-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="5296a-182">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5296a-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="5296a-183">Debería ver la siguiente salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="5296a-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="5296a-184">Ahora continúa con el desarrollo de Quantum mediante herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5296a-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5296a-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5296a-185">Next steps</span></span>

<span data-ttu-id="5296a-186">Ahora que ha creado un proyecto en su entorno preferido, puede continuar con el desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="5296a-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
