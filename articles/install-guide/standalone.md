---
title: 'Ejecutar programas Q # sin un controlador y un idioma host'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706808"
---
# <a name="q-command-line-applications"></a>Aplicaciones de línea de comandos de Q #

Los programas de preguntas y respuestas se pueden ejecutar por sí solos, sin un controlador en un lenguaje de host como C#, F # o Python.

## <a name="pre-requisites"></a>Requisitos previos

- [SDK de .NET Core 3.1 o posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalación

Aunque puede compilar aplicaciones de línea de comandos de Q # en cualquier IDE, se recomienda encarecidamente usar Visual Studio Code (VS Code) o el IDE de Visual Studio para las aplicaciones de preguntas y respuestas. Con VS Code o Visual Studio y la extensión de Visual Studio Code de QDK obtiene acceso a una funcionalidad más enriquecida.

- Instalación de [vs Code](https://code.visualstudio.com/download) (Windows, Linux y Mac)
- Instale la [extensión QDK para vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) o
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 con la carga de trabajo de desarrollo multiplataforma de .NET Core habilitada.
- Descarga e instalación de la [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Desarrollo con Q # usando VS Code

Instale las plantillas de proyecto de Quantum:

- Ir a **Ver** -> **paleta de comandos**
- Seleccionar **Q #: instalar plantillas de proyecto**

Ahora ya tiene Quantum Development Kit instalado y listo para usarse en sus propias aplicaciones y bibliotecas.
- Cree un nuevo proyecto:
  - Ir a **Ver** -> **paleta de comandos**
  - Seleccione **Q #: crear nuevo proyecto**
  - Seleccionar **aplicación de consola independiente**
  - Vaya a la ubicación del sistema de archivos en la que desea crear la aplicación.
  - Haga clic en el botón **Open new project...** (Abrir nuevo proyecto), una vez creado el proyecto.
        
- Inspección del proyecto
  - Debería ver que se ha creado un `Program.qs` archivo llamado Created, que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.

- Ejecute la aplicación:
  - Ir a **Terminal** -> terminal**New** terminal
  - Escriba `dotnet run`.
  - Debería ver el texto siguiente en la ventana de salida: `Hello quantum world!`.


> [!NOTE]
> * No se admiten actualmente áreas de trabajo con varias carpetas raíz en la extensión de Visual Studio Code. Si tiene varios proyectos en un área de trabajo VS Code, todos los proyectos deben estar contenidos en la misma carpeta raíz.

## <a name="develop-with-q-using-visual-studio"></a>Desarrollo con Q # usando Visual Studio

Cree una aplicación `Hello World` para comprobar la instalación.

- Creación de una aplicación de Q#
  - Ir a **archivo** -> **nuevo** -> **proyecto**
  - Escriba `Q#` en el cuadro de búsqueda.
  - Seleccione **Q# Application** (Aplicación de Q#)
  - Seleccione **Siguiente**.
  - Elija un nombre y una ubicación para su aplicación.
  - Seleccione **Crear**

- Inspección del proyecto
  - Debería ver que se ha creado un `Program.qs` archivo llamado, que es un programa de preguntas y respuestas que define una operación sencilla para imprimir un mensaje en la consola.

- Ejecución de la aplicación
  - Seleccione **depurar** -> **iniciar sin depurar**
  - Debería ver el texto `Hello quantum world!` impreso en una ventana de la consola.

> [!NOTE]
> * Si tiene varios proyectos en una solución de Visual Studio, todos los proyectos contenidos en ella deben estar en la misma carpeta que la solución o en una de sus subcarpetas.  


## <a name="whats-next"></a>Pasos adicionales

Ahora que ha instalado Quantum Development Kit en su entorno preferido, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.write-program).
