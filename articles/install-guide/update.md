---
title: Actualización del kit de desarrollo de Quantum (QDK)
description: 'Describe cómo actualizar los proyectos de Q # y el Microsoft Quantum Development Kit a la versión actual.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578188"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="06634-103">Actualización del Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="06634-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="06634-104">Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="06634-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="06634-105">En este artículo se da por supuesto que ya tiene el QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="06634-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="06634-106">Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="06634-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="06634-107">Se recomienda mantenerse al día con la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="06634-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="06634-108">Siga esta guía de actualización para actualizar a la versión más reciente de QDK.</span><span class="sxs-lookup"><span data-stu-id="06634-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="06634-109">El proceso consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="06634-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="06634-110">Actualizar los proyectos y archivos de preguntas # existentes para alinear el código con cualquier sintaxis actualizada.</span><span class="sxs-lookup"><span data-stu-id="06634-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="06634-111">Actualización del propio QDK para el entorno de desarrollo elegido.</span><span class="sxs-lookup"><span data-stu-id="06634-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="06634-112">Actualizar proyectos de Q #</span><span class="sxs-lookup"><span data-stu-id="06634-112">Updating Q# Projects</span></span> 

<span data-ttu-id="06634-113">Independientemente de si usa C# o Python para hospedar las operaciones de Q #, siga estas instrucciones para actualizar los proyectos de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="06634-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="06634-114">En primer lugar, compruebe que dispone de la versión más reciente del [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="06634-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="06634-115">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="06634-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="06634-116">Compruebe que la salida es `3.1.100` o superior.</span><span class="sxs-lookup"><span data-stu-id="06634-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="06634-117">Si no es así, instale la [versión más reciente](https://dotnet.microsoft.com/download) y vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="06634-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="06634-118">A continuación, siga las instrucciones que se indican a continuación en función de la configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="06634-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="06634-119">Actualización de proyectos de Q # en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06634-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="06634-120">Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="06634-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="06634-121">Abra su solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06634-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="06634-122">En el menú, seleccione **compilar**  ->  **solución limpia**.</span><span class="sxs-lookup"><span data-stu-id="06634-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="06634-123">En cada uno de los archivos. csproj, actualice la plataforma de destino en `netcoreapp3.1` (o `netstandard2.1` si se trata de un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="06634-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="06634-124">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="06634-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="06634-125">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="06634-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="06634-126">En cada uno de los archivos. csproj, establezca el SDK en `Microsoft.Quantum.Sdk` , como se indica en la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="06634-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="06634-127">Tenga en cuenta que el número de versión debe ser el más reciente disponible y puede determinarlo revisando las [notas](https://docs.microsoft.com/quantum/relnotes/)de la versión.</span><span class="sxs-lookup"><span data-stu-id="06634-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="06634-128">Guarde y cierre todos los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="06634-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="06634-129">Seleccione **herramientas**  ->  símbolo del sistema para desarrolladores de**línea de comandos**  ->  **Developer Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="06634-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="06634-130">Como alternativa, puede usar la consola de administración de paquetes en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06634-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="06634-131">Para cada proyecto de la solución, ejecute el siguiente comando para **quitar** este paquete:</span><span class="sxs-lookup"><span data-stu-id="06634-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="06634-132">Si los proyectos usan otros paquetes Microsoft. Quantum o Microsoft. Azure. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute el comando **Add** para que se actualice la versión usada.</span><span class="sxs-lookup"><span data-stu-id="06634-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="06634-133">Cierre el símbolo del sistema y **Seleccione compilar compilar**  ->  **solución** ( *no* seleccione recompilar solución).</span><span class="sxs-lookup"><span data-stu-id="06634-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="06634-134">Ahora puede continuar con [la actualización de la extensión QDK de Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="06634-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="06634-135">Actualizar proyectos de Q # en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="06634-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="06634-136">En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="06634-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="06634-137">Seleccione **terminal**  ->  **nuevo terminal**.</span><span class="sxs-lookup"><span data-stu-id="06634-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="06634-138">Siga las instrucciones para la actualización mediante la línea de comandos (directamente a continuación).</span><span class="sxs-lookup"><span data-stu-id="06634-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="06634-139">Actualización de proyectos de Q # mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="06634-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="06634-140">Navegue hasta la carpeta que contiene el archivo de proyecto principal.</span><span class="sxs-lookup"><span data-stu-id="06634-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="06634-141">Ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="06634-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="06634-142">Determine la versión actual de QDK.</span><span class="sxs-lookup"><span data-stu-id="06634-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="06634-143">Para encontrarlo, puede revisar las [notas](https://docs.microsoft.com/quantum/relnotes/)de la versión.</span><span class="sxs-lookup"><span data-stu-id="06634-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="06634-144">La versión tendrá un formato similar a `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="06634-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="06634-145">En cada uno de los `.csproj` archivos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="06634-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="06634-146">Actualice la versión de .NET Framework de destino a `netcoreapp3.1` (o `netstandard2.1` si se trata de un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="06634-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="06634-147">Es decir, edite las líneas del formulario:</span><span class="sxs-lookup"><span data-stu-id="06634-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="06634-148">Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="06634-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="06634-149">Reemplace la referencia al SDK en la definición del proyecto.</span><span class="sxs-lookup"><span data-stu-id="06634-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="06634-150">Asegúrese de que el número de versión corresponde al valor determinado en el **paso 3**.</span><span class="sxs-lookup"><span data-stu-id="06634-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="06634-151">Quite la referencia al paquete `Microsoft.Quantum.Development.Kit` si está presente, que se especificará en la siguiente entrada:</span><span class="sxs-lookup"><span data-stu-id="06634-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="06634-152">Actualice la versión de todos los paquetes Quantum de Microsoft a la versión de lanzamiento más reciente de QDK (determinada en el **paso 3**).</span><span class="sxs-lookup"><span data-stu-id="06634-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="06634-153">Estos paquetes se denominan con los siguientes patrones:</span><span class="sxs-lookup"><span data-stu-id="06634-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="06634-154">Las referencias a los paquetes tienen el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="06634-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="06634-155">Guarde el archivo actualizado.</span><span class="sxs-lookup"><span data-stu-id="06634-155">Save the updated file.</span></span>

    - <span data-ttu-id="06634-156">Restaure las dependencias del proyecto, para lo que debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06634-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="06634-157">Vuelva a la carpeta que contiene el proyecto principal y ejecute:</span><span class="sxs-lookup"><span data-stu-id="06634-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="06634-158">Con los proyectos de preguntas y respuestas ahora actualizados, siga las instrucciones siguientes para actualizar el propio QDK.</span><span class="sxs-lookup"><span data-stu-id="06634-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="06634-159">Actualización de QDK</span><span class="sxs-lookup"><span data-stu-id="06634-159">Updating the QDK</span></span>

<span data-ttu-id="06634-160">El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.</span><span class="sxs-lookup"><span data-stu-id="06634-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="06634-161">Seleccione el entorno de desarrollo a continuación.</span><span class="sxs-lookup"><span data-stu-id="06634-161">Select your development environment below.</span></span>

* [<span data-ttu-id="06634-162">Python: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="06634-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="06634-163">Cuadernos de Jupyter: actualización de la extensión de IQ #</span><span class="sxs-lookup"><span data-stu-id="06634-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="06634-164">Visual Studio: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="06634-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="06634-165">VS Code: actualización de la extensión QDK</span><span class="sxs-lookup"><span data-stu-id="06634-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="06634-166">Línea de comandos y C#: actualizar plantillas de proyecto</span><span class="sxs-lookup"><span data-stu-id="06634-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="06634-167">Actualización de IQ # para Python</span><span class="sxs-lookup"><span data-stu-id="06634-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="06634-168">Actualizar el `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="06634-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="06634-169">Comprobar la `iqsharp` versión</span><span class="sxs-lookup"><span data-stu-id="06634-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="06634-170">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="06634-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="06634-171">No se preocupe si su `iqsharp` versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="06634-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="06634-172">Actualización del `qsharp` paquete</span><span class="sxs-lookup"><span data-stu-id="06634-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="06634-173">Comprobar la `qsharp` versión</span><span class="sxs-lookup"><span data-stu-id="06634-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="06634-174">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="06634-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="06634-175">Ejecute el siguiente comando desde la ubicación de los `.qs` archivos.</span><span class="sxs-lookup"><span data-stu-id="06634-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="06634-176">Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="06634-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="06634-177">Actualización de IQ # for Jupyter notebooks</span><span class="sxs-lookup"><span data-stu-id="06634-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="06634-178">Actualizar el `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="06634-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="06634-179">Comprobar la `iqsharp` versión</span><span class="sxs-lookup"><span data-stu-id="06634-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="06634-180">La salida debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="06634-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="06634-181">No se preocupe si su `iqsharp` versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="06634-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="06634-182">Ejecute el siguiente comando desde una celda del Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="06634-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="06634-183">Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.</span><span class="sxs-lookup"><span data-stu-id="06634-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="06634-184">Actualización de la extensión QDK de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06634-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="06634-185">Actualización de la extensión de preguntas y respuestas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06634-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="06634-186">Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="06634-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="06634-187">Aceptar la actualización</span><span class="sxs-lookup"><span data-stu-id="06634-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="06634-188">Las plantillas de proyecto se actualizan con la extensión.</span><span class="sxs-lookup"><span data-stu-id="06634-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="06634-189">Las plantillas actualizadas solo se aplican a los proyectos recién creados.</span><span class="sxs-lookup"><span data-stu-id="06634-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="06634-190">El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.</span><span class="sxs-lookup"><span data-stu-id="06634-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="06634-191">Actualizar VS Code extensión QDK</span><span class="sxs-lookup"><span data-stu-id="06634-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="06634-192">Actualización de la extensión de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="06634-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="06634-193">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="06634-193">Restart VS Code</span></span>
    - <span data-ttu-id="06634-194">Vaya a la pestaña **extensiones** .</span><span class="sxs-lookup"><span data-stu-id="06634-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="06634-195">Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="06634-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="06634-196">Recarga de la extensión</span><span class="sxs-lookup"><span data-stu-id="06634-196">Reload the extension</span></span>

2. <span data-ttu-id="06634-197">Actualice las plantillas de proyecto Quantum:</span><span class="sxs-lookup"><span data-stu-id="06634-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="06634-198">Ir a **Ver**  ->  **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="06634-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="06634-199">Seleccionar **Q #: instalar plantillas de proyecto**</span><span class="sxs-lookup"><span data-stu-id="06634-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="06634-200">Después de unos segundos, debe obtener una confirmación emergente de "las plantillas de proyecto se han instalado correctamente".</span><span class="sxs-lookup"><span data-stu-id="06634-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="06634-201">C#, uso de la `dotnet` herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="06634-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="06634-202">Actualización de las plantillas de proyecto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="06634-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
