---
title: Desarrollo con Q# y .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426503"
---
# <a name="develop-with-q-and-net"></a>Desarrollo con Q# y .NET

Q # está diseñado para reproducirse bien con lenguajes .NET como C# y F #.
En esta guía, mostraremos cómo usar Q # con un programa host escrito en un lenguaje .NET.

## <a name="prerequisites"></a>Requisitos previos

- Instale el kit de desarrollo [de Quantum para su uso con proyectos de línea de comandos de Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Creación de una biblioteca de Q # y un host de .NET

El primer paso es crear proyectos para la biblioteca de preguntas y respuestas, y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de preguntas y respuestas.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Creación de una nueva biblioteca de preguntas y respuestas
  - Ir a **archivo**  ->  **nuevo**  ->  **proyecto**
  - Escriba "Q #" en el cuadro de búsqueda
  - Seleccionar **biblioteca de preguntas #**
  - Seleccione **Siguiente**.
  - Elegir un nombre y una ubicación para la biblioteca
  - Asegúrese de que la casilla "colocar proyecto y solución en el mismo directorio" esté **desactivada** .
  - Seleccione **Crear**.
- Crear un nuevo programa host de C# o F #
  - Ir a **archivo** → **nuevo** → **proyecto**
  - Seleccione "aplicación de consola (.NET Core") "para C# o F #
  - Seleccione **Siguiente**.
  - En *solución*, seleccione "Agregar a solución".
  - Elegir un nombre para el programa host
  - Seleccione **Crear**.

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code o línea de comandos](#tab/tabid-cmdline)

- Creación de una nueva biblioteca de preguntas y respuestas

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Crear un nuevo proyecto de consola de C# o F #

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Incorporación de la biblioteca de preguntas y respuestas desde el programa host

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Opta Crear una solución para ambos proyectos

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Llamar a Q # desde .NET

Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q # desde la aplicación de consola de .NET.
El compilador de Q # creará clases .NET para cada operación Q # y función que le permita ejecutar programas Quantum en un simulador.

Por ejemplo, el [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) incluye el ejemplo siguiente de una operación de Q #:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Para llamar a esta operación desde .NET en un simulador de Quantum, puede usar el `Run` método de la `RunAlgorithm` clase .net generada por el compilador de preguntas y respuestas:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Pasos siguientes

Ahora que tiene el kit de desarrollo de Quantum configurado para los programas de línea de comandos de Q # y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa Quantum](xref:microsoft.quantum.quickstarts.qrng).
