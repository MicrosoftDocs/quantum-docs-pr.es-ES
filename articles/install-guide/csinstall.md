---
title: Desarrollo con preguntas y respuestasC#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036294"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="a3725-102">Desarrollo con preguntas y respuestasC#</span><span class="sxs-lookup"><span data-stu-id="a3725-102">Develop with Q# + C#</span></span>

<span data-ttu-id="a3725-103">Instale QDK para desarrollar C# programas host para llamar a las operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="a3725-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="a3725-104">Q # se ha creado para experimentar bien con los lenguajes de C#.net, específicamente.</span><span class="sxs-lookup"><span data-stu-id="a3725-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="a3725-105">Puede trabajar con este emparejamiento en entornos de desarrollo diferentes:</span><span class="sxs-lookup"><span data-stu-id="a3725-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="a3725-106">Q # + C# con Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="a3725-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="a3725-107">P # + C# uso de Visual Studio Code (Windows, Linux y Mac)</span><span class="sxs-lookup"><span data-stu-id="a3725-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="a3725-108">Q # + C# con la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="a3725-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="a3725-109">Desarrollo con Q # + C# mediante Visual Studio <a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="a3725-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="a3725-110">Visual Studio ofrece un entorno completo para desarrollar programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="a3725-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="a3725-111">La extensión de preguntas y respuestas de Visual Studio contiene plantillas para los proyectos y archivos de preguntas y respuestas, así como el resaltado de sintaxis, la finalización de código y la compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a3725-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="a3725-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a3725-112">Pre-requisites</span></span>

    - <span data-ttu-id="a3725-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="a3725-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="a3725-114">Instale la extensión de Visual Studio para Q#.</span><span class="sxs-lookup"><span data-stu-id="a3725-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="a3725-115">Descarga e instalación de la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="a3725-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="a3725-116">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a3725-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="a3725-117">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="a3725-117">Create a new Q# application</span></span>

        - <span data-ttu-id="a3725-118">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a3725-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="a3725-119">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a3725-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="a3725-120">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="a3725-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="a3725-121">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a3725-121">Select **Next**</span></span>
        - <span data-ttu-id="a3725-122">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3725-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="a3725-123">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="a3725-123">Select **Create**</span></span>

    - <span data-ttu-id="a3725-124">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="a3725-124">Inspect the project</span></span>

        <span data-ttu-id="a3725-125">Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="a3725-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="a3725-126">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a3725-126">Run the application</span></span>

        - <span data-ttu-id="a3725-127">Seleccione **Depurar** -> **Iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="a3725-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="a3725-128">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="a3725-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="a3725-129">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="a3725-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="a3725-130">Desarrollo con Q # + C# mediante Visual Studio Code <a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="a3725-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="a3725-131">Visual Studio Code (VS Code) ofrece un entorno completo para desarrollar programas de preguntas y respuestas en Windows, Linux y Mac.</span><span class="sxs-lookup"><span data-stu-id="a3725-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="a3725-132">La extensión Q # VS Code incluye compatibilidad con el resaltado de sintaxis Q #, la finalización de código y los fragmentos de código de Q #.</span><span class="sxs-lookup"><span data-stu-id="a3725-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="a3725-133">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a3725-133">Pre-requisites</span></span>

   - [<span data-ttu-id="a3725-134">Código de VS</span><span class="sxs-lookup"><span data-stu-id="a3725-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="a3725-135">SDK de .NET Core 3,1 o posterior</span><span class="sxs-lookup"><span data-stu-id="a3725-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="a3725-136">Instale la extensión de VS Code para Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3725-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="a3725-137">Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="a3725-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="a3725-138">Instale las plantillas de proyecto de Quantum:</span><span class="sxs-lookup"><span data-stu-id="a3725-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="a3725-139">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="a3725-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="a3725-140">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="a3725-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="a3725-141">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a3725-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="a3725-142">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a3725-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="a3725-143">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="a3725-143">Create a new project:</span></span>

        - <span data-ttu-id="a3725-144">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="a3725-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="a3725-145">Seleccione **Q #: crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="a3725-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="a3725-146">Seleccionar **aplicación de consola independiente**</span><span class="sxs-lookup"><span data-stu-id="a3725-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="a3725-147">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3725-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="a3725-148">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a3725-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="a3725-149">Si aún no tiene instalada la C# extensión de vs Code, aparecerá una ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="a3725-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="a3725-150">Instale la extensión.</span><span class="sxs-lookup"><span data-stu-id="a3725-150">Install the extension.</span></span> 

    - <span data-ttu-id="a3725-151">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a3725-151">Run the application:</span></span>

        - <span data-ttu-id="a3725-152">Ir a **terminal** -> **nuevo terminal**</span><span class="sxs-lookup"><span data-stu-id="a3725-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="a3725-153">escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a3725-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="a3725-154">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="a3725-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="a3725-155">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a3725-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="a3725-156">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="a3725-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="a3725-157">Desarrollo con Q # + C# mediante la herramienta de línea de comandos `dotnet` <a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="a3725-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="a3725-158">Por supuesto, también puede compilar y ejecutar programas de Q# desde la línea de comandos, simplemente instalando las plantillas de proyecto del SDK de .NET Core y QDK.</span><span class="sxs-lookup"><span data-stu-id="a3725-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="a3725-159">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a3725-159">Pre-requisites</span></span>

    - [<span data-ttu-id="a3725-160">SDK de .NET Core 3,1 o posterior</span><span class="sxs-lookup"><span data-stu-id="a3725-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="a3725-161">Instale las plantillas de proyecto de Quantum para .NET.</span><span class="sxs-lookup"><span data-stu-id="a3725-161">Install the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="a3725-162">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a3725-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="a3725-163">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a3725-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="a3725-164">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a3725-164">Create a new application</span></span>

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - <span data-ttu-id="a3725-165">Vaya al nuevo directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3725-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="a3725-166">Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="a3725-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="a3725-167">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a3725-167">Run the application</span></span>

        ```dotnetcli
        dotnet run
        ```

        <span data-ttu-id="a3725-168">Debería ver la siguiente salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="a3725-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="a3725-169">¿Qué sigue?</span><span class="sxs-lookup"><span data-stu-id="a3725-169">What's next?</span></span>

<span data-ttu-id="a3725-170">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="a3725-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
