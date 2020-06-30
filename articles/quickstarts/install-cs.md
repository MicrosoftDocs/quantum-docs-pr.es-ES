---
title: Desarrollo con Q# y .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274155"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="ec89d-102">Desarrollo con Q# y .NET</span><span class="sxs-lookup"><span data-stu-id="ec89d-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="ec89d-103">Q# trabaja bien con lenguajes .NET como C# y F#.</span><span class="sxs-lookup"><span data-stu-id="ec89d-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="ec89d-104">En esta guía, mostraremos cómo usar Q# con un programa host escrito en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="ec89d-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec89d-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec89d-105">Prerequisites</span></span>

- <span data-ttu-id="ec89d-106">Instale el kit de desarrollo de Quantum [para usarlo con proyectos de línea de comandos de Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="ec89d-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="ec89d-107">Creación de una biblioteca de Q# y un host de .NET</span><span class="sxs-lookup"><span data-stu-id="ec89d-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="ec89d-108">El primer paso es crear proyectos para la biblioteca de Q# y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de Q#.</span><span class="sxs-lookup"><span data-stu-id="ec89d-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="ec89d-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ec89d-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="ec89d-110">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-110">Create a new Q# library</span></span>
  - <span data-ttu-id="ec89d-111">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ec89d-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="ec89d-112">Escriba "Q#" en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec89d-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="ec89d-113">Seleccione **Q# Library** (Biblioteca de Q#).</span><span class="sxs-lookup"><span data-stu-id="ec89d-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="ec89d-114">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ec89d-114">Select **Next**</span></span>
  - <span data-ttu-id="ec89d-115">Elija un nombre y una ubicación para su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ec89d-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="ec89d-116">Asegúrese de que la casilla "colocar el proyecto y la solución en el mismo directorio" esté **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="ec89d-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="ec89d-117">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="ec89d-117">Select **Create**</span></span>
- <span data-ttu-id="ec89d-118">Cree un nuevo programa host de C# o F#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="ec89d-119">Ve a **Archivo** → **Nuevo** → **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ec89d-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="ec89d-120">Seleccione "Aplicación de consola (.NET Core)" para C# y F#.</span><span class="sxs-lookup"><span data-stu-id="ec89d-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="ec89d-121">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ec89d-121">Select **Next**</span></span>
  - <span data-ttu-id="ec89d-122">En *Solución*, seleccione "Agregar a solución".</span><span class="sxs-lookup"><span data-stu-id="ec89d-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="ec89d-123">Elija un nombre para el programa host.</span><span class="sxs-lookup"><span data-stu-id="ec89d-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="ec89d-124">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="ec89d-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="ec89d-125">Visual Studio Code o línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ec89d-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="ec89d-126">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="ec89d-127">Cree un nuevo proyecto de consola de C# y F#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="ec89d-128">Agregue su biblioteca de Q# desde el programa host:</span><span class="sxs-lookup"><span data-stu-id="ec89d-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="ec89d-129">[Opcional] Cree una solución para ambos proyectos:</span><span class="sxs-lookup"><span data-stu-id="ec89d-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="ec89d-130">Llamada a Q# desde .NET</span><span class="sxs-lookup"><span data-stu-id="ec89d-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="ec89d-131">Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q# desde la aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="ec89d-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="ec89d-132">El compilador de Q# creará clases de .NET para cada operación y función de Q# que le permita ejecutar programas cuánticos en un simulador.</span><span class="sxs-lookup"><span data-stu-id="ec89d-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="ec89d-133">El [ejemplo de interoperabilidad con .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) incluye la muestra siguiente de una operación de Q#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="ec89d-134">Para llamar a esta operación desde .NET en un simulador cuántico, puede usar el método `Run` de la clase `RunAlgorithm` de .NET generada por el compilador de Q#:</span><span class="sxs-lookup"><span data-stu-id="ec89d-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="ec89d-135">C#</span><span class="sxs-lookup"><span data-stu-id="ec89d-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="ec89d-136">F#</span><span class="sxs-lookup"><span data-stu-id="ec89d-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="ec89d-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ec89d-137">Next steps</span></span>

<span data-ttu-id="ec89d-138">Ahora que tiene el kit de desarrollo de Quantum configurado para los programas de línea de comandos de Q# y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="ec89d-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
