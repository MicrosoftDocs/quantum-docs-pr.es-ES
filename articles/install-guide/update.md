---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819746"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="2e65d-102">Actualización del Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="2e65d-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="2e65d-103">Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2e65d-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="2e65d-104">En este artículo se da por supuesto que ya tiene el QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="2e65d-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="2e65d-105">Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="2e65d-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="2e65d-106">Se recomienda mantenerse al día con la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="2e65d-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="2e65d-107">Siga esta guía de actualización para actualizar a la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="2e65d-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="2e65d-108">El proceso consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="2e65d-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="2e65d-109">actualización de los proyectos y archivos de preguntas # existentes para alinear el código con cualquier sintaxis actualizada</span><span class="sxs-lookup"><span data-stu-id="2e65d-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="2e65d-110">actualización del propio QDK para el entorno de desarrollo elegido</span><span class="sxs-lookup"><span data-stu-id="2e65d-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="2e65d-111">Actualizar proyectos de Q #</span><span class="sxs-lookup"><span data-stu-id="2e65d-111">Updating Q# Projects</span></span> 

<span data-ttu-id="2e65d-112">Independientemente de si usa C# o Python para hospedar operaciones de q #, siga estas instrucciones para actualizar los proyectos de q #.</span><span class="sxs-lookup"><span data-stu-id="2e65d-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="2e65d-113">En primer lugar, compruebe que dispone de la versión más reciente del [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="2e65d-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="2e65d-114">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="2e65d-114">Run the following command in the command prompt:</span></span>
    ```bash
    dotnet --version
    ```
<span data-ttu-id="2e65d-115">Compruebe que la salida es `3.1.100` o superior.</span><span class="sxs-lookup"><span data-stu-id="2e65d-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="2e65d-116">Si no es así, instale la [versión más reciente](https://dotnet.microsoft.com/download) y vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="2e65d-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="2e65d-117">A continuación, siga las instrucciones que se indican a continuación en función de la configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="2e65d-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="2e65d-118">Actualización de proyectos de Q # en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e65d-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="2e65d-119">Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="2e65d-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="2e65d-120">Abrir la solución en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e65d-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="2e65d-121">En el menú, seleccione **Compilar** -> **limpiar solución** .</span><span class="sxs-lookup"><span data-stu-id="2e65d-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="2e65d-122">En cada uno de los archivos. csproj, actualice la plataforma de destino a `netcoreapp3.0` (o `netstandard2.1` si es un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="2e65d-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="2e65d-123">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="2e65d-123">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="2e65d-124">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="2e65d-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="2e65d-125">Guardar y cerrar todos los archivos de la solución</span><span class="sxs-lookup"><span data-stu-id="2e65d-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="2e65d-126">Seleccione **herramientas** ->  -> de **línea de comandos** **símbolo del sistema para desarrolladores**</span><span class="sxs-lookup"><span data-stu-id="2e65d-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="2e65d-127">Para cada proyecto de la solución, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2e65d-127">For each project in the solution, run the following command:</span></span>
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="2e65d-128">Si los proyectos usan otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="2e65d-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="2e65d-129">Cierre el símbolo del sistema y seleccione **Compilar** -> **compilar solución** ( *no* seleccione recompilar solución, ya que la regeneración no se realizará inicialmente)</span><span class="sxs-lookup"><span data-stu-id="2e65d-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

<span data-ttu-id="2e65d-130">Ahora puede continuar con [la actualización de la extensión QDK de Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="2e65d-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="2e65d-131">Actualizar proyectos de Q # en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2e65d-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="2e65d-132">En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="2e65d-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="2e65d-133">Seleccionar **terminal** -> **nuevo terminal**</span><span class="sxs-lookup"><span data-stu-id="2e65d-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="2e65d-134">Siga las instrucciones para la actualización mediante la línea de comandos (directamente a continuación).</span><span class="sxs-lookup"><span data-stu-id="2e65d-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="2e65d-135">Actualización de proyectos de Q # mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2e65d-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="2e65d-136">Navegue hasta la carpeta que contiene el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="2e65d-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="2e65d-137">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2e65d-137">Run the following command:</span></span>
    ```bash
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="2e65d-138">En cada uno de los archivos. csproj, actualice la plataforma de destino a `netcoreapp3.0` (o `netstandard2.1` si es un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="2e65d-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="2e65d-139">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="2e65d-139">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="2e65d-140">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="2e65d-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="2e65d-141">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2e65d-141">Run the following command:</span></span>
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="2e65d-142">Si el proyecto usa otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.</span><span class="sxs-lookup"><span data-stu-id="2e65d-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="2e65d-143">Guarde y cierre todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="2e65d-143">Save and close all files.</span></span>
6. <span data-ttu-id="2e65d-144">Repita 1-4 para cada dependencia del proyecto y, a continuación, vuelva a la carpeta que contiene el proyecto principal y ejecute:</span><span class="sxs-lookup"><span data-stu-id="2e65d-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
    ```bash
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="2e65d-145">Con los proyectos de preguntas y respuestas ahora actualizados, siga las instrucciones siguientes para actualizar el propio QDK.</span><span class="sxs-lookup"><span data-stu-id="2e65d-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="2e65d-146">Actualización de QDK</span><span class="sxs-lookup"><span data-stu-id="2e65d-146">Updating the QDK</span></span>

<span data-ttu-id="2e65d-147">El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.</span><span class="sxs-lookup"><span data-stu-id="2e65d-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="2e65d-148">Seleccione el entorno de desarrollo a continuación.</span><span class="sxs-lookup"><span data-stu-id="2e65d-148">Select your development environment below.</span></span>

* [<span data-ttu-id="2e65d-149">Python: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="2e65d-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="2e65d-150">Cuadernos de Jupyter: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="2e65d-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="2e65d-151">Visual Studio: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="2e65d-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="2e65d-152">VS Code: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="2e65d-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="2e65d-153">Línea de comandos y C#: actualizar plantillas de proyecto</span><span class="sxs-lookup"><span data-stu-id="2e65d-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="2e65d-154">Actualización de IQ # para Python</span><span class="sxs-lookup"><span data-stu-id="2e65d-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="2e65d-155">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-155">Update the `iqsharp` kernel</span></span> 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="2e65d-156">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-156">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2e65d-157">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="2e65d-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="2e65d-158">No se preocupe si la versión de `iqsharp` es superior, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="2e65d-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="2e65d-159">Actualizar el paquete de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="2e65d-160">Comprobar la versión de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="2e65d-161">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="2e65d-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
5. <span data-ttu-id="2e65d-162">Ejecute el siguiente comando desde la ubicación de los archivos de `.qs`</span><span class="sxs-lookup"><span data-stu-id="2e65d-162">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="2e65d-163">Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="2e65d-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="2e65d-164">Actualización de IQ # for Jupyter notebooks</span><span class="sxs-lookup"><span data-stu-id="2e65d-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="2e65d-165">Actualización del kernel de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-165">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="2e65d-166">Comprobar la versión de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2e65d-166">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2e65d-167">La salida debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e65d-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="2e65d-168">No se preocupe si la versión de `iqsharp` es superior, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="2e65d-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="2e65d-169">Ejecute el siguiente comando desde una celda del Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="2e65d-169">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

4. <span data-ttu-id="2e65d-170">Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.</span><span class="sxs-lookup"><span data-stu-id="2e65d-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="2e65d-171">Actualización de la extensión QDK de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e65d-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="2e65d-172">Actualización de la extensión de preguntas y respuestas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e65d-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="2e65d-173">Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="2e65d-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="2e65d-174">Aceptar la actualización</span><span class="sxs-lookup"><span data-stu-id="2e65d-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e65d-175">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="2e65d-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="2e65d-176">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="2e65d-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="2e65d-177">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="2e65d-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="2e65d-178">Actualizar VS Code extensión QDK</span><span class="sxs-lookup"><span data-stu-id="2e65d-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="2e65d-179">Actualización de la extensión de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="2e65d-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="2e65d-180">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="2e65d-180">Restart VS Code</span></span>
    - <span data-ttu-id="2e65d-181">Vaya a la pestaña **extensiones** .</span><span class="sxs-lookup"><span data-stu-id="2e65d-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="2e65d-182">Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2e65d-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="2e65d-183">Recarga de la extensión</span><span class="sxs-lookup"><span data-stu-id="2e65d-183">Reload the extension</span></span>

2. <span data-ttu-id="2e65d-184">Actualice las plantillas de proyecto Quantum:</span><span class="sxs-lookup"><span data-stu-id="2e65d-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="2e65d-185">Vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="2e65d-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="2e65d-186">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="2e65d-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="2e65d-187">Después de unos segundos, debe obtener una confirmación emergente de "las plantillas de proyecto se han instalado correctamente".</span><span class="sxs-lookup"><span data-stu-id="2e65d-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2e65d-188">C#, mediante la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="2e65d-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2e65d-189">Actualización de las plantillas de proyecto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="2e65d-189">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="2e65d-190">¿Qué es lo próximo?</span><span class="sxs-lookup"><span data-stu-id="2e65d-190">What's next?</span></span>

<span data-ttu-id="2e65d-191">Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e65d-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="2e65d-192">Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="2e65d-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
