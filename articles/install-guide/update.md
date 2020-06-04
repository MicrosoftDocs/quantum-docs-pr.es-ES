---
title: Actualización del kit de desarrollo de Quantum (QDK)
description: 'Describe cómo actualizar los proyectos de Q # y el Microsoft Quantum Development Kit a la versión actual.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327582"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Actualización del Microsoft Quantum Development Kit (QDK)

Obtenga información sobre cómo actualizar el Microsoft Quantum Development Kit (QDK) a la versión más reciente.

En este artículo se da por supuesto que ya tiene el QDK instalado. Si va a instalar por primera vez, consulte la [Guía de instalación](xref:microsoft.quantum.install).

Se recomienda mantenerse al día con la versión más reciente de QDK. Siga esta guía de actualización para actualizar a la versión más reciente de QDK. El proceso consta de dos partes:
1. Actualizar los proyectos y archivos de preguntas # existentes para alinear el código con cualquier sintaxis actualizada.
2. Actualización del propio QDK para el entorno de desarrollo elegido.

## <a name="updating-q-projects"></a>Actualizar proyectos de Q # 

Independientemente de si usa C# o Python para hospedar las operaciones de Q #, siga estas instrucciones para actualizar los proyectos de preguntas y respuestas.

1. En primer lugar, compruebe que dispone de la versión más reciente del [SDK de .NET Core 3,1](https://dotnet.microsoft.com/download). Ejecute el siguiente comando en el símbolo del sistema:

    ```dotnetcli
    dotnet --version
    ```

    Compruebe que la salida es `3.1.100` o superior. Si no es así, instale la [versión más reciente](https://dotnet.microsoft.com/download) y vuelva a comprobarlo. A continuación, siga las instrucciones que se indican a continuación en función de la configuración (Visual Studio, Visual Studio Code o directamente la línea de comandos).

### <a name="update-q-projects-in-visual-studio"></a>Actualización de proyectos de Q # en Visual Studio
 
1. Actualice a la versión más reciente de Visual Studio 2019, consulte [aquí](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obtener instrucciones.
2. Abra su solución en Visual Studio.
3. En el menú, seleccione **compilar**  ->  **solución limpia**.
4. En cada uno de los archivos. csproj, actualice la plataforma de destino en `netcoreapp3.1` (o `netstandard2.1` si se trata de un proyecto de biblioteca).
    Es decir, edite las líneas del formulario:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. En cada uno de los archivos. csproj, establezca el SDK en `Microsoft.Quantum.Sdk` , como se indica en la línea siguiente. Tenga en cuenta que el número de versión debe ser el más reciente disponible y puede determinarlo revisando las [notas](https://docs.microsoft.com/quantum/relnotes/)de la versión.

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Guarde y cierre todos los archivos de la solución.

7. Seleccione **herramientas**  ->  símbolo del sistema para desarrolladores de**línea de comandos**  ->  **Developer Command Prompt**. Como alternativa, puede usar la consola de administración de paquetes en Visual Studio.

8. Para cada proyecto de la solución, ejecute el siguiente comando para **quitar** este paquete:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Si los proyectos usan otros paquetes Microsoft. Quantum o Microsoft. Azure. Quantum (por ejemplo, Microsoft. Quantum. Numerics), ejecute el comando **Add** para que se actualice la versión usada.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Cierre el símbolo del sistema y **Seleccione compilar compilar**  ->  **solución** ( *no* seleccione recompilar solución).

Ahora puede continuar con [la actualización de la extensión QDK de Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Actualizar proyectos de Q # en Visual Studio Code

1. En Visual Studio Code, abra la carpeta que contiene el proyecto que se va a actualizar.
2. Seleccione **terminal**  ->  **nuevo terminal**.
3. Siga las instrucciones para la actualización mediante la línea de comandos (directamente a continuación).

### <a name="update-q-projects-using-the-command-line"></a>Actualización de proyectos de Q # mediante la línea de comandos

1. Navegue hasta la carpeta que contiene el archivo de proyecto principal.

2. Ejecute el siguiente comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Determine la versión actual de QDK. Para encontrarlo, puede revisar las [notas](https://docs.microsoft.com/quantum/relnotes/)de la versión. La versión tendrá un formato similar a `0.11.2006.207` .

4. En cada uno de los `.csproj` archivos, siga estos pasos:

    - Actualice la versión de .NET Framework de destino a `netcoreapp3.1` (o `netstandard2.1` si se trata de un proyecto de biblioteca). Es decir, edite las líneas del formulario:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Puede encontrar más detalles sobre cómo especificar las plataformas de destino [aquí](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Reemplace la referencia al SDK en la definición del proyecto. Asegúrese de que el número de versión corresponde al valor determinado en el **paso 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Quite la referencia al paquete `Microsoft.Quantum.Development.Kit` si está presente, que se especificará en la siguiente entrada:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Actualice la versión de todos los paquetes Quantum de Microsoft a la versión de lanzamiento más reciente de QDK (determinada en el **paso 3**). Estos paquetes se denominan con los siguientes patrones:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Las referencias a los paquetes tienen el siguiente formato:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Guarde el archivo actualizado.

    - Restaure las dependencias del proyecto, para lo que debe hacer lo siguiente:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Vuelva a la carpeta que contiene el proyecto principal y ejecute:

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

1. Actualizar el `iqsharp` kernel 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Comprobar la `iqsharp` versión

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Debería ver la siguiente salida:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si su `iqsharp` versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).

3. Actualización del `qsharp` paquete

    ```bash
    pip install qsharp --upgrade
    ```

4. Comprobar la `qsharp` versión

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

5. Ejecute el siguiente comando desde la ubicación de los `.qs` archivos.

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Ahora puede usar la versión actualizada de QDK para ejecutar los programas Quantum existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Actualización de IQ # for Jupyter notebooks

1. Actualizar el `iqsharp` kernel

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Comprobar la `iqsharp` versión

    ```dotnetcli
    dotnet iqsharp --version
    ```

    La salida debe ser similar a la siguiente:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    No se preocupe si su `iqsharp` versión es mayor, debe coincidir con la [versión más reciente](xref:microsoft.quantum.relnotes).

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

   - Ir a **Ver**  ->  **paleta de comandos**
   - Seleccionar **Q #: instalar plantillas de proyecto**
   - Después de unos segundos, debe obtener una confirmación emergente de "las plantillas de proyecto se han instalado correctamente".

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, uso de la `dotnet` herramienta de línea de comandos

1. Actualización de las plantillas de proyecto Quantum para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
