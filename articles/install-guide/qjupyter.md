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
# <a name="develop-with-q-jupyter-notebooks"></a>Desarrollo con cuadernos de preguntas # Jupyter

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

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Ejecute el siguiente comando para iniciar el servidor de cuadernos:

        ```bash
        jupyter notebook
        ```

    - Para abrir la copia del cuaderno de Jupyter Notebook y pegar la dirección URL proporcionada por la línea de comandos en el explorador.

    - Cree un cuaderno de Jupyter Notebook con un kernel de Q# y agregue el código siguiente a la primera celda del cuaderno:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Ejecute esta celda del cuaderno:

        ![Celda de cuaderno de Jupyter Notebook con código de Q#](~/media/install-guide-jupyter.png)

        Debe aparecer `SayHello` en la salida de la celda. Cuando se ejecuta en cuadernos de Jupyter Notebook, se compila el código de Q# y la salida del cuaderno es el nombre de las operaciones que encuentra.


    - En una nueva celda, ejecute la operación que acaba de crear (en un simulador) mediante el `%simulate` comando:

        ![Celda de cuaderno de Jupyter Notebook con el magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Debería ver el mensaje impreso en la pantalla junto con el resultado de la operación invocada (aquí, vemos la tupla vacía `()` porque nuestra operación devuelve simplemente un `Unit` tipo).

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
