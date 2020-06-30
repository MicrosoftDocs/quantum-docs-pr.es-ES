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
# <a name="develop-with-q-jupyter-notebooks"></a>Desarrollo con cuadernos en Q# de Jupyter Notebook

Instale el QDK para desarrollar operaciones de Q# en cuadernos en Q# de Jupyter Notebook.

Jupyter Notebook permite la ejecución de código en contexto junto con instrucciones, notas y otro contenido. Este entorno es idóneo para escribir código de Q# con explicaciones insertadas o tutoriales interactivos sobre computación cuántica. Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.

IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.

> [!NOTE]
> * En los cuadernos en Q# de Jupyter Notebook solo se puede ejecutar código de Q# y no se puede llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#). Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa cuántico.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3.6 o versiones posteriores
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalar el paquete `iqsharp`

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

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Ejecute el siguiente comando para iniciar el servidor de cuadernos:

        ```
        jupyter notebook
        ```

    - Para abrir el cuaderno de Jupyter Notebook, copie y pegue en el explorador la dirección URL proporcionada por la línea de comandos.

    - Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Ejecute esta celda del cuaderno:

        ![Celda del cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        Debe aparecer `SayHello` en la salida de la celda. Cuando se ejecuta en cuadernos de Jupyter Notebook, el código de Q# se compila y la salida del cuaderno es el nombre de las operaciones que encuentra.


    - En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el comando `%simulate`:

        ![Celda del cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Verá el mensaje en pantalla junto con el resultado de la operación invocada. En este caso, vemos la tupla vacía `()` porque nuestra operación simplemente devuelve un tipo `Unit`.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado el QDK para los cuadernos en Q# de Jupyter Notebook, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng) escribiendo código de Q# directamente en el entorno de Jupyter Notebook.

Para ver más ejemplos de lo que puede hacer con los cuadernos en Q# de Jupyter Notebook, eche un vistazo a:
- [Introducción a Q# y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Allí encontrará un cuaderno en Q# de Jupyter Notebook que muestra cómo usar Q# en este entorno.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y ejercicios de programación en forma de cuadernos en Q# de Jupyter Notebook. Los [cuadernos de tutoriales de Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida. Quantum Katas es una serie de tutoriales de código abierto autoguiados para la enseñanza de elementos de la computación cuántica y de la programación con Q#. Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos en Q# de Jupyter Notebook.
