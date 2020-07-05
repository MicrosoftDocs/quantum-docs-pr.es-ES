---
title: Desarrollo con aplicaciones de línea de comandos de Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884283"
---
# <a name="develop-with-q-command-line-applications"></a>Desarrollo con aplicaciones de línea de comandos de Q#

Los programas de Q# se pueden ejecutar por sí solos, sin un controlador en un lenguaje host como C# , F# o Python.

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.1 o posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalación

Aunque puede compilar aplicaciones de línea de comandos de Q# en cualquier IDE, se recomienda usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de Q#. Estos entornos de desarrollo incluyen la funcionalidad enriquecida de la extensión QDK, como advertencias, resaltado de sintaxis o plantillas de proyecto, entre otras.

Para configurar VS Code:

1. Descargue e instale [VS Code](https://code.visualstudio.com/download) (Windows, Linux y Mac).
2. Instale el [QDK de Microsoft para VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Para configurar Visual Studio:

1. Descargue e instale [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versiones posteriores con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.
2. Descargue e instale el [QDK de Microsoft](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Para instalar el QDK para otro entorno, escriba en la línea de comandos:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Desarrollo con Q#

Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno.

### <a name="vs-code"></a>[Código de VS](#tab/tabid-vscode)

Instale las plantillas de proyecto de Q#:

1. Abra VS Code.
2. Haga clic en **Ver** -> **Paleta de comandos**.
3. Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto).

Cuando se muestre **Project templates installed successfully** (Plantillas de proyecto instaladas correctamente), ya podrá usar el QDK con sus propias aplicaciones y bibliotecas.

Para crear un nuevo proyecto:

1. Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.
2. Haga clic en **Aplicación de consola independiente**.
3. Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.
4. Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.
        
Inspeccione el proyecto. Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.

Para ejecutar la aplicación:
1. Haga clic en **Terminal** -> **Nuevo terminal**.
2. En el símbolo del sistema del terminal, escriba `dotnet run`.
3. Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.


> [!NOTE]
> Actualmente no se admiten áreas de trabajo con varias carpetas raíz en la extensión Q# para Visual Studio Code. Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Cree una aplicación de Q# `Hello World` para comprobar la instalación de Visual Studio.

Para crear una aplicación de Q#:
1. Abra Visual Studio y haga clic en **Archivo** -> **Nuevo** -> **Proyecto**.
2. Escriba `Q#` en el cuadro de búsqueda, seleccione **Aplicación de Q#** y haga clic en **Siguiente**.
3. Especifique un nombre y una ubicación para la aplicación, y haga clic en **Crear**.


Inspeccione el proyecto. Verá un archivo de código fuente llamado `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola.

Para ejecutar la aplicación:
1. Seleccione **Depurar** -> **Iniciar sin depurar**.
2. Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.

> [!NOTE]
> Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  

### <a name="other-editors-with-the-command-line"></a>[Otros editores con la línea de comandos](#tab/tabid-cmdline)

Cree una aplicación `Hello World` de Q# para comprobar su instalación.

1. Cree una aplicación:
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. Vaya al directorio de la aplicación:
    ```dotnetcli
    cd runSayHello
    ```

    El directorio contendrá un archivo `Program.qs`, que es un programa de Q# que define una operación sencilla para imprimir un mensaje en la consola. Puede modificar esta plantilla con un editor de texto y sobrescribirla con sus propias aplicaciones cuánticas. 

3. Ejecute el programa:
    ```dotnetcli
    dotnet run
    ```

4. Verá el siguiente texto impreso: `Hello quantum world!`

***

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
