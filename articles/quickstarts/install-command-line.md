---
title: Desarrollo con aplicaciones de línea de comandos de Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274193"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="111ef-102">Desarrollo con aplicaciones de línea de comandos de Q#</span><span class="sxs-lookup"><span data-stu-id="111ef-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="111ef-103">Los programas de Q# se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C# , F# o Python.</span><span class="sxs-lookup"><span data-stu-id="111ef-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="111ef-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="111ef-104">Prerequisites</span></span>

- [<span data-ttu-id="111ef-105">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="111ef-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="111ef-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="111ef-106">Installation</span></span>

<span data-ttu-id="111ef-107">Aunque puede compilar aplicaciones de línea de comandos de Q# en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="111ef-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="111ef-108">Desarrollar en estas herramientas aporta una funcionalidad enriquecida.</span><span class="sxs-lookup"><span data-stu-id="111ef-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="111ef-109">Para configurar VS Code:</span><span class="sxs-lookup"><span data-stu-id="111ef-109">To configure VS Code:</span></span>

1. <span data-ttu-id="111ef-110">Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="111ef-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="111ef-111">Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="111ef-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="111ef-112">Para configurar Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="111ef-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="111ef-113">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="111ef-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="111ef-114">Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="111ef-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="111ef-115">Desarrollo con Q# mediante VS Code</span><span class="sxs-lookup"><span data-stu-id="111ef-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="111ef-116">Instale las plantillas de proyecto de Q#:</span><span class="sxs-lookup"><span data-stu-id="111ef-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="111ef-117">Abra VS Code.</span><span class="sxs-lookup"><span data-stu-id="111ef-117">Open VS Code.</span></span>
2. <span data-ttu-id="111ef-118">Haga clic en **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="111ef-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="111ef-119">Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto).</span><span class="sxs-lookup"><span data-stu-id="111ef-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="111ef-120">Cuando se muestre **Project templates installed successfully** (Plantillas de proyecto instaladas correctamente), ya podrá usar el QDK con sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="111ef-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="111ef-121">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="111ef-121">To create a new project:</span></span>

1. <span data-ttu-id="111ef-122">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="111ef-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="111ef-123">Haga clic en **Aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="111ef-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="111ef-124">Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="111ef-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="111ef-125">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="111ef-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="111ef-126">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="111ef-126">Inspect the project.</span></span> <span data-ttu-id="111ef-127">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="111ef-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="111ef-128">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="111ef-128">To run the application:</span></span>
1. <span data-ttu-id="111ef-129">Haga clic en **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="111ef-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="111ef-130">En el símbolo del sistema del terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="111ef-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="111ef-131">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="111ef-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="111ef-132">Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión Q# para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="111ef-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="111ef-133">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="111ef-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="111ef-134">Desarrollo con Q# en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="111ef-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="111ef-135">Cree una aplicación de Q# `Hello World` para comprobar la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="111ef-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="111ef-136">Para crear una aplicación de Q#:</span><span class="sxs-lookup"><span data-stu-id="111ef-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="111ef-137">Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="111ef-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="111ef-138">Escriba `Q#` en el cuadro de búsqueda, seleccione **Aplicación de Q#** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="111ef-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="111ef-139">Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="111ef-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="111ef-140">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="111ef-140">Inspect the project.</span></span> <span data-ttu-id="111ef-141">Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="111ef-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="111ef-142">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="111ef-142">To run the application:</span></span>
1. <span data-ttu-id="111ef-143">Seleccione **Depurar** -> **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="111ef-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="111ef-144">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="111ef-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="111ef-145">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="111ef-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="111ef-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="111ef-146">Next steps</span></span>

<span data-ttu-id="111ef-147">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="111ef-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
