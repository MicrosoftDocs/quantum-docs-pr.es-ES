---
title: Desarrollo con Q# y .NET
description: Obtenga información sobre cómo crear una aplicación de Q# con lenguajes .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834336"
---
# <a name="develop-with-no-locq-and-net"></a>Desarrollo con Q# y .NET

Q# trabaja bien con lenguajes .NET como C# y F#.
En esta guía, mostramos cómo usar Q# con un programa host escrito en un lenguaje .NET.

En primer lugar, se crea la aplicación de Q# y el host de .NET y, a continuación, se muestra cómo llamar a Q# desde el host.

## <a name="prerequisites"></a>Requisitos previos

- Instale el kit de desarrollo de Quantum [para usarlo con proyectos de Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Creación de una biblioteca de Q# y un host de .NET

El primer paso es crear proyectos para la biblioteca de Q# y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de Q#.

Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno de desarrollo.
Si usa un editor que no sea Visual Studio o VS Code, solo tiene que seguir los pasos del símbolo del sistema.

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code o símbolo del sistema](#tab/tabid-cmdline)

- Cree una nueva biblioteca de Q#:

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Cree un nuevo proyecto de consola de C# y F#:

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Agregue su biblioteca de Q# desde el programa host:

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Opcional] Cree una solución para ambos proyectos:

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Cree una nueva biblioteca de Q#:
  - Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.
  - Escriba "Q#" en el cuadro de búsqueda.
  - Seleccione **Q# Library** (Biblioteca de Q#).
  - Seleccione **Siguiente**.
  - Elija un nombre y una ubicación para su biblioteca.
  - Asegúrese de que la casilla "colocar el proyecto y la solución en el mismo directorio" esté **desactivada**.
  - Seleccione **Crear**
- Cree un nuevo programa host de C# o F#:
  - Ve a **Archivo** → **Nuevo** → **Proyecto**.
  - Seleccione "Aplicación de consola (.NET Core)" para C# y F#.
  - Seleccione **Siguiente**.
  - En *Solución*, seleccione "Agregar a solución".
  - Elija un nombre para el programa host.
  - Seleccione **Crear**

***

## <a name="calling-into-no-locq-from-net"></a>Llamada a Q# desde .NET

Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q# desde la aplicación de consola de .NET.
El compilador de Q# creará clases de .NET para cada operación y función de Q# que le permita ejecutar programas cuánticos en un simulador.

El [ejemplo de interoperabilidad con .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) incluye el ejemplo siguiente de una operación de Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Para llamar a esta operación desde .NET en un simulador cuántico, puede usar el método `Run` de la clase `RunAlgorithm` de .NET generada por el compilador de Q#:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Pasos siguientes

Ahora que tiene el kit de desarrollo de Quantum configurado para las aplicaciones de Q# y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).
