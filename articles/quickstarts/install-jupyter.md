---
title: Desarrollo con cuadernos en Q# de Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274160"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="addcc-102">Desarrollo con cuadernos en Q# de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="addcc-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="addcc-103">Instale el QDK para desarrollar operaciones de Q# en cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="addcc-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="addcc-104">Jupyter Notebook permite la ejecución de código en contexto junto con instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="addcc-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="addcc-105">Este entorno es idóneo para escribir código de Q# con explicaciones insertadas o tutoriales interactivos sobre computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="addcc-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="addcc-106">Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.</span><span class="sxs-lookup"><span data-stu-id="addcc-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="addcc-107">IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="addcc-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="addcc-108">En los cuadernos en Q# de Jupyter Notebook solo se puede ejecutar código de Q# y no se puede llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#).</span><span class="sxs-lookup"><span data-stu-id="addcc-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="addcc-109">Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="addcc-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="addcc-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="addcc-110">Prerequisites</span></span>

    - <span data-ttu-id="addcc-111">[Python](https://www.python.org/downloads/) 3.6 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="addcc-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="addcc-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="addcc-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="addcc-113">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="addcc-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="addcc-114">Instalar el paquete `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="addcc-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="addcc-115">Si recibe un error durante el paso `dotnet iqsharp install`, abra una nueva ventana de terminal e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="addcc-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="addcc-116">Si aún así no funciona, intente buscar la herramienta `dotnet-iqsharp` instalada (en Windows, `dotnet-iqsharp.exe`) y ejecute:</span><span class="sxs-lookup"><span data-stu-id="addcc-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="addcc-117">donde `/path/to/dotnet-iqsharp` debe reemplazarse por la ruta de acceso absoluta a la herramienta `dotnet-iqsharp` en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="addcc-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="addcc-118">Normalmente, estará en `.dotnet/tools`, en la carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="addcc-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="addcc-119">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="addcc-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="addcc-120">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="addcc-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="addcc-121">Para abrir el cuaderno de Jupyter Notebook, copie y pegue en el explorador la dirección URL proporcionada por la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="addcc-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="addcc-122">Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="addcc-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="addcc-123">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="addcc-123">Run this cell of the notebook:</span></span>

        ![Celda del cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="addcc-125">Debe aparecer `SayHello` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="addcc-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="addcc-126">Cuando se ejecuta en cuadernos de Jupyter Notebook, el código de Q# se compila y la salida del cuaderno es el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="addcc-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="addcc-127">En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="addcc-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Celda del cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="addcc-129">Verá el mensaje en pantalla junto con el resultado de la operación invocada. En este caso, vemos la tupla vacía `()` porque nuestra operación simplemente devuelve un tipo `Unit`.</span><span class="sxs-lookup"><span data-stu-id="addcc-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="addcc-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="addcc-130">Next steps</span></span>

<span data-ttu-id="addcc-131">Ahora que ha instalado el QDK para los cuadernos en Q# de Jupyter Notebook, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng) escribiendo código de Q# directamente en el entorno de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="addcc-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="addcc-132">Para ver más ejemplos de lo que puede hacer con los cuadernos en Q# de Jupyter Notebook, eche un vistazo a:</span><span class="sxs-lookup"><span data-stu-id="addcc-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="addcc-133">[Introducción a Q# y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="addcc-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="addcc-134">Allí encontrará un cuaderno en Q# de Jupyter Notebook que muestra cómo usar Q# en este entorno.</span><span class="sxs-lookup"><span data-stu-id="addcc-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="addcc-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y ejercicios de programación en forma de cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="addcc-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="addcc-136">Los [cuadernos de tutoriales de Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="addcc-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="addcc-137">Quantum Katas es una serie de tutoriales de código abierto autoguiados para la enseñanza de elementos de la computación cuántica y de la programación con Q#.</span><span class="sxs-lookup"><span data-stu-id="addcc-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="addcc-138">Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="addcc-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
