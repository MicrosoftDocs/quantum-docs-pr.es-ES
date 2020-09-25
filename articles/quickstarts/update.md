---
title: Actualización del kit de desarrollo de Microsoft Quantum
description: Describe cómo actualizar los proyectos de Q# y el kit de desarrollo de Microsoft Quantum a la versión actual.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: d9678a61f5fe4ca466b6a84e9e4b68321c5baee3
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834930"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="9659a-103">Actualización del kit de desarrollo de Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="9659a-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="9659a-104">Descubra cómo actualizar el kit de desarrollo de Microsoft Quantum (QDK) a la última versión.</span><span class="sxs-lookup"><span data-stu-id="9659a-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="9659a-105">En este artículo se da por hecho que ya tiene el QDK instalado:</span><span class="sxs-lookup"><span data-stu-id="9659a-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="9659a-106">Si va a instalarlo por primera vez, consulte la [guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="9659a-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="9659a-107">Es recomendable mantenerse al día con la versión más reciente del QDK.</span><span class="sxs-lookup"><span data-stu-id="9659a-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="9659a-108">Siga esta guía de actualización para actualizar a la versión más reciente del QDK.</span><span class="sxs-lookup"><span data-stu-id="9659a-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="9659a-109">El proceso consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="9659a-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="9659a-110">Actualización de los proyectos y archivos de Q# existentes para alinear el código con la sintaxis actualizada.</span><span class="sxs-lookup"><span data-stu-id="9659a-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="9659a-111">Actualización del propio QDK para el entorno de desarrollo elegido.</span><span class="sxs-lookup"><span data-stu-id="9659a-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="9659a-112">Actualización de proyectos de Q#</span><span class="sxs-lookup"><span data-stu-id="9659a-112">Updating Q# Projects</span></span> 

<span data-ttu-id="9659a-113">Independientemente de si usa C# o Python para hospedar las operaciones de Q#, siga estas instrucciones para actualizar los proyectos de Q#.</span><span class="sxs-lookup"><span data-stu-id="9659a-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="9659a-114">En primer lugar, compruebe que tiene la versión más reciente del [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="9659a-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="9659a-115">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="9659a-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="9659a-116">Compruebe que la salida es `3.1.100` o superior.</span><span class="sxs-lookup"><span data-stu-id="9659a-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="9659a-117">Si no es así, instale la [última versión](https://dotnet.microsoft.com/download) y vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="9659a-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="9659a-118">Después, siga las instrucciones que se indican a continuación en función de su configuración (Visual Studio, Visual Studio Code o directamente desde el símbolo del sistema).</span><span class="sxs-lookup"><span data-stu-id="9659a-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="9659a-119">Actualización de proyectos de Q# en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9659a-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="9659a-120">Actualice a la versión más reciente de Visual Studio 2019; consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9659a-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="9659a-121">Abra su solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9659a-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="9659a-122">En el menú, seleccione **Compilar** -> **Limpiar solución**.</span><span class="sxs-lookup"><span data-stu-id="9659a-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="9659a-123">En cada uno de los archivos .csproj, actualice la plataforma de destino a `netcoreapp3.1` (o `netstandard2.1` si es un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="9659a-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="9659a-124">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="9659a-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="9659a-125">[Aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) encontrará más detalles sobre cómo especificar las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="9659a-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="9659a-126">En cada uno de los archivos .csproj, establezca el SDK en `Microsoft.Quantum.Sdk`, tal y como se indica en la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="9659a-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="9659a-127">Tenga en cuenta que el número de versión debe ser el más reciente disponible y puede determinarlo revisando las [notas de la versión](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="9659a-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="9659a-128">Guarde y cierre todos los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="9659a-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="9659a-129">Seleccione **Herramientas** -> **Línea de comandos** -> **Símbolo del sistema para desarrolladores**.</span><span class="sxs-lookup"><span data-stu-id="9659a-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="9659a-130">También puede utilizar la consola del administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9659a-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="9659a-131">En cada proyecto de la solución, ejecute el siguiente comando para **quitar** este paquete:</span><span class="sxs-lookup"><span data-stu-id="9659a-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="9659a-132">Si los proyectos usan otros paquetes de Microsoft.Quantum o Microsoft.Azure.Quantum (por ejemplo, Microsoft.Quantum.Numerics), ejecute el comando **Agregar** para que se actualice la versión usada.</span><span class="sxs-lookup"><span data-stu-id="9659a-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="9659a-133">Cierre el símbolo del sistema y seleccione **Compilar** -> **Compilar solución** (*no* seleccione Recompilar solución).</span><span class="sxs-lookup"><span data-stu-id="9659a-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="9659a-134">Ahora puede ir directamente a [actualizar la extensión QDK para Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="9659a-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="9659a-135">Actualización de proyectos de Q# en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9659a-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="9659a-136">En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="9659a-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="9659a-137">Seleccione **Terminal** -> **Nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="9659a-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="9659a-138">Siga las instrucciones para actualizar mediante el símbolo del sistema (a continuación).</span><span class="sxs-lookup"><span data-stu-id="9659a-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="9659a-139">Actualización de proyectos de Q# mediante el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="9659a-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="9659a-140">Vaya hasta la carpeta que contiene el archivo de proyecto principal.</span><span class="sxs-lookup"><span data-stu-id="9659a-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="9659a-141">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9659a-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="9659a-142">Determine la versión actual del QDK.</span><span class="sxs-lookup"><span data-stu-id="9659a-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="9659a-143">Para encontrarlo, revise las [notas de la versión](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="9659a-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="9659a-144">La versión tendrá un formato similar a `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="9659a-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="9659a-145">En cada uno de los archivos de `.csproj`, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9659a-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="9659a-146">Actualice la plataforma de destino a `netcoreapp3.1` (o `netstandard2.1` si es un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="9659a-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="9659a-147">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="9659a-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="9659a-148">[Aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) encontrará más detalles sobre cómo especificar las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="9659a-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="9659a-149">Reemplace la referencia al SDK en la definición del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9659a-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="9659a-150">Asegúrese de que el número de versión se corresponde con el valor determinado en el **paso 3**.</span><span class="sxs-lookup"><span data-stu-id="9659a-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="9659a-151">Quite la referencia al paquete `Microsoft.Quantum.Development.Kit` si está presente, que se especificará en la entrada siguiente:</span><span class="sxs-lookup"><span data-stu-id="9659a-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="9659a-152">Actualice la versión de todos los paquetes de Microsoft Quantum a la versión de lanzamiento más reciente del QDK (determinada en el **paso 3**).</span><span class="sxs-lookup"><span data-stu-id="9659a-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="9659a-153">El nombre de estos paquetes siguen estos patrones:</span><span class="sxs-lookup"><span data-stu-id="9659a-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="9659a-154">Las referencias a los paquetes tienen el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="9659a-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="9659a-155">Guarde el archivo actualizado.</span><span class="sxs-lookup"><span data-stu-id="9659a-155">Save the updated file.</span></span>

    - <span data-ttu-id="9659a-156">Restaure las dependencias del proyecto de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9659a-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="9659a-157">Vuelva a la carpeta que contiene el archivo de proyecto principal y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9659a-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="9659a-158">Con los proyectos de Q# actualizados, siga estas instrucciones para actualizar el propio QDK.</span><span class="sxs-lookup"><span data-stu-id="9659a-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="9659a-159">Actualización del código</span><span class="sxs-lookup"><span data-stu-id="9659a-159">Updating the QDK</span></span>

<span data-ttu-id="9659a-160">El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.</span><span class="sxs-lookup"><span data-stu-id="9659a-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="9659a-161">Seleccione el entorno de desarrollo a continuación.</span><span class="sxs-lookup"><span data-stu-id="9659a-161">Select your development environment below.</span></span>

* [<span data-ttu-id="9659a-162">Python: actualización del paquete `qsharp`</span><span class="sxs-lookup"><span data-stu-id="9659a-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="9659a-163">Jupyter Notebook: actualización del kernel de IQ#</span><span class="sxs-lookup"><span data-stu-id="9659a-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="9659a-164">Visual Studio: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="9659a-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="9659a-165">VS Code: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="9659a-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="9659a-166">Línea de comandos y C# : actualización de las plantillas de proyecto</span><span class="sxs-lookup"><span data-stu-id="9659a-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="9659a-167">Actualización del paquete `qsharp` de Python</span><span class="sxs-lookup"><span data-stu-id="9659a-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="9659a-168">El procedimiento de actualización depende de la instalación original se hizo con Conda o con la CLI de .NET y PIP.</span><span class="sxs-lookup"><span data-stu-id="9659a-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="9659a-169">Actualización mediante Conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="9659a-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="9659a-170">Active el entorno de Conda en el que instaló el paquete `qsharp` y, a continuación, ejecute este comando para actualizarlo:</span><span class="sxs-lookup"><span data-stu-id="9659a-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="9659a-171">Ejecute el siguiente comando desde la ubicación de los archivos `.qs`:</span><span class="sxs-lookup"><span data-stu-id="9659a-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="9659a-172">Actualización mediante la CLI de .NET y PIP (avanzado)</span><span class="sxs-lookup"><span data-stu-id="9659a-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="9659a-173">Actualice el kernel `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="9659a-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="9659a-174">Compruebe la versión de `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="9659a-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="9659a-175">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="9659a-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="9659a-176">No se preocupe si la versión de `iqsharp` es superior.</span><span class="sxs-lookup"><span data-stu-id="9659a-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="9659a-177">Será la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="9659a-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="9659a-178">Actualice el paquete `qsharp`.</span><span class="sxs-lookup"><span data-stu-id="9659a-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="9659a-179">Compruebe la versión de `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="9659a-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="9659a-180">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="9659a-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="9659a-181">Ejecute el siguiente comando desde la ubicación de los archivos `.qs`:</span><span class="sxs-lookup"><span data-stu-id="9659a-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="9659a-182">Ahora puede usar la versión actualizada del paquete `qsharp` de Python para ejecutar los programas cuánticos existentes.</span><span class="sxs-lookup"><span data-stu-id="9659a-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="9659a-183">Actualización del kernel de IQ# para Jupyter</span><span class="sxs-lookup"><span data-stu-id="9659a-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="9659a-184">El procedimiento de actualización depende de la instalación original se hizo con Conda o con la CLI de .NET y PIP.</span><span class="sxs-lookup"><span data-stu-id="9659a-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="9659a-185">Actualización mediante Conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="9659a-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="9659a-186">Active el entorno de Conda en el que instaló el paquete `qsharp` y, a continuación, ejecute este comando para actualizarlo:</span><span class="sxs-lookup"><span data-stu-id="9659a-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="9659a-187">Ejecute el siguiente comando desde una celda de cada uno de los cuadernos en Q# de Jupyter Notebook existentes:</span><span class="sxs-lookup"><span data-stu-id="9659a-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="9659a-188">Actualización mediante la CLI de .NET y PIP (avanzado)</span><span class="sxs-lookup"><span data-stu-id="9659a-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="9659a-189">Actualice el paquete `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="9659a-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="9659a-190">Compruebe la versión de `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="9659a-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="9659a-191">La salida debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9659a-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="9659a-192">No se preocupe si la versión de `iqsharp` es superior.</span><span class="sxs-lookup"><span data-stu-id="9659a-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="9659a-193">Será la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="9659a-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="9659a-194">Ejecute el siguiente comando desde una celda de cada uno de los cuadernos en Q# de Jupyter Notebook existentes:</span><span class="sxs-lookup"><span data-stu-id="9659a-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="9659a-195">Ahora puede usar el kernel de IQ# actualizado para ejecutar los cuadernos en Q# de Jupyter Notebook existentes.</span><span class="sxs-lookup"><span data-stu-id="9659a-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="9659a-196">Actualización de la extensión QDK para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9659a-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="9659a-197">Actualización de la extensión de Q# para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9659a-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="9659a-198">Visual Studio le pide que acepte las actualizaciones de la [extensión de Quantum para Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="9659a-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="9659a-199">Acepte la actualización.</span><span class="sxs-lookup"><span data-stu-id="9659a-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="9659a-200">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="9659a-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="9659a-201">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="9659a-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="9659a-202">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="9659a-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="9659a-203">Actualización de la extensión QDK para VS Code</span><span class="sxs-lookup"><span data-stu-id="9659a-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="9659a-204">Actualización de la extensión Quantum para VS Code</span><span class="sxs-lookup"><span data-stu-id="9659a-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="9659a-205">Reinicie VS Code.</span><span class="sxs-lookup"><span data-stu-id="9659a-205">Restart VS Code</span></span>
    - <span data-ttu-id="9659a-206">Vaya a la pestaña **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="9659a-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="9659a-207">Seleccione la extensión **Kit de desarrollo de Microsoft Quantum para Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="9659a-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="9659a-208">Vuelva a cargar la extensión</span><span class="sxs-lookup"><span data-stu-id="9659a-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="9659a-209">C#, con la herramienta de línea de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="9659a-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="9659a-210">Actualice las plantillas de proyecto de Quantum para .NET.</span><span class="sxs-lookup"><span data-stu-id="9659a-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="9659a-211">En el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="9659a-211">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="9659a-212">Si tiene la intención de usar las plantillas de línea de comandos y ya tiene instalada la extensión QDK para VS Code, también puede actualizar las plantillas de proyecto desde la propia extensión:</span><span class="sxs-lookup"><span data-stu-id="9659a-212">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="9659a-213">Actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="9659a-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="9659a-214">En VS Code, vaya a **Ver** -> **Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="9659a-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="9659a-215">Seleccione **Q#: Install command line project templates** (Instalar plantillas de proyecto de línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="9659a-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="9659a-216">Después de unos segundos, aparece el mensaje "Project templates installed successfully" (Plantillas de proyecto instaladas correctamente).</span><span class="sxs-lookup"><span data-stu-id="9659a-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
