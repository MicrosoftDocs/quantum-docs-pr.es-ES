---
title: Desarrollo con Q# y Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577827"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Desarrollo con Q# y Jupyter Notebook

Instale QDK para desarrollar operaciones de Q # en cuadernos de preguntas # Jupyter.

Los cuadernos de Jupyter Notebook permiten la ejecución de código en contexto junto con instrucciones, notas y otro contenido. Este entorno es idóneo para escribir un código de Q # con explicaciones incrustadas o tutoriales interactivos de Quantum Computing. Esto es lo que tiene que hacer para empezar a crear sus propios cuadernos de Q#.

IQ# (pronunciado i-q-sharp) es una extensión del SDK de .NET Core usada principalmente por Jupyter y Python que proporciona funcionalidad básica para compilar y simular operaciones de Q#.

> [!NOTE]
> * En los cuadernos de Jupyter de preguntas y respuestas, solo puede ejecutar el código de Q # y no es posible llamar a las operaciones desde programas host externos (por ejemplo, archivos de Python o C#). Este entorno no es adecuado si su objetivo es combinar un programa host clásico externo con el programa Quantum.

1. Requisitos previos

    - [Python](https://www.python.org/downloads/) 3,6 o posterior
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalar el paquete `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Ejecute el siguiente comando para iniciar el servidor de cuadernos:

        ```
        jupyter notebook
        ```

    - Para abrir el Jupyter Notebook, copie y pegue la dirección URL proporcionada por la línea de comandos en el explorador.

    - Cree un Jupyter Notebook con un kernel de Q # y agregue el código siguiente a la primera celda del cuaderno:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Ejecute esta celda del cuaderno:

        ![Jupyter Notebook celda con código de Q #](~/media/install-guide-jupyter.png)

        Debe aparecer `SayHello` en la salida de la celda. Cuando se ejecuta en Jupyter Notebook, se compila el código de Q # y el Bloc de notas da como resultado el nombre de las operaciones que encuentra.


    - En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el `%simulate` comando:

        ![Jupyter Notebook celda con% de simulación mágica](~/media/install-guide-jupyter-simulate.png)

        Debería ver el mensaje impreso en la pantalla junto con el resultado de la operación invocada (aquí, vemos la tupla vacía `()` porque nuestra operación devuelve simplemente un `Unit` tipo).

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado el QDK para los cuadernos de Q # Jupyter, puede escribir y ejecutar [el primer programa Quantum](xref:microsoft.quantum.quickstarts.qrng) escribiendo el código de preguntas y respuestas directamente en el entorno de Jupyter Notebook.

Para obtener más ejemplos de lo que puede hacer con los cuadernos de preguntas # Jupyter, eche un vistazo a:
- [Introducción a Q # y Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Allí encontrará un Jupyter Notebook de preguntas y respuestas en el que se muestra cómo usar Q # en este entorno.
- [Quantum katas](xref:microsoft.quantum.overview.katas), una colección de código abierto de tutoriales autoguiados y conjuntos de ejercicios de programación en forma de cuadernos de preguntas # Jupyter. Los [cuadernos de tutoriales de Quantum katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) son un buen punto de partida. El katas Quantum se destina a la enseñanza de elementos de Quantum Computing y la programación de Q # al mismo tiempo. Son un ejemplo excelente del tipo de contenido que se puede crear con cuadernos de preguntas # Jupyter Notebook.
