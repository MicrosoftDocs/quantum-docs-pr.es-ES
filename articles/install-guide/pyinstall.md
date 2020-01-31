---
title: 'Desarrollo con Q # + Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831008"
---
# <a name="develop-with-q--python"></a>Desarrollo con Q # + Python

Instale QDK para desarrollar programas host de Python para llamar a las operaciones de Q #.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK de .NET Core 3,1 o posterior](https://www.microsoft.com/net/download)


1. Instale el paquete de `qsharp`, un paquete de Python que habilita la interoperabilidad entre Q # y Python.

    ```bash
    pip install qsharp
    ```

1. Instale `iqsharp`, un kernel usado por Jupyter y Python que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q #.

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

## <a name="whats-next"></a>¿Qué es lo próximo?

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).
