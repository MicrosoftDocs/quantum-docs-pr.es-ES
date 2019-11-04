---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185858"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Actualización del Microsoft Quantum Development Kit (QDK)

Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.

En este artículo se da por supuesto que ya tiene el QDK instalado. Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).

Los pasos de actualización dependen de su entorno de desarrollo. Elija el entorno en las secciones siguientes.

## <a name="python"></a>Python

1. Actualización del kernel de `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Comprobar la versión de `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Debería ver la siguiente salida:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Actualizar el paquete de `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Comprobar la versión de `qsharp`

    ```bash
    pip show qsharp
    ```

    Debería ver la siguiente salida:

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.

## <a name="jupyter-notebooks"></a>Jupyter Notebook

1. Actualización del kernel de `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Comprobar la versión de `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Debería ver la siguiente salida:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.

## <a name="c-on-windows-using-visual-studio"></a>C#en Windows con Visual Studio

1. Actualización de la extensión de preguntas y respuestas de Visual Studio

    - Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .
    - Aceptar la actualización

    > [!NOTE]
    > Las plantillas de proyecto se actualizan con la extensión. Las plantillas actualizadas solo se aplican a los proyectos recién creados. El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.

1. Actualización de los paquetes de QDK

    - Abrir una aplicación existente
    - Seleccione las **dependencias** en el explorador de soluciones
    - Seleccione **administrar paquetes NuGet** .
    - Actualización de los paquetes de **Microsoft. Quantum** a la versión más reciente

1. Ahora puede ejecutar la aplicación con el QDK más reciente.

## <a name="c-using-vs-code"></a>C#, mediante VS Code

1. Actualización de la extensión de VS Code Quantum

    - Reiniciar VS Code
    - Vaya a la pestaña **extensiones** .
    - Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code
    - Recarga de la extensión

1. Actualice las plantillas de proyecto Quantum:

   - Ir a **vista** -> **paleta de comandos**
   - Seleccionar **Q #: instalar plantillas de proyecto**

1. Abra una aplicación existente en VS Code

   - Edite el archivo. csproj para agregar las nuevas versiones del paquete

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Si usa otros paquetes de `Microsoft.Quantum`, también puede actualizarlos.

1. Ahora puede ejecutar la aplicación con el QDK actualizado

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, mediante la herramienta de línea de comandos `dotnet`

1. Actualización de las plantillas de proyecto Quantum para .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Actualización y ejecución de una aplicación existente

    - Actualización de las versiones del paquete QDK en la aplicación

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Si la aplicación usa cualquier otro paquete de `Microsoft.Quantum`, actualícelo también.

    - Ejecución de la aplicación

        ```bash
        dotnet run
        ```

    - La aplicación se ejecutará con las nuevas versiones del paquete

## <a name="whats-next"></a>¿Qué es lo próximo?

Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum. Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).
