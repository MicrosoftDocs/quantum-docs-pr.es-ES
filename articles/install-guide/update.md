---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
description: 'Describe cómo actualizar los proyectos de Q # y el Microsoft Quantum Development Kit a la versión actual.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: bf6d6d3d80af485b555429f25b125bfea685bebf
ms.sourcegitcommit: c57c271ab73f75f165401651fad2b5bc143e9c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82862214"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="fb63d-103">Actualización del Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="fb63d-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="fb63d-104">Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="fb63d-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="fb63d-105">En este artículo se da por supuesto que ya tiene el QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="fb63d-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="fb63d-106">Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="fb63d-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="fb63d-107">Se recomienda mantenerse al día con la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="fb63d-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="fb63d-108">Siga esta guía de actualización para actualizar a la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="fb63d-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="fb63d-109">El proceso consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="fb63d-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="fb63d-110">actualización de los proyectos y archivos de preguntas # existentes para alinear el código con cualquier sintaxis actualizada</span><span class="sxs-lookup"><span data-stu-id="fb63d-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="fb63d-111">actualización del propio QDK para el entorno de desarrollo elegido</span><span class="sxs-lookup"><span data-stu-id="fb63d-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="fb63d-112">Actualizar proyectos de Q #</span><span class="sxs-lookup"><span data-stu-id="fb63d-112">Updating Q# Projects</span></span> 

<span data-ttu-id="fb63d-113">Independientemente de si usa C# o Python para hospedar las operaciones de Q #, siga estas instrucciones para actualizar los proyectos de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="fb63d-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="fb63d-114">En primer lugar, compruebe que dispone de la versión más reciente del [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="fb63d-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="fb63d-115">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="fb63d-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="fb63d-116">Compruebe que la salida `3.1.100` es o superior.</span><span class="sxs-lookup"><span data-stu-id="fb63d-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="fb63d-117">Si no es así, instale la [versión más reciente](https://dotnet.microsoft.com/download) y vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="fb63d-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="fb63d-118">A continuación, siga las instrucciones que se indican a continuación en función de la configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="fb63d-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="fb63d-119">Actualización de proyectos de Q # en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb63d-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="fb63d-120">Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="fb63d-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="fb63d-121">Abrir la solución en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb63d-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="fb63d-122">En el menú, seleccione **compilar** -> **limpiar solución** .</span><span class="sxs-lookup"><span data-stu-id="fb63d-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="fb63d-123">En cada uno de los archivos. csproj, actualice la plataforma de `netcoreapp3.1` destino en `netstandard2.1` (o si se trata de un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="fb63d-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="fb63d-124">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="fb63d-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="fb63d-125">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="fb63d-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="fb63d-126">Guardar y cerrar todos los archivos de la solución</span><span class="sxs-lookup"><span data-stu-id="fb63d-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="fb63d-127">Seleccionar **herramientas** -> **Command Line** -> **símbolo del sistema para desarrolladores** de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="fb63d-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="fb63d-128">Para cada proyecto de la solución, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fb63d-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="fb63d-129">Si los proyectos usan otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="fb63d-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="fb63d-130">Cierre el símbolo del sistema y **Seleccione** -> compilar compilar**solución** ( *no* seleccione recompilar solución).</span><span class="sxs-lookup"><span data-stu-id="fb63d-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="fb63d-131">Ahora puede continuar con [la actualización de la extensión QDK de Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="fb63d-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="fb63d-132">Actualizar proyectos de Q # en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fb63d-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="fb63d-133">En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="fb63d-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="fb63d-134"> -> Seleccione **termina\l\*\*\**nuevo** terminal</span><span class="sxs-lookup"><span data-stu-id="fb63d-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="fb63d-135">Siga las instrucciones para la actualización mediante la línea de comandos (directamente a continuación).</span><span class="sxs-lookup"><span data-stu-id="fb63d-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="fb63d-136">Actualización de proyectos de Q # mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="fb63d-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="fb63d-137">Navegue hasta la carpeta que contiene el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb63d-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="fb63d-138">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fb63d-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="fb63d-139">En cada uno de los archivos. csproj, actualice la plataforma de `netcoreapp3.1` destino en `netstandard2.1` (o si se trata de un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="fb63d-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="fb63d-140">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="fb63d-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="fb63d-141">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="fb63d-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="fb63d-142">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fb63d-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="fb63d-143">Si el proyecto usa otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="fb63d-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="fb63d-144">Guarde y cierre todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="fb63d-144">Save and close all files.</span></span>
6. <span data-ttu-id="fb63d-145">Repita 1-4 para cada dependencia del proyecto y, a continuación, vuelva a la carpeta que contiene el proyecto principal y ejecute:</span><span class="sxs-lookup"><span data-stu-id="fb63d-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="fb63d-146">Con los proyectos de preguntas y respuestas ahora actualizados, siga las instrucciones siguientes para actualizar el propio QDK.</span><span class="sxs-lookup"><span data-stu-id="fb63d-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="fb63d-147">Actualización de QDK</span><span class="sxs-lookup"><span data-stu-id="fb63d-147">Updating the QDK</span></span>

<span data-ttu-id="fb63d-148">El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.</span><span class="sxs-lookup"><span data-stu-id="fb63d-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="fb63d-149">Seleccione el entorno de desarrollo a continuación.</span><span class="sxs-lookup"><span data-stu-id="fb63d-149">Select your development environment below.</span></span>

* [<span data-ttu-id="fb63d-150">Python: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="fb63d-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="fb63d-151">Cuadernos de Jupyter: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="fb63d-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="fb63d-152">Visual Studio: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="fb63d-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="fb63d-153">VS Code: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="fb63d-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="fb63d-154">Línea de comandos y C#: actualizar plantillas de proyecto</span><span class="sxs-lookup"><span data-stu-id="fb63d-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="fb63d-155">Actualización de IQ # para Python</span><span class="sxs-lookup"><span data-stu-id="fb63d-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="fb63d-156">Actualizar el `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="fb63d-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="fb63d-157">Comprobar la `iqsharp` versión</span><span class="sxs-lookup"><span data-stu-id="fb63d-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="fb63d-158">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="fb63d-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="fb63d-159">No se preocupe si `iqsharp` su versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="fb63d-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="fb63d-160">Actualización del `qsharp` paquete</span><span class="sxs-lookup"><span data-stu-id="fb63d-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="fb63d-161">Comprobar la `qsharp` versión</span><span class="sxs-lookup"><span data-stu-id="fb63d-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="fb63d-162">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="fb63d-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="fb63d-163">Ejecute el siguiente comando desde la ubicación de los `.qs` archivos.</span><span class="sxs-lookup"><span data-stu-id="fb63d-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="fb63d-164">Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="fb63d-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="fb63d-165">Actualización de IQ # for Jupyter notebooks</span><span class="sxs-lookup"><span data-stu-id="fb63d-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="fb63d-166">Actualizar el `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="fb63d-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="fb63d-167">Comprobar la `iqsharp` versión</span><span class="sxs-lookup"><span data-stu-id="fb63d-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="fb63d-168">La salida debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb63d-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="fb63d-169">No se preocupe si `iqsharp` su versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="fb63d-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="fb63d-170">Ejecute el siguiente comando desde una celda del Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="fb63d-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="fb63d-171">Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.</span><span class="sxs-lookup"><span data-stu-id="fb63d-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="fb63d-172">Actualización de la extensión QDK de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb63d-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="fb63d-173">Actualización de la extensión de preguntas y respuestas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb63d-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="fb63d-174">Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="fb63d-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="fb63d-175">Aceptar la actualización</span><span class="sxs-lookup"><span data-stu-id="fb63d-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb63d-176">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="fb63d-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="fb63d-177">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="fb63d-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="fb63d-178">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="fb63d-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="fb63d-179">Actualizar VS Code extensión QDK</span><span class="sxs-lookup"><span data-stu-id="fb63d-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="fb63d-180">Actualización de la extensión de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="fb63d-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="fb63d-181">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="fb63d-181">Restart VS Code</span></span>
    - <span data-ttu-id="fb63d-182">Vaya a la pestaña **extensiones** .</span><span class="sxs-lookup"><span data-stu-id="fb63d-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="fb63d-183">Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fb63d-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="fb63d-184">Recarga de la extensión</span><span class="sxs-lookup"><span data-stu-id="fb63d-184">Reload the extension</span></span>

2. <span data-ttu-id="fb63d-185">Actualice las plantillas de proyecto Quantum:</span><span class="sxs-lookup"><span data-stu-id="fb63d-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="fb63d-186">Ir a **Ver** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="fb63d-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="fb63d-187">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="fb63d-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="fb63d-188">Después de unos segundos, debe obtener una confirmación emergente de "las plantillas de proyecto se han instalado correctamente".</span><span class="sxs-lookup"><span data-stu-id="fb63d-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="fb63d-189">C#, uso de `dotnet` la herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="fb63d-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="fb63d-190">Actualización de las plantillas de proyecto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="fb63d-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="fb63d-191">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="fb63d-191">What's next?</span></span>

<span data-ttu-id="fb63d-192">Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum.</span><span class="sxs-lookup"><span data-stu-id="fb63d-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="fb63d-193">Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="fb63d-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
