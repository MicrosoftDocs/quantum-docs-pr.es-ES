---
title: Desarrollo con Q# y Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660759"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="ae725-102">Desarrollo con Q# y Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ae725-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="ae725-103">Instale QDK para desarrollar operaciones de Q # en cuadernos de preguntas # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="ae725-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="ae725-104">Los cuadernos de Jupyter Notebook permiten la ejecución de código en contexto junto con instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="ae725-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="ae725-105">Este entorno es idóneo para escribir un código de Q # con explicaciones incrustadas o tutoriales interactivos de Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="ae725-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="ae725-106">Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.</span><span class="sxs-lookup"><span data-stu-id="ae725-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="ae725-107">IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="ae725-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="ae725-108">En los cuadernos de Jupyter de preguntas y respuestas, solo puede ejecutar el código de Q # y no es posible llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#).</span><span class="sxs-lookup"><span data-stu-id="ae725-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="ae725-109">Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="ae725-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="ae725-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ae725-110">Pre-requisites</span></span>

    - <span data-ttu-id="ae725-111">[Python](https://www.python.org/downloads/) 3,6 o posterior</span><span class="sxs-lookup"><span data-stu-id="ae725-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="ae725-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ae725-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="ae725-113">SDK de .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="ae725-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="ae725-114">Instalar el paquete `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="ae725-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ae725-115">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ae725-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ae725-116">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="ae725-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="ae725-117">Para abrir el Jupyter Notebook, copie y pegue la dirección URL proporcionada por la línea de comandos en el explorador.</span><span class="sxs-lookup"><span data-stu-id="ae725-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="ae725-118">Cree un Jupyter Notebook con un kernel de Q # y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="ae725-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="ae725-119">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="ae725-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook celda con código de Q #](~/media/install-guide-jupyter.png)

        <span data-ttu-id="ae725-121">Debe aparecer `SayHello` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="ae725-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="ae725-122">Cuando se ejecuta en Jupyter Notebook, se compila el código de Q # y el Bloc de notas da como resultado el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="ae725-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="ae725-123">En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="ae725-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook celda con% de simulación mágica](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="ae725-125">Debería ver el mensaje impreso en la pantalla junto con el resultado de la operación invocada (aquí, vemos la tupla vacía `()` porque nuestra operación devuelve simplemente un `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="ae725-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae725-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ae725-126">Next steps</span></span>

<span data-ttu-id="ae725-127">Ahora que ha instalado el QDK para los cuadernos de Q # Jupyter, puede escribir y ejecutar [el primer programa Quantum](xref:microsoft.quantum.quickstarts.qrng) escribiendo el código de preguntas y respuestas directamente en el entorno de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="ae725-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="ae725-128">Para obtener más ejemplos de lo que puede hacer con los cuadernos de preguntas # Jupyter, eche un vistazo a:</span><span class="sxs-lookup"><span data-stu-id="ae725-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="ae725-129">[Introducción a Q # y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="ae725-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="ae725-130">Allí encontrará un Jupyter Notebook de preguntas y respuestas en el que se muestra cómo usar Q # en este entorno.</span><span class="sxs-lookup"><span data-stu-id="ae725-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="ae725-131">[Quantum katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y conjuntos de ejercicios de programación en forma de cuadernos de preguntas # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="ae725-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="ae725-132">Los [cuadernos de tutoriales de Quantum katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="ae725-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="ae725-133">El katas Quantum se destina a la enseñanza de elementos de Quantum Computing y la programación de Q # al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ae725-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="ae725-134">Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos de preguntas # Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="ae725-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
