---
title: Desarrollo con Q# y Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885538"
---
# <a name="develop-with-q-and-python"></a>Desarrollo con Q# y Python

Instale el QDK para desarrollar programas host de Python para llamar a las operaciones de Q#.

## <a name="install-the-qsharp-python-package"></a>Instalación del paquete `qsharp` de Python

### <a name="install-using-conda-recommended"></a>[Instalación mediante Conda (recomendado)](#tab/tabid-conda)

1. Instale [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads).

1. Abra un símbolo del sistema de Anaconda.

   - O bien, si prefiere usar PowerShell o pwsh, abra un shell, ejecute `conda init powershell`, luego cierre y vuelva a abrir el shell.

1. Cree y active un nuevo entorno de Conda llamado `qsharp-env` con los paquetes necesarios (incluidos Jupyter Notebook e IQ#) mediante la ejecución de los siguientes comandos:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Ejecute `python -c "import qsharp"` desde el mismo terminal para comprobar la instalación y rellenar la memoria caché del paquete local con todos los componentes del QDK necesarios.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Instalación mediante la CLI de .NET y PIP (avanzado)](#tab/tabid-dotnetcli)

1. Requisitos previos:

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
    
***

Eso es todo. Ahora tiene el paquete `qsharp` de Python y el kernel de IQ# para Jupyter, que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q# desde Python y permite usar cuadernos de Jupyter en Q#.

## <a name="choose-your-ide"></a>Elija el IDE

Aunque puede usar Q# con Python en cualquier IDE, es muy recomendable usar el IDE de Visual Studio Code (VS Code) para las aplicaciones de Q# + Python. La extensión QDK para Visual Studio Code ofrece acceso a una funcionalidad más completa, como advertencias, resaltado de sintaxis, plantillas de proyecto, etc.

Si desea usar VS Code:

- Instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).
- Instale la [extensión QDK para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Si quiere usar un editor diferente, siga las instrucciones anteriores.

## <a name="write-your-first-q-program"></a>Escritura del primer programa de Q#

Ahora ya puede comprobar la instalación del paquete `qsharp` de Python; para ello, escriba y ejecute un sencillo programa de Q#.

1. Cree una operación mínima de Q#; para ello, cree un archivo llamado `Operation.qs` y añádale el siguiente código:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. En la misma carpeta que `Operation.qs`, cree un programa de Python llamado `host.py` para simular la operación `SampleQuantumRandomNumberGenerator()` de Q#:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. Desde el entorno que creó durante la instalación (es decir, el entorno Conda o Python en el que instaló `qsharp`), ejecute el programa:

    ```
    python host.py
    ```

1. Verá el resultado de la operación que ha invocado. En este caso, como la operación genera un resultado aleatorio, verá `Zero` o `One` en la pantalla. Si ejecuta el programa varias veces, verá cada resultado aproximadamente la mitad del tiempo.

> [!NOTE]
> * El código de Python es un programa normal de Python. Puede usar cualquier entorno de Python, incluidos cuadernos en Python de Jupyter Notebook, para escribir el programa de Python y llamar a las operaciones de Q#. El programa de Python puede importar las operaciones de Q# desde cualquier archivo .qs situado en la misma carpeta que el código de Python.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado el kit de desarrollo de Microsoft Quantum en su entorno preferido, siga este tutorial para escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
