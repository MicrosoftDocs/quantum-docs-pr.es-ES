---
title: 'Desarrollo con cuadernos de preguntas # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551046"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="cdcf4-102">Desarrollo con cuadernos de preguntas # Jupyter</span><span class="sxs-lookup"><span data-stu-id="cdcf4-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="cdcf4-103">Instale QDK para desarrollar operaciones de Q # en cuadernos de preguntas # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="cdcf4-104">Los cuadernos de Jupyter Notebook permiten la ejecución de código en contexto junto con instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="cdcf4-105">Este entorno es idóneo para escribir un código de Q # con explicaciones incrustadas o tutoriales interactivos de Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="cdcf4-106">Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="cdcf4-107">IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="cdcf4-108">En los cuadernos de Jupyter de preguntas y respuestas, solo puede ejecutar el código de Q # y no es posible llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#).</span><span class="sxs-lookup"><span data-stu-id="cdcf4-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="cdcf4-109">Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="cdcf4-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cdcf4-110">Pre-requisites</span></span>

    - <span data-ttu-id="cdcf4-111">[Python](https://www.python.org/downloads/) 3,6 o posterior</span><span class="sxs-lookup"><span data-stu-id="cdcf4-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="cdcf4-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="cdcf4-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="cdcf4-113">SDK de .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="cdcf4-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="cdcf4-114">Instalar el paquete `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="cdcf4-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="cdcf4-115">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cdcf4-116">Ejecute el siguiente comando para iniciar el servidor de cuadernos:</span><span class="sxs-lookup"><span data-stu-id="cdcf4-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="cdcf4-117">Para abrir la copia del cuaderno de Jupyter Notebook y pegar la dirección URL proporcionada por la línea de comandos en el explorador.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="cdcf4-118">Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="cdcf4-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="cdcf4-119">Ejecute esta celda del cuaderno:</span><span class="sxs-lookup"><span data-stu-id="cdcf4-119">Run this cell of the notebook:</span></span>

        ![Celda de cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="cdcf4-121">Debe aparecer `SayHello` en la salida de la celda.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="cdcf4-122">Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q# y la salida del cuaderno es el nombre de las operaciones que encuentra.</span><span class="sxs-lookup"><span data-stu-id="cdcf4-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="cdcf4-123">En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="cdcf4-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Celda de cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="cdcf4-125">Debería ver el mensaje impreso en la pantalla junto con el resultado de la operación invocada (aquí, vemos la tupla vacía `()` porque nuestra operación devuelve simplemente un `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="cdcf4-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cdcf4-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cdcf4-126">Next steps</span></span>

<span data-ttu-id="cdcf4-127">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="cdcf4-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
