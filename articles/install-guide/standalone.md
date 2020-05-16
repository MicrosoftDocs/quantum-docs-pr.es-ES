---
title: 'Desarrollo con aplicaciones de línea de comandos de Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426431"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="0f2e7-102">Desarrollo con aplicaciones de línea de comandos de Q #</span><span class="sxs-lookup"><span data-stu-id="0f2e7-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="0f2e7-103">Los programas de preguntas y respuestas se pueden ejecutar por sí solos, sin un controlador en un lenguaje de host como C#, F # o Python.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="0f2e7-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f2e7-104">Pre-requisites</span></span>

- [<span data-ttu-id="0f2e7-105">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="0f2e7-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="0f2e7-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="0f2e7-106">Installation</span></span>

<span data-ttu-id="0f2e7-107">Aunque puede compilar aplicaciones de línea de comandos de Q # en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="0f2e7-108">El desarrollo en estas herramientas proporciona acceso a una funcionalidad enriquecida.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="0f2e7-109">Para configurar VS Code:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-109">To configure VS Code:</span></span>

1. <span data-ttu-id="0f2e7-110">Descargue e instale [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="0f2e7-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="0f2e7-111">Instale [Microsoft QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="0f2e7-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="0f2e7-112">Para configurar Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="0f2e7-113">Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 o una versión posterior, con la carga de trabajo de desarrollo multiplataforma de .net Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="0f2e7-114">Descargue e instale [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="0f2e7-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="0f2e7-115">Desarrollo con Q # usando VS Code</span><span class="sxs-lookup"><span data-stu-id="0f2e7-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="0f2e7-116">Instale las plantillas de proyecto de Q #:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="0f2e7-117">Abra VS Code.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-117">Open VS Code.</span></span>
2. <span data-ttu-id="0f2e7-118">Haga clic en **Ver**  ->  **paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="0f2e7-119">Seleccione **Q #: instalar plantillas de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="0f2e7-120">Cuando **las plantillas de proyecto se instalan correctamente** , el QDK está listo para usarse con sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="0f2e7-121">Para crear un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-121">To create a new project:</span></span>

1. <span data-ttu-id="0f2e7-122">Haga clic en **Ver**  ->  **paleta de comandos** y seleccione **Q #: crear nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="0f2e7-123">Haga clic en **aplicación de consola independiente**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="0f2e7-124">Navegue hasta la ubicación donde desea guardar el proyecto y haga clic en **crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="0f2e7-125">Cuando el proyecto se haya creado correctamente, haga clic en **abrir nuevo proyecto...** en la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="0f2e7-126">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-126">Inspect the project.</span></span> <span data-ttu-id="0f2e7-127">Debería ver un archivo de código fuente denominado `Program.qs` , que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="0f2e7-128">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-128">To run the application:</span></span>
1. <span data-ttu-id="0f2e7-129">Haga **clic en terminal**  ->  **nuevo**terminal.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="0f2e7-130">En el símbolo del sistema de terminal, escriba `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="0f2e7-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="0f2e7-131">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="0f2e7-132">Las áreas de trabajo con varias carpetas raíz no se admiten actualmente en la extensión VS Code Q #.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="0f2e7-133">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="0f2e7-134">Desarrollo con Q # usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f2e7-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="0f2e7-135">Compruebe la instalación de Visual Studio mediante la creación de una aplicación de preguntas y respuestas `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="0f2e7-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="0f2e7-136">Para crear una nueva aplicación de Q #:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="0f2e7-137">Abra Visual Studio y haga clic en **archivo**  ->  **nuevo**  ->  **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="0f2e7-138">Escriba `Q#` en el cuadro de búsqueda, seleccione la **aplicación de Q #** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="0f2e7-139">Escriba un nombre y una ubicación para la aplicación y haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="0f2e7-140">Inspeccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-140">Inspect the project.</span></span> <span data-ttu-id="0f2e7-141">Debería ver un archivo de código fuente denominado `Program.qs` , que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="0f2e7-142">Para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0f2e7-142">To run the application:</span></span>
1. <span data-ttu-id="0f2e7-143">Seleccione **depurar**  ->  **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="0f2e7-144">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="0f2e7-145">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en la solución deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0f2e7-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="0f2e7-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0f2e7-146">Next steps</span></span>

<span data-ttu-id="0f2e7-147">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="0f2e7-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
