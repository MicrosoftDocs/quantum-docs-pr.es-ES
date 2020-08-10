---
title: Desarrollo con cuadernos en Q# de Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 10b1faafa70c87a99ea09916e2c386b32f9a570f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866815"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Desarrollo con cuadernos en Q# de Jupyter Notebook

Instale el QDK para desarrollar operaciones de Q# en cuadernos en Q# de Jupyter Notebook.

Jupyter Notebook permite la ejecución de código en contexto junto con instrucciones, notas y otro contenido. Este entorno es idóneo para escribir código de Q# con explicaciones insertadas o tutoriales interactivos sobre computación cuántica. Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.

> [!NOTE]
> * En los cuadernos en Q# de Jupyter Notebook solo se puede ejecutar código de Q#, y no se puede llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#). Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa cuántico.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Instalación del kernel de IQ# para Jupyter

IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.

### <a name="install-using-conda-recommended"></a>[Instalación mediante Conda (recomendado)](#tab/tabid-conda)

1. Instale [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Nota:** Se necesita una instalación de 64 bits.

1. Abra un símbolo del sistema de Anaconda.

   - O bien, si prefiere usar PowerShell o pwsh, abra un shell, ejecute `conda init powershell`, luego cierre y vuelva a abrir el shell.

1. Cree y active un nuevo entorno de Conda llamado `qsharp-env` con los paquetes necesarios (incluidos Jupyter Notebook e IQ#) mediante la ejecución de los siguientes comandos:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Ejecute `python -c "import qsharp"` desde el mismo terminal para comprobar la instalación y rellenar la memoria caché del paquete local con todos los componentes del QDK necesarios.

### <a name="install-using-net-cli-advanced"></a>[Instalación mediante la CLI de .NET (avanzado)](#tab/tabid-dotnetcli)

1. Requisitos previos:

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instale el paquete `Microsoft.Quantum.IQSharp`.

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

Eso es todo. Ahora tiene el kernel de IQ# para Jupyter, que proporciona la funcionalidad básica para compilar y ejecutar operaciones de Q# desde cuadernos en Q# de Jupyter Notebook.

## <a name="create-your-first-no-locq-notebook"></a>Creación del primer cuaderno de Q#

Ahora ya puede comprobar la instalación del cuaderno en Q# de Jupyter Notebook; para ello, escriba y ejecute una sencilla operación de Q#.

1. En el entorno que creó durante la instalación (es decir, en el entorno de Conda que creó, o en el entorno de Python donde instaló Jupyter), ejecute el siguiente comando para iniciar el servidor de Jupyter Notebook:

    ```
    jupyter notebook
    ```

    - Si el cuaderno de Jupyter Notebook no se abre automáticamente en su explorador, copie y pegue en el explorador la dirección URL proporcionada por la línea de comandos.

1. Seleccione "Nuevo" → "Q#" para crear un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Ejecute esta celda del cuaderno:

    ![Celda del cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

    Debe aparecer `SampleQuantumRandomNumberGenerator` en la salida de la celda. Cuando se ejecuta en cuadernos de Jupyter Notebook, el código de Q# se compila y la salida de la celda es el nombre de las operaciones que encuentra.

1. En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el comando `%simulate`:

    ![Celda del cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Verá el resultado de la operación que ha invocado. En este caso, como la operación genera un resultado aleatorio, verá `Zero` o `One` en la pantalla. Si ejecuta la celda varias veces, verá cada resultado aproximadamente la mitad del tiempo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado el QDK para los cuadernos en Q# de Jupyter Notebook, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng) escribiendo código de Q# directamente en el entorno de Jupyter Notebook.

Para ver más ejemplos de lo que puede hacer con los cuadernos en Q# de Jupyter Notebook, eche un vistazo a:

- [Introducción a Q# y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Ahí encontrará un cuaderno en Q# de Jupyter Notebook con más información sobre cómo usar Q# en el entorno de Jupyter.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y ejercicios de programación en forma de cuadernos en Q# de Jupyter Notebook. Los [cuadernos de tutoriales de Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida. Quantum Katas es una serie de tutoriales de código abierto autoguiados para la enseñanza de elementos de la computación cuántica y de la programación con Q#. Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos en Q# de Jupyter Notebook.
