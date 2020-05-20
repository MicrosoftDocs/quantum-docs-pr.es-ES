---
title: Desarrollo con preguntas y respuestas de Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 35499daae0cd0ae329e39b43b0d8dd5a00183871
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660736"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="20b49-102">Desarrollo con preguntas y respuestas de Python</span><span class="sxs-lookup"><span data-stu-id="20b49-102">Develop with Q# and Python</span></span>

<span data-ttu-id="20b49-103">Instale QDK para desarrollar programas host de Python para llamar a las operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="20b49-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="20b49-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="20b49-104">Pre-requisites</span></span>

    - <span data-ttu-id="20b49-105">[Python](https://www.python.org/downloads/) 3,6 o posterior</span><span class="sxs-lookup"><span data-stu-id="20b49-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="20b49-106">El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="20b49-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="20b49-107">SDK de .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="20b49-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="20b49-108">Instale el `qsharp` paquete, un paquete de Python que habilita la interoperabilidad entre Q # y Python.</span><span class="sxs-lookup"><span data-stu-id="20b49-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="20b49-109">Instale IQ #, un kernel usado por Jupyter y Python que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="20b49-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="20b49-110">Aunque puede usar Q # con Python en cualquier IDE, se recomienda encarecidamente usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de preguntas y respuestas de Python # +.</span><span class="sxs-lookup"><span data-stu-id="20b49-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="20b49-111">Mediante el uso de Visual Studio Code y la extensión de Visual Studio Code QDK obtiene acceso a una funcionalidad más enriquecida.</span><span class="sxs-lookup"><span data-stu-id="20b49-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="20b49-112">Instalación de [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac)</span><span class="sxs-lookup"><span data-stu-id="20b49-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="20b49-113">Instale la [extensión QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="20b49-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="20b49-114">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="20b49-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="20b49-115">Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:</span><span class="sxs-lookup"><span data-stu-id="20b49-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="20b49-116">Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="20b49-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="20b49-117">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="20b49-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="20b49-118">Compruebe el resultado.</span><span class="sxs-lookup"><span data-stu-id="20b49-118">Verify the output.</span></span> <span data-ttu-id="20b49-119">El programa debe generar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="20b49-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="20b49-120">También puede usar cuadernos de Jupyter de Python para escribir el programa de Python clásico y llamar a las operaciones de Q # desde las celdas.</span><span class="sxs-lookup"><span data-stu-id="20b49-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="20b49-121">El código de Python es simplemente un programa de Python normal.</span><span class="sxs-lookup"><span data-stu-id="20b49-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20b49-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20b49-122">Next steps</span></span>

<span data-ttu-id="20b49-123">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="20b49-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
