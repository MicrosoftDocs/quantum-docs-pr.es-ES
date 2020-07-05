---
title: Desarrollo con aplicaciones de línea de comandos de Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884283"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="86dcd-102">Desarrollo con aplicaciones de línea de comandos de Q#</span><span class="sxs-lookup"><span data-stu-id="86dcd-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="86dcd-103">Los programas de Q# se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C# , F# o Python.</span><span class="sxs-lookup"><span data-stu-id="86dcd-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86dcd-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="86dcd-104">Prerequisites</span></span>

- [<span data-ttu-id="86dcd-105">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="86dcd-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="86dcd-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="86dcd-106">Installation</span></span>

<span data-ttu-id="86dcd-107">Aunque puede compilar aplicaciones de línea de comandos de Q# en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="86dcd-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="86dcd-108">Estos entornos de desarrollo incluyen la funcionalidad enriquecida de la extensión QDK, como advertencias, resaltado de sintaxis o plantillas de proyecto, entre otras.</span><span class="sxs-lookup"><span data-stu-id="86dcd-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="86dcd-109">Para configurar VS Code:</span><span class="sxs-lookup"><span data-stu-id="86dcd-109">To configure VS Code:</span></span>

1. <span data-ttu-id="86dcd-110">Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="86dcd-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="86dcd-111">Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="86dcd-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="86dcd-112">Para configurar Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="86dcd-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="86dcd-113">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="86dcd-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="86dcd-114">Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="86dcd-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="86dcd-115">Para instalar el QDK para otro entorno, escriba en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="86dcd-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="86dcd-116">Desarrollo con Q#</span><span class="sxs-lookup"><span data-stu-id="86dcd-116">Develop with Q#</span></span>

<span data-ttu-id="86dcd-117">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno.</span><span class="sxs-lookup"><span data-stu-id="86dcd-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="86dcd-118">Código de VS</span><span class="sxs-lookup"><span data-stu-id="86dcd-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="86dcd-119">Instale las plantillas de proyecto de Q#:</span><span class="sxs-lookup"><span data-stu-id="86dcd-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="86dcd-120">Abra VS Code.</span><span class="sxs-lookup"><span data-stu-id="86dcd-120">Open VS Code.</span></span>
2. <span data-ttu-id="86dcd-121">Haga clic en **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="86dcd-122">Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto).</span><span class="sxs-lookup"><span data-stu-id="86dcd-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="86dcd-123">Cuando se muestre **Project templates installed successfully** (Plantillas de proyecto instaladas correctamente), ya podrá usar el QDK con sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="86dcd-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="86dcd-124">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="86dcd-124">To create a new project:</span></span>

1. <span data-ttu-id="86dcd-125">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="86dcd-126">Haga clic en **Aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="86dcd-127">Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="86dcd-128">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="86dcd-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="86dcd-129">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="86dcd-129">Inspect the project.</span></span> <span data-ttu-id="86dcd-130">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="86dcd-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="86dcd-131">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="86dcd-131">To run the application:</span></span>
1. <span data-ttu-id="86dcd-132">Haga clic en **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="86dcd-133">En el símbolo del sistema del terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="86dcd-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="86dcd-134">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="86dcd-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="86dcd-135">Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión Q# para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="86dcd-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="86dcd-136">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="86dcd-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="86dcd-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dcd-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="86dcd-138">Cree una aplicación de Q# `Hello World` para comprobar la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86dcd-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="86dcd-139">Para crear una aplicación de Q#:</span><span class="sxs-lookup"><span data-stu-id="86dcd-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="86dcd-140">Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="86dcd-141">Escriba `Q#` en el cuadro de búsqueda, seleccione **Aplicación de Q#** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="86dcd-142">Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="86dcd-143">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="86dcd-143">Inspect the project.</span></span> <span data-ttu-id="86dcd-144">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="86dcd-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="86dcd-145">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="86dcd-145">To run the application:</span></span>
1. <span data-ttu-id="86dcd-146">Seleccione **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="86dcd-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="86dcd-147">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="86dcd-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="86dcd-148">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="86dcd-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="86dcd-149">Otros editores con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="86dcd-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="86dcd-150">Cree una aplicación `Hello World` de Q# para comprobar su instalación.</span><span class="sxs-lookup"><span data-stu-id="86dcd-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="86dcd-151">Cree una aplicación:</span><span class="sxs-lookup"><span data-stu-id="86dcd-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="86dcd-152">Vaya al directorio de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="86dcd-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="86dcd-153">El directorio contendrá un archivo `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="86dcd-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="86dcd-154">Puede modificar esta plantilla con un editor de texto y sobrescribirla con sus propias aplicaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="86dcd-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="86dcd-155">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="86dcd-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="86dcd-156">Verá el siguiente texto impreso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="86dcd-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="86dcd-157">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="86dcd-157">Next steps</span></span>

<span data-ttu-id="86dcd-158">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="86dcd-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
