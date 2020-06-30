---
title: Desarrollo con Q# y Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274148"
---
# <a name="develop-with-q-and-python"></a>Desarrollo con Q# y Python

Instale el QDK para desarrollar programas host de Python para llamar a las operaciones de Q#.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - El administrador de paquetes de Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Instale `qsharp`, un paquete de Python que habilita la interoperabilidad entre Q# y Python.

    ```
    pip install qsharp
    ```

1. Instale IQ#, un kernel usado por Jupyter y Python que proporciona funcionalidad básica para compilar y ejecutar operaciones de Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Si recibe un error durante el paso `dotnet iqsharp install`, abra una nueva ventana de terminal e inténtelo de nuevo.
    > Si aún así no funciona, intente buscar la herramienta `dotnet-iqsharp` instalada (en Windows, `dotnet-iqsharp.exe`) y ejecute:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > donde `/path/to/dotnet-iqsharp` debe reemplazarse por la ruta de acceso absoluta a la herramienta `dotnet-iqsharp` en el sistema de archivos.
    > Normalmente, estará en `.dotnet/tools`, en la carpeta de perfil de usuario.
  
1. Aunque puede usar Q# con Python en cualquier IDE, es muy recomendable usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de Q# + Python. El uso de Visual Studio Code y la extensión QDK para Visual Studio Code ofrece acceso a una funcionalidad más completa.

    - Instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).
    - Instale la [extensión QDK para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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

        ```
        python hello_world.py
        ```

    - Compruebe el resultado. El programa debe generar las siguientes líneas:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * También puede usar cuadernos de Jupyter Notebook en Python para escribir el programa clásico en Python y llamar a las operaciones de Q# desde las celdas. El código de Python es un programa normal de Python.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
