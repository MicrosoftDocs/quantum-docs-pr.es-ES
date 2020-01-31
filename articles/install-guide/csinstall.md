---
title: Desarrollo con preguntas y respuestasC#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831025"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="4dcf9-102">Desarrollo con preguntas y respuestasC#</span><span class="sxs-lookup"><span data-stu-id="4dcf9-102">Develop with Q# + C#</span></span>

<span data-ttu-id="4dcf9-103">Instale QDK para desarrollar C# programas host para llamar a las operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="4dcf9-104">Q # se ha creado para experimentar bien con los lenguajes de C#.net, específicamente.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="4dcf9-105">Puede trabajar con este emparejamiento en entornos de desarrollo diferentes:</span><span class="sxs-lookup"><span data-stu-id="4dcf9-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="4dcf9-106">Q # + C# con Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="4dcf9-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="4dcf9-107">P # + C# uso de Visual Studio Code (Windows, Linux y Mac)</span><span class="sxs-lookup"><span data-stu-id="4dcf9-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="4dcf9-108">Q # + C# con la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="4dcf9-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="4dcf9-109">Desarrollo con Q # + C# mediante Visual Studio<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="4dcf9-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="4dcf9-110">Visual Studio ofrece un entorno completo para desarrollar programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="4dcf9-111">La extensión de preguntas y respuestas de Visual Studio contiene plantillas para los proyectos y archivos de preguntas y respuestas, así como el resaltado de sintaxis, la finalización de código y la compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="4dcf9-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4dcf9-112">Pre-requisites</span></span>

    - <span data-ttu-id="4dcf9-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="4dcf9-114">Instale la extensión de Visual Studio para Q#.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4dcf9-115">Descarga e instalación de la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4dcf9-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="4dcf9-116">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4dcf9-117">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="4dcf9-117">Create a new Q# application</span></span>

        - <span data-ttu-id="4dcf9-118">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="4dcf9-119">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="4dcf9-120">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="4dcf9-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="4dcf9-121">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-121">Select **Next**</span></span>
        - <span data-ttu-id="4dcf9-122">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="4dcf9-123">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="4dcf9-123">Select **Create**</span></span>

    - <span data-ttu-id="4dcf9-124">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="4dcf9-124">Inspect the project</span></span>

        <span data-ttu-id="4dcf9-125">Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="4dcf9-126">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4dcf9-126">Run the application</span></span>

        - <span data-ttu-id="4dcf9-127">Seleccione **Depurar** -> **Iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="4dcf9-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4dcf9-128">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="4dcf9-129">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="4dcf9-130">Desarrollo con Q # + C# mediante Visual Studio Code<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="4dcf9-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="4dcf9-131">Visual Studio Code (VS Code) ofrece un entorno completo para desarrollar programas de preguntas y respuestas en Windows, Linux y Mac.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="4dcf9-132">La extensión Q # VS Code incluye compatibilidad con el resaltado de sintaxis Q #, la finalización de código y los fragmentos de código de Q #.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="4dcf9-133">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4dcf9-133">Pre-requisites</span></span>

   - [<span data-ttu-id="4dcf9-134">Código de VS</span><span class="sxs-lookup"><span data-stu-id="4dcf9-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="4dcf9-135">SDK de .NET Core 3,1 o posterior</span><span class="sxs-lookup"><span data-stu-id="4dcf9-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4dcf9-136">Instale la extensión de VS Code para Quantum.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4dcf9-137">Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="4dcf9-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="4dcf9-138">Instale las plantillas de proyecto de Quantum:</span><span class="sxs-lookup"><span data-stu-id="4dcf9-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="4dcf9-139">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4dcf9-140">Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto)</span><span class="sxs-lookup"><span data-stu-id="4dcf9-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="4dcf9-141">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4dcf9-142">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4dcf9-143">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="4dcf9-143">Create a new project:</span></span>

        - <span data-ttu-id="4dcf9-144">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="4dcf9-145">Seleccione **Q#: Crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="4dcf9-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="4dcf9-146">Seleccionar **aplicación de consola independiente**</span><span class="sxs-lookup"><span data-stu-id="4dcf9-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="4dcf9-147">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="4dcf9-148">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="4dcf9-149">Si aún no tiene instalada la C# extensión de vs Code, aparecerá una ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="4dcf9-150">Instale la extensión.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-150">Install the extension.</span></span> 

    - <span data-ttu-id="4dcf9-151">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4dcf9-151">Run the application:</span></span>

        - <span data-ttu-id="4dcf9-152">Ir a **terminal** -> **nuevo terminal**</span><span class="sxs-lookup"><span data-stu-id="4dcf9-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="4dcf9-153">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="4dcf9-154">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="4dcf9-155">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="4dcf9-156">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="4dcf9-157">Desarrollo con Q # + C# mediante la herramienta de línea de comandos `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="4dcf9-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="4dcf9-158">Por supuesto, también puede compilar y ejecutar programas de Q# desde la línea de comandos, simplemente instalando las plantillas de proyecto del SDK de .NET Core y QDK.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="4dcf9-159">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4dcf9-159">Pre-requisites</span></span>

    - [<span data-ttu-id="4dcf9-160">SDK de .NET Core 3,1 o posterior</span><span class="sxs-lookup"><span data-stu-id="4dcf9-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4dcf9-161">Instale las plantillas de proyecto de Quantum para .NET.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="4dcf9-162">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4dcf9-163">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4dcf9-164">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="4dcf9-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="4dcf9-165">Vaya al nuevo directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="4dcf9-166">Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="4dcf9-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="4dcf9-167">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4dcf9-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="4dcf9-168">Debería ver la siguiente salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="4dcf9-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="4dcf9-169">¿Qué sigue?</span><span class="sxs-lookup"><span data-stu-id="4dcf9-169">What's next?</span></span>

<span data-ttu-id="4dcf9-170">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="4dcf9-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
