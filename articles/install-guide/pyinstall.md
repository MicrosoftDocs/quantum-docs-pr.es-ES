---
title: Desarrollo con preguntas y respuestas de Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630289"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="4a997-102">Desarrollo con preguntas y respuestas de Python</span><span class="sxs-lookup"><span data-stu-id="4a997-102">Develop with Q# and Python</span></span>

<span data-ttu-id="4a997-103">Instale QDK para desarrollar programas host de Python para llamar a las operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="4a997-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="4a997-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4a997-104">Prerequisites</span></span>

    - <span data-ttu-id="4a997-105">[Python](https://www.python.org/downloads/) 3,6 o posterior</span><span class="sxs-lookup"><span data-stu-id="4a997-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="4a997-106">El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="4a997-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="4a997-107">SDK de .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="4a997-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="4a997-108">Instale el `qsharp` paquete, un paquete de Python que habilita la interoperabilidad entre Q # y Python.</span><span class="sxs-lookup"><span data-stu-id="4a997-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="4a997-109">Instale IQ #, un kernel usado por Jupyter y Python que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="4a997-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="4a997-110">Si recibe un error durante el `dotnet iqsharp install` paso, abra una nueva ventana de terminal e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4a997-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="4a997-111">Si esto sigue sin funcionar, intente buscar la herramienta instalada `dotnet-iqsharp` (en Windows, `dotnet-iqsharp.exe` ) y en ejecución:</span><span class="sxs-lookup"><span data-stu-id="4a997-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="4a997-112">donde `/path/to/dotnet-iqsharp` debe reemplazarse por la ruta de acceso absoluta a la `dotnet-iqsharp` herramienta en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="4a997-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="4a997-113">Normalmente, estará en `.dotnet/tools` la carpeta del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a997-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="4a997-114">Aunque puede usar Q # con Python en cualquier IDE, se recomienda encarecidamente usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de preguntas y respuestas de Python # +.</span><span class="sxs-lookup"><span data-stu-id="4a997-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="4a997-115">Mediante el uso de Visual Studio Code y la extensión de Visual Studio Code QDK obtiene acceso a una funcionalidad más enriquecida.</span><span class="sxs-lookup"><span data-stu-id="4a997-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="4a997-116">Instalación de [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac)</span><span class="sxs-lookup"><span data-stu-id="4a997-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="4a997-117">Instale la [extensión QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="4a997-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="4a997-118">Cree una aplicación `Hello World` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="4a997-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4a997-119">Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:</span><span class="sxs-lookup"><span data-stu-id="4a997-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="4a997-120">Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="4a997-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="4a997-121">Ejecute el programa:</span><span class="sxs-lookup"><span data-stu-id="4a997-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="4a997-122">Compruebe el resultado.</span><span class="sxs-lookup"><span data-stu-id="4a997-122">Verify the output.</span></span> <span data-ttu-id="4a997-123">El programa debe generar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="4a997-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="4a997-124">También puede usar cuadernos de Jupyter de Python para escribir el programa de Python clásico y llamar a las operaciones de Q # desde las celdas.</span><span class="sxs-lookup"><span data-stu-id="4a997-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="4a997-125">El código de Python es simplemente un programa de Python normal.</span><span class="sxs-lookup"><span data-stu-id="4a997-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a997-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4a997-126">Next steps</span></span>

<span data-ttu-id="4a997-127">Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="4a997-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
