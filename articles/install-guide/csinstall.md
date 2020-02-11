---
title: Desarrollo con preguntas y respuestasC#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036294"
---
# <a name="develop-with-q--c"></a>Desarrollo con preguntas y respuestasC#

Instale QDK para desarrollar C# programas host para llamar a las operaciones de Q #.

Q # se ha creado para experimentar bien con los lenguajes de C#.net, específicamente. Puede trabajar con este emparejamiento en entornos de desarrollo diferentes:

- [Q # + C# con Visual Studio (Windows)](#VS)
- [P # + C# uso de Visual Studio Code (Windows, Linux y Mac)](#VSC)
- [Q # + C# con la herramienta de línea de comandos `dotnet`](#command)

## Desarrollo con Q # + C# mediante Visual Studio <a name="VS"></a>

Visual Studio ofrece un entorno completo para desarrollar programas de preguntas y respuestas. La extensión de preguntas y respuestas de Visual Studio contiene plantillas para los proyectos y archivos de preguntas y respuestas, así como el resaltado de sintaxis, la finalización de código y la compatibilidad con IntelliSense.


1. Requisitos previos

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.

1. Instale la extensión de Visual Studio para Q#.

    - Descarga e instalación de la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Creación de una aplicación de Q#

        - Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.
        - Escriba `Q#` en el cuadro de búsqueda.
        - Seleccione **Q# Application** (Aplicación de Q#)
        - Seleccione **Siguiente**.
        - Elija un nombre y una ubicación para su aplicación.
        - Seleccione **Crear**

    - Inspección del proyecto

        Debería ver que se han creado dos archivos: `Driver.cs`, que es la aplicación host en C# y `Operation.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.

    - Ejecución de la aplicación

        - Seleccione **Depurar** -> **Iniciar sin depurar**
        - Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.

> [!NOTE]
> * Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  

## Desarrollo con Q # + C# mediante Visual Studio Code <a name="VSC"></a>

Visual Studio Code (VS Code) ofrece un entorno completo para desarrollar programas de preguntas y respuestas en Windows, Linux y Mac.  La extensión Q # VS Code incluye compatibilidad con el resaltado de sintaxis Q #, la finalización de código y los fragmentos de código de Q #.

1. Requisitos previos

   - [Código de VS](https://code.visualstudio.com/download)
   - [SDK de .NET Core 3,1 o posterior](https://www.microsoft.com/net/download)

1. Instale la extensión de VS Code para Quantum.

    - Instale la [extensión de VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Instale las plantillas de proyecto de Quantum:

   - Vaya a **Ver** -> **Paleta de comandos**.
   - Seleccionar **Q #: instalar plantillas de proyecto**

    Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Cree un nuevo proyecto:

        - Vaya a **Ver** -> **Paleta de comandos**.
        - Seleccione **Q #: crear nuevo proyecto**
        - Seleccionar **aplicación de consola independiente**
        - Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.
        - Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.

    - Si aún no tiene instalada la C# extensión de vs Code, aparecerá una ventana emergente. Instale la extensión. 

    - Ejecute la aplicación:

        - Ir a **terminal** -> **nuevo terminal**
        - escriba `dotnet run`.
        - Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.


> [!NOTE]
> * No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code. Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

## Desarrollo con Q # + C# mediante la herramienta de línea de comandos `dotnet` <a name="command"></a>

Por supuesto, también puede compilar y ejecutar programas de Q# desde la línea de comandos, simplemente instalando las plantillas de proyecto del SDK de .NET Core y QDK. 

1. Requisitos previos

    - [SDK de .NET Core 3,1 o posterior](https://www.microsoft.com/net/download)

1. Instale las plantillas de proyecto de Quantum para .NET.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.

1. Cree una aplicación `Hello World` para comprobar la instalación.

    - Creación de una aplicación

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Vaya al nuevo directorio de la aplicación.

       ```bash
       cd runSayHello
       ```

    Debería ver que se han creado dos archivos junto con los archivos de proyecto de la aplicación: un archivo de Q# (`Operation.qs`) y un archivo host de C# (`Driver.cs`).

    - Ejecución de la aplicación

        ```dotnetcli
        dotnet run
        ```

        Debería ver la siguiente salida: `Hello quantum world!`.

    
## <a name="whats-next"></a>¿Qué sigue?

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).
