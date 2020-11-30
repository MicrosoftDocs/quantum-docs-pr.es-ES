---
title: Desarrollo con aplicaciones de Q# en un IDE
description: Obtenga información sobre cómo crear una aplicación de Q# que se ejecute desde el símbolo del sistema.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeb567dedc1b8123b32faf7ed3a42bb51f16a7d2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228736"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="b8d5f-103">Desarrollo con aplicaciones de Q# en un IDE</span><span class="sxs-lookup"><span data-stu-id="b8d5f-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="b8d5f-104">Los programas de Q# se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C#, F# o Python.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="b8d5f-105">Puede desarrollar aplicaciones de Q# en Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces o con cualquier editor o IDE, y ejecutar las aplicaciones desde la consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="b8d5f-106">Requisitos previos de todos los entornos</span><span class="sxs-lookup"><span data-stu-id="b8d5f-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="b8d5f-107">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b8d5f-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="b8d5f-108">Instalación</span><span class="sxs-lookup"><span data-stu-id="b8d5f-108">Installation</span></span>

<span data-ttu-id="b8d5f-109">Aunque puede crear aplicaciones de Q# en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para desarrollar aplicaciones de Q# en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="b8d5f-110">Para desarrollar en la nube mediante un explorador web, se recomienda utilizar Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="b8d5f-111">Estos entornos de desarrollo aprovechan la funcionalidad enriquecida de la extensión QDK, como las advertencias, el resaltado de sintaxis o las plantillas de proyecto, entre otras.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="b8d5f-112">Configuración para VS Code:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="b8d5f-113">Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="b8d5f-114">Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="b8d5f-115">Configuración para Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="b8d5f-116">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="b8d5f-117">Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="b8d5f-118">Configuración para otros entornos:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="b8d5f-119">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="b8d5f-120">Configuración para Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="b8d5f-121">Cree una [cuenta de Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="b8d5f-122">Cree un entorno de Codespaces.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-122">Create a Codespaces environment.</span></span> <span data-ttu-id="b8d5f-123">Consulte la [guía de inicio rápido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="b8d5f-124">Al crear el entorno de Codespace, se recomienda especificar `microsoft/Quantum` en el campo "Git Repository" (Repositorio Git) para cargar la configuración específica del QDK.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="b8d5f-125">Ahora puede iniciar el nuevo entorno y empezar a desarrollar en el explorador mediante el [IDE en la nube de VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="b8d5f-126">También se puede usar la instalación local de VS Code y usar Codespaces como un [entorno remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="b8d5f-127">Desarrollo con Q#</span><span class="sxs-lookup"><span data-stu-id="b8d5f-127">Develop with Q#</span></span>

<span data-ttu-id="b8d5f-128">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="b8d5f-129">Código de VS</span><span class="sxs-lookup"><span data-stu-id="b8d5f-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="b8d5f-130">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-130">To create a new project:</span></span>

1. <span data-ttu-id="b8d5f-131">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="b8d5f-132">Haga clic en **Aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="b8d5f-133">Vaya a la ubicación para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="b8d5f-134">Escriba el nombre del proyecto y haga clic en **Create project** (Crear proyecto).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="b8d5f-135">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="b8d5f-136">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-136">Inspect the project.</span></span> <span data-ttu-id="b8d5f-137">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b8d5f-138">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-138">To run the application:</span></span>

1. <span data-ttu-id="b8d5f-139">Haga clic en **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="b8d5f-140">En el símbolo del sistema del terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="b8d5f-141">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="b8d5f-142">Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión Q# para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="b8d5f-143">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="b8d5f-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8d5f-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="b8d5f-145">Cree una aplicación de Q# `Hello World` para comprobar la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="b8d5f-146">Para crear una aplicación nueva de Q#:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="b8d5f-147">Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="b8d5f-148">Escriba `Q#` en el cuadro de búsqueda, seleccione **Aplicación de Q#** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="b8d5f-149">Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="b8d5f-150">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-150">Inspect the project.</span></span> <span data-ttu-id="b8d5f-151">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b8d5f-152">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-152">To run the application:</span></span>

1. <span data-ttu-id="b8d5f-153">Seleccione **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="b8d5f-154">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="b8d5f-155">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="b8d5f-156">Otros editores con el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="b8d5f-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b8d5f-157">Cree una aplicación de Q# `Hello World` para comprobar su instalación.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="b8d5f-158">Cree una aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="b8d5f-159">Vaya al directorio de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="b8d5f-160">El directorio contendrá un archivo `Program.qs`, que es un programa de Q#que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="b8d5f-161">Puede modificar esta plantilla con un editor de texto y sobrescribirla con sus propias aplicaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="b8d5f-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="b8d5f-162">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="b8d5f-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="b8d5f-163">Verá el siguiente texto impreso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b8d5f-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="b8d5f-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b8d5f-164">Next steps</span></span>

<span data-ttu-id="b8d5f-165">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b8d5f-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
