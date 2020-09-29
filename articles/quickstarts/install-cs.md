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
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="02753-103">Desarrollo con Q# y .NET</span><span class="sxs-lookup"><span data-stu-id="02753-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="02753-104">Q# trabaja bien con lenguajes .NET como C# y F#.</span><span class="sxs-lookup"><span data-stu-id="02753-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="02753-105">En esta guía, mostramos cómo usar Q# con un programa host escrito en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="02753-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="02753-106">En primer lugar, se crea la aplicación de Q# y el host de .NET y, a continuación, se muestra cómo llamar a Q# desde el host.</span><span class="sxs-lookup"><span data-stu-id="02753-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02753-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="02753-107">Prerequisites</span></span>

- <span data-ttu-id="02753-108">Instale el kit de desarrollo de Quantum [para usarlo con proyectos de Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="02753-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="02753-109">Creación de una biblioteca de Q# y un host de .NET</span><span class="sxs-lookup"><span data-stu-id="02753-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="02753-110">El primer paso es crear proyectos para la biblioteca de Q# y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de Q#.</span><span class="sxs-lookup"><span data-stu-id="02753-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="02753-111">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="02753-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="02753-112">Si usa un editor que no sea Visual Studio o VS Code, solo tiene que seguir los pasos del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="02753-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="02753-113">Visual Studio Code o símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="02753-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="02753-114">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="02753-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="02753-115">Cree un nuevo proyecto de consola de C# y F#:</span><span class="sxs-lookup"><span data-stu-id="02753-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="02753-116">Agregue su biblioteca de Q# desde el programa host:</span><span class="sxs-lookup"><span data-stu-id="02753-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="02753-117">[Opcional] Cree una solución para ambos proyectos:</span><span class="sxs-lookup"><span data-stu-id="02753-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="02753-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="02753-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="02753-119">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="02753-119">Create a new Q# library</span></span>
  - <span data-ttu-id="02753-120">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02753-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="02753-121">Escriba "Q#" en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02753-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="02753-122">Seleccione **Q# Library** (Biblioteca de Q#).</span><span class="sxs-lookup"><span data-stu-id="02753-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="02753-123">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02753-123">Select **Next**</span></span>
  - <span data-ttu-id="02753-124">Elija un nombre y una ubicación para su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="02753-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="02753-125">Asegúrese de que la casilla "colocar el proyecto y la solución en el mismo directorio" esté **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="02753-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="02753-126">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="02753-126">Select **Create**</span></span>
- <span data-ttu-id="02753-127">Cree un nuevo programa host de C# o F#:</span><span class="sxs-lookup"><span data-stu-id="02753-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="02753-128">Ve a **Archivo** → **Nuevo** → **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02753-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="02753-129">Seleccione "Aplicación de consola (.NET Core)" para C# y F#.</span><span class="sxs-lookup"><span data-stu-id="02753-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="02753-130">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02753-130">Select **Next**</span></span>
  - <span data-ttu-id="02753-131">En *Solución*, seleccione "Agregar a solución".</span><span class="sxs-lookup"><span data-stu-id="02753-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="02753-132">Elija un nombre para el programa host.</span><span class="sxs-lookup"><span data-stu-id="02753-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="02753-133">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="02753-133">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="02753-134">Llamada a Q# desde .NET</span><span class="sxs-lookup"><span data-stu-id="02753-134">Calling into Q# from .NET</span></span>

<span data-ttu-id="02753-135">Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q# desde la aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="02753-135">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="02753-136">El compilador de Q# creará clases de .NET para cada operación y función de Q# que le permita ejecutar programas cuánticos en un simulador.</span><span class="sxs-lookup"><span data-stu-id="02753-136">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="02753-137">El [ejemplo de interoperabilidad con .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) incluye el ejemplo siguiente de una operación de Q#:</span><span class="sxs-lookup"><span data-stu-id="02753-137">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="02753-138">Para llamar a esta operación desde .NET en un simulador cuántico, puede usar el método `Run` de la clase `RunAlgorithm` de .NET generada por el compilador de Q#:</span><span class="sxs-lookup"><span data-stu-id="02753-138">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="02753-139">C#</span><span class="sxs-lookup"><span data-stu-id="02753-139">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="02753-140">F#</span><span class="sxs-lookup"><span data-stu-id="02753-140">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="02753-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="02753-141">Next steps</span></span>

<span data-ttu-id="02753-142">Ahora que tiene el kit de desarrollo de Quantum configurado para las aplicaciones de Q# y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="02753-142">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
