---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185858"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="fa444-102">Actualización del Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="fa444-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="fa444-103">Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="fa444-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="fa444-104">En este artículo se da por supuesto que ya tiene el QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="fa444-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="fa444-105">Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="fa444-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="fa444-106">Los pasos de actualización dependen de su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fa444-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="fa444-107">Elija el entorno en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fa444-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="fa444-108">Python</span><span class="sxs-lookup"><span data-stu-id="fa444-108">Python</span></span>

1. <span data-ttu-id="fa444-109">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="fa444-110">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="fa444-111">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="fa444-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="fa444-112">Actualizar el paquete de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="fa444-113">Comprobar la versión de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="fa444-114">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="fa444-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="fa444-115">Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="fa444-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="fa444-116">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="fa444-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="fa444-117">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="fa444-118">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="fa444-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="fa444-119">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="fa444-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="fa444-120">Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.</span><span class="sxs-lookup"><span data-stu-id="fa444-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="fa444-121">C#en Windows con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa444-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="fa444-122">Actualización de la extensión de preguntas y respuestas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa444-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="fa444-123">Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="fa444-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="fa444-124">Aceptar la actualización</span><span class="sxs-lookup"><span data-stu-id="fa444-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa444-125">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="fa444-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="fa444-126">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="fa444-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="fa444-127">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="fa444-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="fa444-128">Actualización de los paquetes de QDK</span><span class="sxs-lookup"><span data-stu-id="fa444-128">Update the QDK packages</span></span>

    - <span data-ttu-id="fa444-129">Abrir una aplicación existente</span><span class="sxs-lookup"><span data-stu-id="fa444-129">Open an existing application</span></span>
    - <span data-ttu-id="fa444-130">Seleccione las **dependencias** en el explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="fa444-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="fa444-131">Seleccione **administrar paquetes NuGet** .</span><span class="sxs-lookup"><span data-stu-id="fa444-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="fa444-132">Actualización de los paquetes de **Microsoft. Quantum** a la versión más reciente</span><span class="sxs-lookup"><span data-stu-id="fa444-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="fa444-133">Ahora puede ejecutar la aplicación con el QDK más reciente.</span><span class="sxs-lookup"><span data-stu-id="fa444-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="fa444-134">C#, mediante VS Code</span><span class="sxs-lookup"><span data-stu-id="fa444-134">C#, using VS Code</span></span>

1. <span data-ttu-id="fa444-135">Actualización de la extensión de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="fa444-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="fa444-136">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="fa444-136">Restart VS Code</span></span>
    - <span data-ttu-id="fa444-137">Vaya a la pestaña **extensiones** .</span><span class="sxs-lookup"><span data-stu-id="fa444-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="fa444-138">Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fa444-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="fa444-139">Recarga de la extensión</span><span class="sxs-lookup"><span data-stu-id="fa444-139">Reload the extension</span></span>

1. <span data-ttu-id="fa444-140">Actualice las plantillas de proyecto Quantum:</span><span class="sxs-lookup"><span data-stu-id="fa444-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="fa444-141">Ir a **vista** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="fa444-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="fa444-142">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="fa444-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="fa444-143">Abra una aplicación existente en VS Code</span><span class="sxs-lookup"><span data-stu-id="fa444-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="fa444-144">Edite el archivo. csproj para agregar las nuevas versiones del paquete</span><span class="sxs-lookup"><span data-stu-id="fa444-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="fa444-145">Si usa otros paquetes de `Microsoft.Quantum`, también puede actualizarlos.</span><span class="sxs-lookup"><span data-stu-id="fa444-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="fa444-146">Ahora puede ejecutar la aplicación con el QDK actualizado</span><span class="sxs-lookup"><span data-stu-id="fa444-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="fa444-147">C#, mediante la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="fa444-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="fa444-148">Actualización de las plantillas de proyecto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="fa444-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="fa444-149">Actualización y ejecución de una aplicación existente</span><span class="sxs-lookup"><span data-stu-id="fa444-149">Update and run an existing application</span></span>

    - <span data-ttu-id="fa444-150">Actualización de las versiones del paquete QDK en la aplicación</span><span class="sxs-lookup"><span data-stu-id="fa444-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="fa444-151">Si la aplicación usa cualquier otro paquete de `Microsoft.Quantum`, actualícelo también.</span><span class="sxs-lookup"><span data-stu-id="fa444-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="fa444-152">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="fa444-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="fa444-153">La aplicación se ejecutará con las nuevas versiones del paquete</span><span class="sxs-lookup"><span data-stu-id="fa444-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="fa444-154">¿Qué es lo próximo?</span><span class="sxs-lookup"><span data-stu-id="fa444-154">What's next?</span></span>

<span data-ttu-id="fa444-155">Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum.</span><span class="sxs-lookup"><span data-stu-id="fa444-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="fa444-156">Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="fa444-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
