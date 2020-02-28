---
title: Obtenga información acerca de cómo actualizar el Microsoft Quantum Development Kit (QDK)
description: 'Describe cómo actualizar los proyectos de Q # y el Microsoft Quantum Development Kit a la versión actual.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 264b5640216b2c0a468b625cdef4b9e0123d8b39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904764"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Actualización del Microsoft Quantum Development Kit (QDK)

Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.

En este artículo se da por supuesto que ya tiene el QDK instalado. Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).

Se recomienda mantenerse al día con la versión más reciente de QDK. Siga esta guía de actualización para actualizar a la versión más reciente de QDK. El proceso consta de dos partes:
1. actualización de los proyectos y archivos de preguntas # existentes para alinear el código con cualquier sintaxis actualizada
2. actualización del propio QDK para el entorno de desarrollo elegido 

## <a name="updating-q-projects"></a>Actualizar proyectos de Q # 

Independientemente de si usa C# o Python para hospedar operaciones de q #, siga estas instrucciones para actualizar los proyectos de q #.

1. En primer lugar, compruebe que dispone de la versión más reciente del [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download). Ejecute el siguiente comando en el símbolo del sistema:

    ```dotnetcli
    dotnet --version
    ```

    Compruebe que la salida es `3.1.100` o superior. Si no es así, instale la [versión más reciente](https://dotnet.microsoft.com/download) y vuelva a comprobarlo. A continuación, siga las instrucciones que se indican a continuación en función de la configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).

### <a name="update-q-projects-in-visual-studio"></a>Actualización de proyectos de Q # en Visual Studio
 
1. Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones
2. Abrir la solución en Visual Studio
3. En el menú, seleccione **Compilar** -> **limpiar solución** .
4. En cada uno de los archivos. csproj, actualice la plataforma de destino a `netcoreapp3.0` (o `netstandard2.1` si es un proyecto de biblioteca).
    Es decir, edite las líneas del formulario:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Guardar y cerrar todos los archivos de la solución
6. Seleccione **herramientas** ->  -> de **línea de comandos** **símbolo del sistema para desarrolladores**
7. Para cada proyecto de la solución, ejecute el siguiente comando:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Si los proyectos usan otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.
8. Cierre el símbolo del sistema y seleccione **Compilar** -> **compilar solución** ( *no* seleccione recompilar solución).

Ahora puede continuar con [la actualización de la extensión QDK de Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Actualizar proyectos de Q # en Visual Studio Code

1. En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.
2. Seleccionar **terminal** -> **nuevo terminal**
3. Siga las instrucciones para la actualización mediante la línea de comandos (directamente a continuación).

### <a name="update-q-projects-using-the-command-line"></a>Actualización de proyectos de Q # mediante la línea de comandos

1. Navegue hasta la carpeta que contiene el archivo de proyecto.
2. Ejecute el siguiente comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. En cada uno de los archivos. csproj, actualice la plataforma de destino a `netcoreapp3.0` (o `netstandard2.1` si es un proyecto de biblioteca).
    Es decir, edite las líneas del formulario:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Ejecute el siguiente comando:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Si el proyecto usa otros paquetes Microsoft. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute también el comando.
5. Guarde y cierre todos los archivos.
6. Repita 1-4 para cada dependencia del proyecto y, a continuación, vuelva a la carpeta que contiene el proyecto principal y ejecute:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Con los proyectos de preguntas y respuestas ahora actualizados, siga las instrucciones siguientes para actualizar el propio QDK.

## <a name="updating-the-qdk"></a>Actualización de QDK

El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.
Seleccione el entorno de desarrollo a continuación.

* [Python: actualización de la extensión de IQ #](#update-iq-for-python)
* [Cuadernos de Jupyter: actualización de la extensión de IQ #](#update-iq-for-jupyter-notebooks)
* [Visual Studio: actualización de la extensión QDK](#update-visual-studio-qdk-extension)
* [VS Code: actualización de la extensión QDK](#update-vs-code-qdk-extension)
* [Línea de comandos y C#: actualizar plantillas de proyecto](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Actualización de IQ # para Python

1. Actualización del kernel de `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Comprobar la versión de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Debería ver la siguiente salida:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si la versión de `iqsharp` es superior, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).

3. Actualizar el paquete de `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

4. Comprobar la versión de `qsharp`

    ```bash
    pip show qsharp
    ```

    Debería ver la siguiente salida:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Ejecute el siguiente comando desde la ubicación de los archivos de `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Actualización de IQ # for Jupyter notebooks

1. Actualización del kernel de `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Comprobar la versión de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    La salida debe ser similar a la siguiente:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si la versión de `iqsharp` es superior, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).

3. Ejecute el siguiente comando desde una celda del Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.

### <a name="update-visual-studio-qdk-extension"></a>Actualización de la extensión QDK de Visual Studio

1. Actualización de la extensión de preguntas y respuestas de Visual Studio

    - Visual Studio le pide que acepte actualizaciones de la [extensión Quantum de Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .
    - Aceptar la actualización

    > [!NOTE]
    > Las plantillas de proyecto se actualizan con la extensión. Las plantillas actualizadas solo se aplican a los proyectos recién creados. El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.

### <a name="update-vs-code-qdk-extension"></a>Actualizar VS Code extensión QDK

1. Actualización de la extensión de VS Code Quantum

    - Reiniciar VS Code
    - Vaya a la pestaña **extensiones** .
    - Seleccione la **Microsoft Quantum Development Kit para** la extensión Visual Studio Code
    - Recarga de la extensión

2. Actualice las plantillas de proyecto Quantum:

   - Vaya a **Ver** -> **Paleta de comandos**.
   - Seleccionar **Q #: instalar plantillas de proyecto**
   - Después de unos segundos, debe obtener una confirmación emergente de "las plantillas de proyecto se han instalado correctamente".

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, mediante la herramienta de línea de comandos `dotnet`

1. Actualización de las plantillas de proyecto Quantum para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>¿Qué sigue?

Ahora que ha actualizado el kit de desarrollo de Quantum en su entorno preferido, puede seguir desarrollando y ejecutando sus programas de Quantum. Si aún no ha escrito un programa, puede empezar a trabajar con [su primer programa Quantum](xref:microsoft.quantum.write-program).
