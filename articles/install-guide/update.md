---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463285"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0517d-102">Actualización del Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="0517d-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0517d-103">Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="0517d-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="0517d-104">En este artículo se da por supuesto que ya tiene el QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="0517d-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="0517d-105">Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="0517d-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="0517d-106">Actualizar proyectos de Q #</span><span class="sxs-lookup"><span data-stu-id="0517d-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="0517d-107">En primer lugar, instale la versión más reciente del [SDK de .NET Core 3,0](https://dotnet.microsoft.com/download) y ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="0517d-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="0517d-108">Compruebe que la salida sea 3.0.100 o posterior y, a continuación, siga las instrucciones que se indican a continuación en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0517d-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="0517d-109">En Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0517d-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="0517d-110">Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="0517d-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="0517d-111">Abrir la solución en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0517d-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="0517d-112">En el menú, seleccione compilar > limpiar solución.</span><span class="sxs-lookup"><span data-stu-id="0517d-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="0517d-113">[Actualice la plataforma de destino](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) de cada uno de los archivos. csproj a netcoreapp 3.0 (o netstandard 2.1 si es un proyecto de biblioteca)</span><span class="sxs-lookup"><span data-stu-id="0517d-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="0517d-114">Guardar y cerrar todos los archivos de la solución</span><span class="sxs-lookup"><span data-stu-id="0517d-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="0517d-115">Seleccione Herramientas > > de línea de comandos Símbolo del sistema para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="0517d-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="0517d-116">Para cada proyecto de la solución, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0517d-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="0517d-117">Si los proyectos usan otros paquetes Microsoft. Quantum, ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="0517d-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="0517d-118">Cierre el símbolo del sistema y seleccione compilar > compilar solución ( *no* seleccione recompilar solución, ya que la regeneración no se realizará inicialmente)</span><span class="sxs-lookup"><span data-stu-id="0517d-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="0517d-119">En Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0517d-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="0517d-120">En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="0517d-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="0517d-121">Seleccionar terminal > nuevo terminal</span><span class="sxs-lookup"><span data-stu-id="0517d-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="0517d-122">Siga las instrucciones para la actualización mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="0517d-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="0517d-123">Usar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="0517d-123">Using the command line</span></span>

1. <span data-ttu-id="0517d-124">Navegue hasta la carpeta que contiene el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0517d-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="0517d-125">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0517d-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="0517d-126">[Actualice la plataforma de destino](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) de cada uno de los archivos. csproj a netcoreapp 3.0 (o netstandard 2.1 si es un proyecto de biblioteca)</span><span class="sxs-lookup"><span data-stu-id="0517d-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="0517d-127">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0517d-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="0517d-128">Si el proyecto usa cualquier otro paquete de Microsoft. Quantum, ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="0517d-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="0517d-129">Guardar y cerrar todos los archivos</span><span class="sxs-lookup"><span data-stu-id="0517d-129">Save and close all files</span></span>
6. <span data-ttu-id="0517d-130">Repita 1-4 para cada dependencia del proyecto y, a continuación, vuelva a la carpeta que contiene el proyecto principal y ejecute:</span><span class="sxs-lookup"><span data-stu-id="0517d-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="0517d-131">Actualización de IQ # para Python</span><span class="sxs-lookup"><span data-stu-id="0517d-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="0517d-132">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="0517d-133">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="0517d-134">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="0517d-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="0517d-135">Actualizar el paquete de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="0517d-136">Comprobar la versión de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="0517d-137">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="0517d-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="0517d-138">Ejecute el siguiente comando desde la ubicación de los archivos de `.qs`</span><span class="sxs-lookup"><span data-stu-id="0517d-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="0517d-139">Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="0517d-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="0517d-140">Actualización de IQ # for Jupyter notebooks</span><span class="sxs-lookup"><span data-stu-id="0517d-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="0517d-141">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="0517d-142">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0517d-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="0517d-143">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="0517d-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="0517d-144">Ejecute el siguiente comando desde una celda del Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="0517d-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="0517d-145">Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.</span><span class="sxs-lookup"><span data-stu-id="0517d-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="0517d-146">Actualización de la extensión QDK de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0517d-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="0517d-147">Actualización de la extensión de preguntas y respuestas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0517d-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="0517d-148">Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="0517d-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="0517d-149">Aceptar la actualización</span><span class="sxs-lookup"><span data-stu-id="0517d-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="0517d-150">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="0517d-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="0517d-151">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="0517d-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="0517d-152">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="0517d-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="0517d-153">Actualizar VS Code extensión QDK</span><span class="sxs-lookup"><span data-stu-id="0517d-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="0517d-154">Actualización de la extensión de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="0517d-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="0517d-155">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="0517d-155">Restart VS Code</span></span>
    - <span data-ttu-id="0517d-156">Vaya a la pestaña **extensiones** .</span><span class="sxs-lookup"><span data-stu-id="0517d-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="0517d-157">Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0517d-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="0517d-158">Recarga de la extensión</span><span class="sxs-lookup"><span data-stu-id="0517d-158">Reload the extension</span></span>

1. <span data-ttu-id="0517d-159">Actualice las plantillas de proyecto Quantum:</span><span class="sxs-lookup"><span data-stu-id="0517d-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="0517d-160">Ir a **vista** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="0517d-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="0517d-161">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="0517d-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="0517d-162">C#, mediante la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="0517d-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="0517d-163">Actualización de las plantillas de proyecto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="0517d-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="0517d-164">¿Qué es lo próximo?</span><span class="sxs-lookup"><span data-stu-id="0517d-164">What's next?</span></span>

<span data-ttu-id="0517d-165">Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum.</span><span class="sxs-lookup"><span data-stu-id="0517d-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="0517d-166">Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="0517d-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
