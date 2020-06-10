---
title: 'Desarrollo con aplicaciones de línea de comandos de Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630275"
---
# <a name="develop-with-q-command-line-applications"></a>Desarrollo con aplicaciones de línea de comandos de Q #

Los programas de preguntas y respuestas se pueden ejecutar por sí solos, sin un controlador en un lenguaje de host como C#, F # o Python.

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.1 o posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalación

Aunque puede compilar aplicaciones de línea de comandos de Q # en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de preguntas y respuestas. El desarrollo en estas herramientas proporciona acceso a una funcionalidad enriquecida.

Para configurar VS Code:

1. Descargue e instale [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).
2. Instale [Microsoft QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Para configurar Visual Studio:

1. Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 o una versión posterior, con la carga de trabajo de desarrollo multiplataforma de .net Core habilitada.
2. Descargue e instale [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Desarrollo con Q # usando VS Code

Instale las plantillas de proyecto de Q #:

1. Abra VS Code.
2. Haga clic en **Ver**  ->  **paleta de comandos**.
3. Seleccione **Q #: instalar plantillas de proyecto**.

Cuando **las plantillas de proyecto se instalan correctamente** , el QDK está listo para usarse con sus propias aplicaciones y bibliotecas.

Para crear un nuevo proyecto:

1. Haga clic en **Ver**  ->  **paleta de comandos** y seleccione **Q #: crear nuevo proyecto**.
2. Haga clic en **aplicación de consola independiente**.
3. Navegue hasta la ubicación donde desea guardar el proyecto y haga clic en **crear proyecto**.
4. Cuando el proyecto se haya creado correctamente, haga clic en **abrir nuevo proyecto...** en la parte inferior derecha.
        
Inspeccione el proyecto. Debería ver un archivo de código fuente denominado `Program.qs` , que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.

Para ejecutar la aplicación:
1. Haga **clic en terminal**  ->  **nuevo**terminal.
2. En el símbolo del sistema de terminal, escriba `dotnet run` .
3. Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.


> [!NOTE]
> Las áreas de trabajo con varias carpetas raíz no se admiten actualmente en la extensión VS Code Q #. Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

## <a name="develop-with-q-using-visual-studio"></a>Desarrollo con Q # usando Visual Studio

Compruebe la instalación de Visual Studio mediante la creación de una aplicación de preguntas y respuestas `Hello World` .

Para crear una nueva aplicación de Q #:
1. Abra Visual Studio y haga clic en **archivo**  ->  **nuevo**  ->  **proyecto**.
2. Escriba `Q#` en el cuadro de búsqueda, seleccione la **aplicación de Q #** y haga clic en **siguiente**.
3. Escriba un nombre y una ubicación para la aplicación y haga clic en **crear**.


Inspeccione el proyecto. Debería ver un archivo de código fuente denominado `Program.qs` , que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.

Para ejecutar la aplicación:
1. Seleccione **depurar**  ->  **iniciar sin depurar**.
2. Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.

> [!NOTE]
> Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en la solución deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  


## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
