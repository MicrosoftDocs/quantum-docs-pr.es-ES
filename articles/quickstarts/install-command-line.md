---
title: Desarrollo con aplicaciones de línea de comandos de Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871440"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="c69a5-102">Desarrollo con aplicaciones de línea de comandos de Q#</span><span class="sxs-lookup"><span data-stu-id="c69a5-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="c69a5-103">Los programas de Q# se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C# , F# o Python.</span><span class="sxs-lookup"><span data-stu-id="c69a5-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c69a5-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c69a5-104">Prerequisites</span></span>

- [<span data-ttu-id="c69a5-105">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="c69a5-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="c69a5-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="c69a5-106">Installation</span></span>

<span data-ttu-id="c69a5-107">Aunque puede crear aplicaciones de línea de comandos de Q# en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para desarrollar aplicaciones de Q# en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="c69a5-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="c69a5-108">Para desarrollar en la nube mediante un explorador web, se recomienda utilizar Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="c69a5-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="c69a5-109">Estos entornos de desarrollo incluyen la funcionalidad enriquecida de la extensión QDK, como advertencias, resaltado de sintaxis o plantillas de proyecto, entre otras.</span><span class="sxs-lookup"><span data-stu-id="c69a5-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="c69a5-110">Para configurar VS Code:</span><span class="sxs-lookup"><span data-stu-id="c69a5-110">To configure VS Code:</span></span>

1. <span data-ttu-id="c69a5-111">Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="c69a5-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="c69a5-112">Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="c69a5-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="c69a5-113">Para configurar Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="c69a5-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="c69a5-114">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="c69a5-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="c69a5-115">Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="c69a5-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="c69a5-116">Para configurar Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="c69a5-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="c69a5-117">Cree una [cuenta de Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="c69a5-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="c69a5-118">Cree un entorno de Codespaces.</span><span class="sxs-lookup"><span data-stu-id="c69a5-118">Create a Codespaces environment.</span></span> <span data-ttu-id="c69a5-119">Consulte la [guía de inicio rápido](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="c69a5-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="c69a5-120">Al crear el entorno de Codespace, se recomienda especificar `microsoft/Quantum` en el campo "Git Repository" (Repositorio Git) para cargar la configuración específica del QDK.</span><span class="sxs-lookup"><span data-stu-id="c69a5-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="c69a5-121">Ahora puede iniciar el nuevo entorno y empezar a desarrollar en el explorador mediante el [IDE en la nube de VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="c69a5-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="c69a5-122">También se puede usar la instalación local de VS Code y usar Codespaces como un [entorno remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="c69a5-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="c69a5-123">Para instalar el QDK para otro entorno, escriba en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="c69a5-123">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="c69a5-124">Desarrollo con Q#</span><span class="sxs-lookup"><span data-stu-id="c69a5-124">Develop with Q#</span></span>

<span data-ttu-id="c69a5-125">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno.</span><span class="sxs-lookup"><span data-stu-id="c69a5-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="c69a5-126">Código de VS</span><span class="sxs-lookup"><span data-stu-id="c69a5-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c69a5-127">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="c69a5-127">To create a new project:</span></span>

1. <span data-ttu-id="c69a5-128">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="c69a5-129">Haga clic en **Aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="c69a5-130">Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="c69a5-131">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c69a5-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="c69a5-132">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c69a5-132">Inspect the project.</span></span> <span data-ttu-id="c69a5-133">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="c69a5-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c69a5-134">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c69a5-134">To run the application:</span></span>
1. <span data-ttu-id="c69a5-135">Haga clic en **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="c69a5-136">En el símbolo del sistema del terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c69a5-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="c69a5-137">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="c69a5-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="c69a5-138">Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión Q# para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c69a5-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="c69a5-139">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="c69a5-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="c69a5-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c69a5-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="c69a5-141">Cree una aplicación de Q# `Hello World` para comprobar la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c69a5-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="c69a5-142">Para crear una aplicación de Q#:</span><span class="sxs-lookup"><span data-stu-id="c69a5-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="c69a5-143">Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="c69a5-144">Escriba `Q#` en el cuadro de búsqueda, seleccione **Aplicación de Q#** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="c69a5-145">Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="c69a5-146">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c69a5-146">Inspect the project.</span></span> <span data-ttu-id="c69a5-147">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="c69a5-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c69a5-148">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c69a5-148">To run the application:</span></span>
1. <span data-ttu-id="c69a5-149">Seleccione **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="c69a5-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="c69a5-150">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="c69a5-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="c69a5-151">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="c69a5-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="c69a5-152">Otros editores con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c69a5-152">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="c69a5-153">Cree una aplicación `Hello World` de Q# para comprobar su instalación.</span><span class="sxs-lookup"><span data-stu-id="c69a5-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="c69a5-154">Instale las plantillas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c69a5-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="c69a5-155">Cree una aplicación:</span><span class="sxs-lookup"><span data-stu-id="c69a5-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="c69a5-156">Vaya al directorio de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c69a5-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="c69a5-157">El directorio contendrá un archivo `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="c69a5-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="c69a5-158">Puede modificar esta plantilla con un editor de texto y sobrescribirla con sus propias aplicaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="c69a5-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="c69a5-159">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="c69a5-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="c69a5-160">Verá el siguiente texto impreso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c69a5-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="c69a5-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c69a5-161">Next steps</span></span>

<span data-ttu-id="c69a5-162">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="c69a5-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
