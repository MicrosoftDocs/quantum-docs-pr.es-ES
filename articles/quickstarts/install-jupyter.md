---
title: Desarrollo con cuadernos en Q# de Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 8a878e8f930f4b898f4de35751e4a39cc8716cec
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884268"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="2ed38-102">Desarrollo con cuadernos en Q# de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2ed38-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="2ed38-103">Instale el QDK para desarrollar operaciones de Q# en cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2ed38-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="2ed38-104">Jupyter Notebook permite la ejecución de código en contexto junto con instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="2ed38-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="2ed38-105">Este entorno es idóneo para escribir código de Q# con explicaciones insertadas o tutoriales interactivos sobre computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="2ed38-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="2ed38-106">Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.</span><span class="sxs-lookup"><span data-stu-id="2ed38-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="2ed38-107">En los cuadernos en Q# de Jupyter Notebook solo se puede ejecutar código de Q#, y no se puede llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#).</span><span class="sxs-lookup"><span data-stu-id="2ed38-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="2ed38-108">Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="2ed38-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-iq-jupyter-kernel"></a><span data-ttu-id="2ed38-109">Instalación del kernel de IQ# para Jupyter</span><span class="sxs-lookup"><span data-stu-id="2ed38-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="2ed38-110">IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="2ed38-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="2ed38-111">Instalación mediante Conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2ed38-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="2ed38-112">Instale [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="2ed38-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span>

1. <span data-ttu-id="2ed38-113">Abra un símbolo del sistema de Anaconda.</span><span class="sxs-lookup"><span data-stu-id="2ed38-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="2ed38-114">O bien, si prefiere usar PowerShell o pwsh, abra un shell, ejecute `conda init powershell`, luego cierre y vuelva a abrir el shell.</span><span class="sxs-lookup"><span data-stu-id="2ed38-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="2ed38-115">Cree y active un nuevo entorno de Conda llamado `qsharp-env` con los paquetes necesarios (incluidos Jupyter Notebook e IQ#) mediante la ejecución de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="2ed38-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="2ed38-116">Ejecute `python -c "import qsharp"` desde el mismo terminal para comprobar la instalación y rellenar la memoria caché del paquete local con todos los componentes del QDK necesarios.</span><span class="sxs-lookup"><span data-stu-id="2ed38-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="2ed38-117">Instalación mediante la CLI de .NET (avanzado)</span><span class="sxs-lookup"><span data-stu-id="2ed38-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="2ed38-118">Requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="2ed38-118">Prerequisites:</span></span>

    - <span data-ttu-id="2ed38-119">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2ed38-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="2ed38-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2ed38-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="2ed38-121">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2ed38-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="2ed38-122">Instale el paquete `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="2ed38-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="2ed38-123">Si recibe un error durante el paso `dotnet iqsharp install`, abra una nueva ventana de terminal e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2ed38-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="2ed38-124">Si aún así no funciona, intente buscar la herramienta `dotnet-iqsharp` instalada (en Windows, `dotnet-iqsharp.exe`) y ejecute:</span><span class="sxs-lookup"><span data-stu-id="2ed38-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="2ed38-125">donde `/path/to/dotnet-iqsharp` debe reemplazarse por la ruta de acceso absoluta a la herramienta `dotnet-iqsharp` en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2ed38-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="2ed38-126">Normalmente, estará en `.dotnet/tools`, en la carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="2ed38-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="2ed38-127">Eso es todo.</span><span class="sxs-lookup"><span data-stu-id="2ed38-127">That's it!</span></span> <span data-ttu-id="2ed38-128">Ahora tiene el kernel de IQ# para Jupyter, que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q# desde cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2ed38-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-q-notebook"></a><span data-ttu-id="2ed38-129">Creación del primer cuaderno de Q#</span><span class="sxs-lookup"><span data-stu-id="2ed38-129">Create your first Q# notebook</span></span>

<span data-ttu-id="2ed38-130">Ahora ya puede comprobar la instalación del cuaderno en Q# de Jupyter Notebook; para ello, escriba y ejecute una sencilla operación de Q#.</span><span class="sxs-lookup"><span data-stu-id="2ed38-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="2ed38-131">En el entorno que creó durante la instalación (es decir, en el entorno de Conda que creó, o en el entorno de Python donde instaló Jupyter), ejecute el siguiente comando para iniciar el servidor de Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="2ed38-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="2ed38-132">Si el cuaderno de Jupyter Notebook no se abre automáticamente en su explorador, copie y pegue en el explorador la dirección URL proporcionada por la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2ed38-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="2ed38-133">Seleccione "Nuevo" → "Q#" para crear un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="2ed38-133">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="2ed38-134">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="2ed38-134">Run this cell of the notebook:</span></span>

    ![Celda del cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="2ed38-136">Debe aparecer `SampleQuantumRandomNumberGenerator` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="2ed38-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="2ed38-137">Cuando se ejecuta en cuadernos de Jupyter Notebook, el código de Q# se compila y la salida de la celda es el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="2ed38-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="2ed38-138">En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="2ed38-138">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Celda del cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="2ed38-140">Verá el resultado de la operación que ha invocado.</span><span class="sxs-lookup"><span data-stu-id="2ed38-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="2ed38-141">En este caso, como la operación genera un resultado aleatorio, verá `Zero` o `One` en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="2ed38-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="2ed38-142">Si ejecuta la celda varias veces, verá cada resultado aproximadamente la mitad del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2ed38-142">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ed38-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2ed38-143">Next steps</span></span>

<span data-ttu-id="2ed38-144">Ahora que ha instalado el QDK para los cuadernos en Q# de Jupyter Notebook, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng) escribiendo código de Q# directamente en el entorno de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2ed38-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="2ed38-145">Para ver más ejemplos de lo que puede hacer con los cuadernos en Q# de Jupyter Notebook, eche un vistazo a:</span><span class="sxs-lookup"><span data-stu-id="2ed38-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="2ed38-146">[Introducción a Q# y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="2ed38-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="2ed38-147">Ahí encontrará un cuaderno en Q# de Jupyter Notebook con más información sobre cómo usar Q# en el entorno de Jupyter.</span><span class="sxs-lookup"><span data-stu-id="2ed38-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="2ed38-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y ejercicios de programación en forma de cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2ed38-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="2ed38-149">Los [cuadernos de tutoriales de Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="2ed38-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="2ed38-150">Quantum Katas es una serie de tutoriales de código abierto autoguiados para la enseñanza de elementos de la computación cuántica y de la programación con Q#.</span><span class="sxs-lookup"><span data-stu-id="2ed38-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="2ed38-151">Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2ed38-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
