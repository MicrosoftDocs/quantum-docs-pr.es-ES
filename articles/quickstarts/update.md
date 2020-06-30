---
title: Actualización del kit de desarrollo de Microsoft Quantum
description: Describe cómo actualizar los proyectos de Q# y el kit de desarrollo de Microsoft Quantum a la versión actual.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274143"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Actualización del kit de desarrollo de Microsoft Quantum (QDK)

Descubra cómo actualizar el kit de desarrollo de Microsoft Quantum (QDK) a la última versión.

En este artículo se da por hecho que ya tiene el QDK instalado: Si va a instalarlo por primera vez, consulte la [guía de instalación](xref:microsoft.quantum.install).

Es recomendable mantenerse al día con la versión más reciente del QDK. Siga esta guía de actualización para actualizar a la versión más reciente del QDK. El proceso consta de dos partes:
1. Actualización de los proyectos y archivos de Q# existentes para alinear el código con la sintaxis actualizada.
2. Actualización del propio QDK para el entorno de desarrollo elegido.

## <a name="updating-q-projects"></a>Actualización de los proyectos de Q# 

Siga estas instrucciones para actualizar los proyectos de Q# independientemente de si usa C# o Python para hospedar las operaciones de Q#.

1. En primer lugar, compruebe que tiene la versión más reciente del [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download). Ejecute el siguiente comando en el símbolo del sistema:

    ```dotnetcli
    dotnet --version
    ```

    Compruebe que la salida es `3.1.100` o superior. Si no es así, instale la [última versión](https://dotnet.microsoft.com/download) y vuelva a comprobarlo. Después, siga las instrucciones que se indican a continuación en función de su configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).

### <a name="update-q-projects-in-visual-studio"></a>Actualización de proyectos de Q# en Visual Studio
 
1. Actualice a la versión más reciente de Visual Studio 2019; consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones.
2. Abra su solución en Visual Studio.
3. En el menú, seleccione **Compilar** -> **Limpiar solución**.
4. En cada uno de los archivos .csproj, actualice la plataforma de destino a `netcoreapp3.1` (o `netstandard2.1` si es un proyecto de biblioteca).
    Es decir, edite las líneas del formulario:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    [Aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) encontrará más detalles sobre cómo especificar las plataformas de destino.

5. En cada uno de los archivos .csproj, establezca el SDK en `Microsoft.Quantum.Sdk`, tal y como se indica en la línea siguiente. Tenga en cuenta que el número de versión debe ser el más reciente disponible y puede determinarlo revisando las [notas de la versión](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Guarde y cierre todos los archivos de la solución.

7. Seleccione **Herramientas** -> **Línea de comandos** -> **Símbolo del sistema para desarrolladores**. También puede utilizar la consola del administrador de paquetes de Visual Studio.

8. En cada proyecto de la solución, ejecute el siguiente comando para **quitar** este paquete:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Si los proyectos usan otros paquetes de Microsoft.Quantum o Microsoft.Azure.Quantum (por ejemplo, Microsoft.Quantum.Numerics), ejecute el comando **Agregar** para que se actualice la versión usada.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Cierre el símbolo del sistema y seleccione **Compilar** -> **Compilar solución** (*no* seleccione Recompilar solución).

Ahora puede ir directamente a [actualizar la extensión QDK para Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Actualización de proyectos de Q# en Visual Studio Code

1. En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.
2. Seleccione **Terminal** -> **Nuevo terminal**.
3. Siga las instrucciones para actualizar mediante la línea de comandos (a continuación).

### <a name="update-q-projects-using-the-command-line"></a>Actualización de proyectos de Q# mediante la línea de comandos

1. Vaya hasta la carpeta que contiene el archivo de proyecto principal.

2. Ejecute el siguiente comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Determine la versión actual del QDK. Para encontrarlo, revise las [notas de la versión](https://docs.microsoft.com/quantum/relnotes/). La versión tendrá un formato similar a `0.11.2006.207`.

4. En cada uno de los archivos de `.csproj`, siga estos pasos:

    - Actualice la plataforma de destino a `netcoreapp3.1` (o `netstandard2.1` si es un proyecto de biblioteca). Es decir, edite las líneas del formulario:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        [Aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) encontrará más detalles sobre cómo especificar las plataformas de destino.

    - Reemplace la referencia al SDK en la definición del proyecto. Asegúrese de que el número de versión se corresponde con el valor determinado en el **paso 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Quite la referencia al paquete `Microsoft.Quantum.Development.Kit` si está presente, que se especificará en la entrada siguiente:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Actualice la versión de todos los paquetes de Microsoft Quantum a la versión de lanzamiento más reciente del QDK (determinada en el **paso 3**). El nombre de estos paquetes siguen estos patrones:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Las referencias a los paquetes tienen el siguiente formato:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Guarde el archivo actualizado.

    - Restaure las dependencias del proyecto de la siguiente manera:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Vuelva a la carpeta que contiene el archivo de proyecto principal y ejecute lo siguiente:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Con los proyectos de Q# actualizados, siga estas instrucciones para actualizar el propio QDK.

## <a name="updating-the-qdk"></a>Actualización del código

El proceso para actualizar el QDK varía en función del lenguaje de desarrollo y del entorno.
Seleccione el entorno de desarrollo a continuación.

* [Python: actualización de la extensión IQ#](#update-iq-for-python)
* [Jupyter Notebook: actualización de la extensión IQ#](#update-iq-for-jupyter-notebooks)
* [Visual Studio: actualización de la extensión QDK](#update-visual-studio-qdk-extension)
* [VS Code: actualización de la extensión QDK](#update-vs-code-qdk-extension)
* [Línea de comandos y C# : actualización de las plantillas de proyecto](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Actualización de IQ# para Python

1. Actualice el kernel `iqsharp`. 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Compruebe la versión de `iqsharp`.

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Debería ver la siguiente salida:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si la versión de `iqsharp` es superior; coincidirá con la [versión más reciente](xref:microsoft.quantum.relnotes).

3. Actualice el paquete `qsharp`.

    ```
    pip install qsharp --upgrade
    ```

4. Compruebe la versión de `qsharp`.

    ```
    pip show qsharp
    ```

    Debería ver la siguiente salida:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Ejecute el siguiente comando desde la ubicación de los archivos de `.qs`.

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Ahora puede usar la versión actualizada del QDK para ejecutar los programas cuánticos existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Actualización de IQ# para Jupyter Notebook

1. Actualice el kernel `iqsharp`.

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Compruebe la versión de `iqsharp`.

    ```dotnetcli
    dotnet iqsharp --version
    ```

    La salida debe ser similar a la siguiente:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si la versión de `iqsharp` es superior; coincidirá con la [versión más reciente](xref:microsoft.quantum.relnotes).

3. Ejecute el siguiente comando desde una celda del cuaderno de Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Ahora puede abrir un cuaderno de Jupyter Notebook existente y ejecutarlo con el QDK actualizado.

### <a name="update-visual-studio-qdk-extension"></a>Actualización de la extensión QDK para Visual Studio

1. Actualización de la extensión Q# para Visual Studio

    - Visual Studio le pide que acepte las actualizaciones de la [extensión de Quantum para Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Acepte la actualización.

    > [!NOTE]
    > Las plantillas de proyecto se actualizan con la extensión. Las plantillas actualizadas solo se aplican a los proyectos recién creados. El código de los proyectos existentes no se actualiza cuando se actualiza la extensión.

### <a name="update-vs-code-qdk-extension"></a>Actualización de la extensión QDK para VS Code

1. Actualización de la extensión Quantum para VS Code

    - Reinicie VS Code.
    - Vaya a la pestaña **Extensiones**.
    - Seleccione la extensión **Kit de desarrollo de Microsoft Quantum para Visual Studio Code**.
    - Vuelva a cargar la extensión

2. Instale las plantillas de proyecto de Quantum:

   - Vaya a **Ver** -> **Paleta de comandos**.
   - Seleccione **Q#: Install project templates** (Q#: Instalar plantillas de proyecto)
   - Después de unos segundos, aparece el mensaje "Project templates installed successfully" (Plantillas de proyecto instaladas correctamente).

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, con la herramienta de línea de comandos `dotnet`

1. Actualice las plantillas de proyecto de Quantum para .NET.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
