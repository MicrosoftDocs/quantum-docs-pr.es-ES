---
title: 'Ejecutar programas Q # sin un controlador y un idioma host'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706808"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="12733-102">Aplicaciones de línea de comandos de Q #</span><span class="sxs-lookup"><span data-stu-id="12733-102">Q# Command Line Applications</span></span>

<span data-ttu-id="12733-103">Los programas de preguntas y respuestas se pueden ejecutar por sí solos, sin un controlador en un lenguaje de host como C#, F # o Python.</span><span class="sxs-lookup"><span data-stu-id="12733-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="12733-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="12733-104">Pre-requisites</span></span>

- [<span data-ttu-id="12733-105">SDK de .NET Core 3.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="12733-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="12733-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="12733-106">Installation</span></span>

<span data-ttu-id="12733-107">Aunque puede compilar aplicaciones de línea de comandos de Q # en cualquier IDE, se recomienda encarecidamente usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="12733-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="12733-108">Con VS Code o Visual Studio y la extensión de Visual Studio Code de QDK obtiene acceso a una funcionalidad más enriquecida.</span><span class="sxs-lookup"><span data-stu-id="12733-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="12733-109">Instalación de [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac)</span><span class="sxs-lookup"><span data-stu-id="12733-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="12733-110">Instale la [extensión QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) o</span><span class="sxs-lookup"><span data-stu-id="12733-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="12733-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.</span><span class="sxs-lookup"><span data-stu-id="12733-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="12733-112">Descarga e instalación de la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="12733-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="12733-113">Desarrollo con Q # usando VS Code</span><span class="sxs-lookup"><span data-stu-id="12733-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="12733-114">Instale las plantillas de proyecto de Quantum:</span><span class="sxs-lookup"><span data-stu-id="12733-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="12733-115">Ir a **Ver** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="12733-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="12733-116">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="12733-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="12733-117">Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="12733-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="12733-118">Cree un nuevo proyecto:</span><span class="sxs-lookup"><span data-stu-id="12733-118">Create a new project:</span></span>
  - <span data-ttu-id="12733-119">Ir a **Ver** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="12733-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="12733-120">Seleccione **Q #: crear nuevo proyecto**</span><span class="sxs-lookup"><span data-stu-id="12733-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="12733-121">Seleccionar **aplicación de consola independiente**</span><span class="sxs-lookup"><span data-stu-id="12733-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="12733-122">Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12733-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="12733-123">Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="12733-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="12733-124">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="12733-124">Inspect the project</span></span>
  - <span data-ttu-id="12733-125">Debería ver que se ha creado un `Program.qs` archivo llamado Created, que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="12733-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="12733-126">Ejecute la aplicación:</span><span class="sxs-lookup"><span data-stu-id="12733-126">Run the application:</span></span>
  - <span data-ttu-id="12733-127">Ir a **Terminal** -> terminal**New** terminal</span><span class="sxs-lookup"><span data-stu-id="12733-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="12733-128">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="12733-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="12733-129">Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="12733-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="12733-130">No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="12733-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="12733-131">Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="12733-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="12733-132">Desarrollo con Q # usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12733-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="12733-133">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="12733-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="12733-134">Creación de una aplicación de Q#</span><span class="sxs-lookup"><span data-stu-id="12733-134">Create a new Q# application</span></span>
  - <span data-ttu-id="12733-135">Ir a **archivo** -> **nuevo** -> **proyecto**</span><span class="sxs-lookup"><span data-stu-id="12733-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="12733-136">Escriba `Q#` en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="12733-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="12733-137">Seleccione **Q# Application** (Aplicación de Q#)</span><span class="sxs-lookup"><span data-stu-id="12733-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="12733-138">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="12733-138">Select **Next**</span></span>
  - <span data-ttu-id="12733-139">Elija un nombre y una ubicación para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="12733-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="12733-140">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="12733-140">Select **Create**</span></span>

- <span data-ttu-id="12733-141">Inspección del proyecto</span><span class="sxs-lookup"><span data-stu-id="12733-141">Inspect the project</span></span>
  - <span data-ttu-id="12733-142">Debería ver que se ha creado un `Program.qs` archivo llamado, que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="12733-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="12733-143">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="12733-143">Run the application</span></span>
  - <span data-ttu-id="12733-144">Seleccione **depurar** -> **iniciar sin depurar**</span><span class="sxs-lookup"><span data-stu-id="12733-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="12733-145">Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="12733-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="12733-146">Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="12733-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="12733-147">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="12733-147">What's next?</span></span>

<span data-ttu-id="12733-148">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="12733-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
