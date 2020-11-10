---
title: 'Desarrollo con aplicaciones de :::no-loc(Q#)::: en un IDE'
description: 'Obtenga información sobre cómo crear una aplicación de :::no-loc(Q#)::: que se ejecute desde el símbolo del sistema.'
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376429"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="b8b99-103">Desarrollo con aplicaciones de :::no-loc(Q#)::: en un IDE</span><span class="sxs-lookup"><span data-stu-id="b8b99-103">Develop with :::no-loc(Q#)::: applications in an IDE</span></span>

<span data-ttu-id="b8b99-104">Los programas de :::no-loc(Q#)::: se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C#, F# o Python.</span><span class="sxs-lookup"><span data-stu-id="b8b99-104">:::no-loc(Q#)::: programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="b8b99-105">Puede desarrollar aplicaciones de :::no-loc(Q#)::: en Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces o con cualquier editor o IDE, y ejecutar las aplicaciones desde la consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="b8b99-105">You can develop :::no-loc(Q#)::: applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="b8b99-106">Requisitos previos de todos los entornos</span><span class="sxs-lookup"><span data-stu-id="b8b99-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="b8b99-107">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b8b99-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="b8b99-108">Instalación</span><span class="sxs-lookup"><span data-stu-id="b8b99-108">Installation</span></span>

<span data-ttu-id="b8b99-109">Aunque puede crear aplicaciones de :::no-loc(Q#)::: en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para desarrollar aplicaciones de :::no-loc(Q#)::: en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="b8b99-109">While you can build :::no-loc(Q#)::: applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your :::no-loc(Q#)::: applications locally.</span></span> <span data-ttu-id="b8b99-110">Para desarrollar en la nube mediante un explorador web, se recomienda utilizar Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="b8b99-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="b8b99-111">Estos entornos de desarrollo aprovechan la funcionalidad enriquecida de la extensión QDK, como las advertencias, el resaltado de sintaxis o las plantillas de proyecto, entre otras.</span><span class="sxs-lookup"><span data-stu-id="b8b99-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="b8b99-112">Configuración para VS Code:</span><span class="sxs-lookup"><span data-stu-id="b8b99-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="b8b99-113">Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="b8b99-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="b8b99-114">Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="b8b99-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="b8b99-115">Configuración para Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b8b99-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="b8b99-116">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="b8b99-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="b8b99-117">Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="b8b99-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="b8b99-118">Configuración para otros entornos:</span><span class="sxs-lookup"><span data-stu-id="b8b99-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="b8b99-119">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8b99-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="b8b99-120">Configuración para Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="b8b99-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="b8b99-121">Cree una [cuenta de Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="b8b99-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="b8b99-122">Cree un entorno de Codespaces.</span><span class="sxs-lookup"><span data-stu-id="b8b99-122">Create a Codespaces environment.</span></span> <span data-ttu-id="b8b99-123">Consulte la [guía de inicio rápido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="b8b99-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="b8b99-124">Al crear el entorno de Codespace, se recomienda especificar `microsoft/Quantum` en el campo "Git Repository" (Repositorio Git) para cargar la configuración específica del QDK.</span><span class="sxs-lookup"><span data-stu-id="b8b99-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="b8b99-125">Ahora puede iniciar el nuevo entorno y empezar a desarrollar en el explorador mediante el [IDE en la nube de VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="b8b99-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="b8b99-126">También se puede usar la instalación local de VS Code y usar Codespaces como un [entorno remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="b8b99-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="b8b99-127">Desarrollo con :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="b8b99-127">Develop with :::no-loc(Q#):::</span></span>

<span data-ttu-id="b8b99-128">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b8b99-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="b8b99-129">Código de VS</span><span class="sxs-lookup"><span data-stu-id="b8b99-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="b8b99-130">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="b8b99-130">To create a new project:</span></span>

1. <span data-ttu-id="b8b99-131">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **:::no-loc(Q#):::: Crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-131">Click **View** -> **Command Palette** and select **:::no-loc(Q#):::: Create New Project**.</span></span>
2. <span data-ttu-id="b8b99-132">Haga clic en **Aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="b8b99-133">Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-133">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="b8b99-134">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="b8b99-134">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="b8b99-135">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8b99-135">Inspect the project.</span></span> <span data-ttu-id="b8b99-136">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de :::no-loc(Q#)::: que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8b99-136">You should see a source file named `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b8b99-137">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8b99-137">To run the application:</span></span>

1. <span data-ttu-id="b8b99-138">Haga clic en **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-138">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="b8b99-139">En el símbolo del sistema del terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="b8b99-139">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="b8b99-140">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b8b99-140">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="b8b99-141">Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión :::no-loc(Q#)::: para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b8b99-141">Workspaces with multiple root folders are not currently supported by the VS Code :::no-loc(Q#)::: extension.</span></span> <span data-ttu-id="b8b99-142">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="b8b99-142">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="b8b99-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8b99-143">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="b8b99-144">Cree una aplicación de :::no-loc(Q#)::: `Hello World` para comprobar la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8b99-144">Verify your Visual Studio installation by creating a :::no-loc(Q#)::: `Hello World` application.</span></span>

<span data-ttu-id="b8b99-145">Para crear una aplicación nueva de :::no-loc(Q#)::::</span><span class="sxs-lookup"><span data-stu-id="b8b99-145">To create a new :::no-loc(Q#)::: application:</span></span>

1. <span data-ttu-id="b8b99-146">Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-146">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="b8b99-147">Escriba `:::no-loc(Q#):::` en el cuadro de búsqueda, seleccione **Aplicación de :::no-loc(Q#):::** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-147">Type `:::no-loc(Q#):::` in the search box, select **:::no-loc(Q#)::: Application** and click **Next**.</span></span>
3. <span data-ttu-id="b8b99-148">Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-148">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="b8b99-149">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8b99-149">Inspect the project.</span></span> <span data-ttu-id="b8b99-150">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de :::no-loc(Q#)::: que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8b99-150">You should see a source file named `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b8b99-151">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8b99-151">To run the application:</span></span>

1. <span data-ttu-id="b8b99-152">Seleccione **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="b8b99-152">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="b8b99-153">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="b8b99-153">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="b8b99-154">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="b8b99-154">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="b8b99-155">Otros editores con el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="b8b99-155">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b8b99-156">Cree una aplicación de :::no-loc(Q#)::: `Hello World` para comprobar su instalación.</span><span class="sxs-lookup"><span data-stu-id="b8b99-156">Verify your installation by creating a :::no-loc(Q#)::: `Hello World` application.</span></span>

1. <span data-ttu-id="b8b99-157">Cree una aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8b99-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang :::no-loc(Q#)::: -o runSayHello
    ```

1. <span data-ttu-id="b8b99-158">Vaya al directorio de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b8b99-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="b8b99-159">El directorio contendrá un archivo `Program.qs`, que es un programa de :::no-loc(Q#):::que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="b8b99-159">This directory should now contain a file `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="b8b99-160">Puede modificar esta plantilla con un editor de texto y sobrescribirla con sus propias aplicaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="b8b99-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="b8b99-161">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="b8b99-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="b8b99-162">Verá el siguiente texto impreso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b8b99-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="b8b99-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b8b99-163">Next steps</span></span>

<span data-ttu-id="b8b99-164">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b8b99-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
