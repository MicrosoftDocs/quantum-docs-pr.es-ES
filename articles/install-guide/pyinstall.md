---
title: Desarrollo con preguntas y respuestas de Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: a8c5b9c25c069f98ef8eefd6cfbc36bf3376931c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426360"
---
# <a name="develop-with-q-and-python"></a>Desarrollo con preguntas y respuestas de Python

Instale QDK para desarrollar programas host de Python para llamar a las operaciones de Q #.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3,6 o posterior
    - El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK de .NET Core 3.1 o posterior](https://www.microsoft.com/net/download)


1. Instale el `qsharp` paquete, un paquete de Python que habilita la interoperabilidad entre Q # y Python.

    ```bash
    pip install qsharp
    ```

1. Instale IQ #, un kernel usado por Jupyter y Python que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q #.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. Aunque puede usar Q # con Python en cualquier IDE, se recomienda encarecidamente usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de preguntas y respuestas de Python # +. Mediante el uso de Visual Studio Code y la extensión de Visual Studio Code QDK obtiene acceso a una funcionalidad más enriquecida.

    - Instalación de [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac)
    - Instale la [extensión QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` e incorpore el siguiente código a este:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Cree un programa de Python llamado `hello_world.py` para llamar a la operación de Q# `SayHello()`:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Ejecute el programa:

        ```bash
        python hello_world.py
        ```

    - Compruebe el resultado. El programa debe generar las siguientes líneas:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * También puede usar cuadernos de Jupyter de Python para escribir el programa de Python clásico y llamar a las operaciones de Q # desde las celdas. El código de Python es simplemente un programa de Python normal.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
