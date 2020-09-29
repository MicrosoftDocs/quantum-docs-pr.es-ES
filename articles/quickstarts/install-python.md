---
title: Desarrollo con Q# y Python
description: Obtenga información sobre cómo crear una aplicación de Q# con Python.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: f6a2a7d1888cfe458fa3989a27d71fcdeed0f01f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834166"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="a2a8f-103">Desarrollo con Q# y Python</span><span class="sxs-lookup"><span data-stu-id="a2a8f-103">Develop with Q# and Python</span></span>

<span data-ttu-id="a2a8f-104">Instale el QDK para desarrollar programas host de Python para llamar a las operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="a2a8f-105">Instalación del paquete `qsharp` de Python</span><span class="sxs-lookup"><span data-stu-id="a2a8f-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="a2a8f-106">Instalación mediante Conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a2a8f-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="a2a8f-107">Instale [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="a2a8f-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="a2a8f-108">**Nota:** Se necesita una instalación de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="a2a8f-109">Abra un símbolo del sistema de Anaconda.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="a2a8f-110">O bien, si prefiere usar PowerShell o pwsh, abra un shell, ejecute `conda init powershell`, luego cierre y vuelva a abrir el shell.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="a2a8f-111">Cree y active un nuevo entorno de Conda llamado `qsharp-env` con los paquetes necesarios (incluidos Jupyter Notebook e IQ#) mediante la ejecución de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="a2a8f-112">Ejecute `python -c "import qsharp"` desde el mismo terminal para comprobar la instalación y rellenar la memoria caché del paquete local con todos los componentes del QDK necesarios.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="a2a8f-113">Instalación mediante la CLI de .NET y PIP (avanzado)</span><span class="sxs-lookup"><span data-stu-id="a2a8f-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="a2a8f-114">Requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-114">Prerequisites:</span></span>

    - <span data-ttu-id="a2a8f-115">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a2a8f-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="a2a8f-116">El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="a2a8f-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="a2a8f-117">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a2a8f-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="a2a8f-118">Instale `qsharp`, un paquete de Python que habilita la interoperabilidad entre Q# y Python.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="a2a8f-119">Instale IQ#, un kernel usado por Jupyter y Python que proporciona funcionalidad básica para compilar y ejecutar operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="a2a8f-120">Si recibe un error durante el paso `dotnet iqsharp install`, abra una nueva ventana de terminal e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="a2a8f-121">Si aún así no funciona, intente buscar la herramienta `dotnet-iqsharp` instalada (en Windows, `dotnet-iqsharp.exe`) y ejecute:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="a2a8f-122">donde `/path/to/dotnet-iqsharp` debe reemplazarse por la ruta de acceso absoluta a la herramienta `dotnet-iqsharp` en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="a2a8f-123">Normalmente, estará en `.dotnet/tools`, en la carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="a2a8f-124">Eso es todo.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-124">That's it!</span></span> <span data-ttu-id="a2a8f-125">Ahora tiene el paquete `qsharp` de Python y el kernel de IQ# para Jupyter, que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q# desde Python y permite usar cuadernos de Jupyter en Q#.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-125">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="a2a8f-126">Elija el IDE</span><span class="sxs-lookup"><span data-stu-id="a2a8f-126">Choose your IDE</span></span>

<span data-ttu-id="a2a8f-127">Aunque puede usar Q# con Python en cualquier IDE, es muy recomendable usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-127">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="a2a8f-128">La extensión QDK para Visual Studio Code ofrece acceso a una funcionalidad más completa, como advertencias, resaltado de sintaxis, plantillas de proyecto, etc.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-128">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="a2a8f-129">Si desea usar VS Code:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-129">If you would like to use VS Code:</span></span>

- <span data-ttu-id="a2a8f-130">Instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).</span><span class="sxs-lookup"><span data-stu-id="a2a8f-130">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="a2a8f-131">Instale la [extensión QDK para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="a2a8f-131">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="a2a8f-132">Si quiere usar un editor diferente, siga las instrucciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-132">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="a2a8f-133">Escribir el primer programa de Q#</span><span class="sxs-lookup"><span data-stu-id="a2a8f-133">Write your first Q# program</span></span>

<span data-ttu-id="a2a8f-134">Ahora ya puede comprobar la instalación del paquete `qsharp` de Python; para ello, escriba y ejecute un sencillo programa de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-134">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="a2a8f-135">Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` y añádale el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-135">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="a2a8f-136">En la misma carpeta que `Operation.qs`, cree un programa de Python llamado `host.py` para simular la operación de Q# `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-136">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="a2a8f-137">Desde el entorno que creó durante la instalación (es decir, el entorno Conda o Python en el que instaló `qsharp`), ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="a2a8f-137">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="a2a8f-138">Verá el resultado de la operación que ha invocado.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-138">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="a2a8f-139">En este caso, como la operación genera un resultado aleatorio, verá `0` o `1` en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-139">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="a2a8f-140">Si ejecuta el programa varias veces, verá cada resultado aproximadamente la mitad del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-140">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="a2a8f-141">El código de Python es un programa normal de Python.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-141">The Python code is just a normal Python program.</span></span> <span data-ttu-id="a2a8f-142">Puede usar cualquier entorno de Python, incluidos cuadernos en Python de Jupyter Notebook, para escribir el programa de Python y llamar a las operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-142">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="a2a8f-143">El programa de Python puede importar las operaciones de Q# desde cualquier archivo .qs situado en la misma carpeta que el código de Python.</span><span class="sxs-lookup"><span data-stu-id="a2a8f-143">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2a8f-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a2a8f-144">Next steps</span></span>

<span data-ttu-id="a2a8f-145">Ahora que ha probado el kit de desarrollo de Microsoft Quantum en su entorno preferido, siga este tutorial para escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="a2a8f-145">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
