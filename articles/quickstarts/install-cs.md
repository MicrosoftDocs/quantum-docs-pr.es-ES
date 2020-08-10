---
title: Desarrollo con Q# y .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 13d73bdf0287941c89e03ba63869095e5fca4e70
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867563"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="8c011-102">Desarrollo con Q# y .NET</span><span class="sxs-lookup"><span data-stu-id="8c011-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="8c011-103">Q# trabaja bien con lenguajes .NET como C# y F#.</span><span class="sxs-lookup"><span data-stu-id="8c011-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="8c011-104">En esta guía, mostramos cómo usar Q# con un programa host escrito en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="8c011-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="8c011-105">En primer lugar, se crea la aplicación de Q# y el host de .NET y, a continuación, se muestra cómo llamar a Q# desde el host.</span><span class="sxs-lookup"><span data-stu-id="8c011-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c011-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8c011-106">Prerequisites</span></span>

- <span data-ttu-id="8c011-107">Instale el kit de desarrollo de Quantum [para usarlo con proyectos de línea de comandos de Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="8c011-107">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="8c011-108">Creación de una biblioteca de Q# y un host de .NET</span><span class="sxs-lookup"><span data-stu-id="8c011-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="8c011-109">El primer paso es crear proyectos para la biblioteca de Q# y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de Q#.</span><span class="sxs-lookup"><span data-stu-id="8c011-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="8c011-110">Siga las instrucciones que aparecen en la pestaña correspondiente a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="8c011-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="8c011-111">Si usa un editor que no sea Visual Studio o VS Code, solo tiene que seguir los pasos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8c011-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command line steps.</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="8c011-112">Visual Studio Code o línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8c011-112">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="8c011-113">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="8c011-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="8c011-114">Cree un nuevo proyecto de consola de C# y F#:</span><span class="sxs-lookup"><span data-stu-id="8c011-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="8c011-115">Agregue su biblioteca de Q# desde el programa host:</span><span class="sxs-lookup"><span data-stu-id="8c011-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="8c011-116">[Opcional] Cree una solución para ambos proyectos:</span><span class="sxs-lookup"><span data-stu-id="8c011-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="8c011-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="8c011-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="8c011-118">Cree una nueva biblioteca de Q#:</span><span class="sxs-lookup"><span data-stu-id="8c011-118">Create a new Q# library</span></span>
  - <span data-ttu-id="8c011-119">Vaya a **Archivo** -> **Nuevo** -> **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="8c011-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="8c011-120">Escriba "Q#" en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8c011-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="8c011-121">Seleccione **Q# Library** (Biblioteca de Q#).</span><span class="sxs-lookup"><span data-stu-id="8c011-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="8c011-122">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8c011-122">Select **Next**</span></span>
  - <span data-ttu-id="8c011-123">Elija un nombre y una ubicación para su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8c011-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="8c011-124">Asegúrese de que la casilla "colocar el proyecto y la solución en el mismo directorio" esté **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="8c011-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="8c011-125">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="8c011-125">Select **Create**</span></span>
- <span data-ttu-id="8c011-126">Cree un nuevo programa host de C# o F#:</span><span class="sxs-lookup"><span data-stu-id="8c011-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="8c011-127">Ve a **Archivo** → **Nuevo** → **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="8c011-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="8c011-128">Seleccione "Aplicación de consola (.NET Core)" para C# y F#.</span><span class="sxs-lookup"><span data-stu-id="8c011-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="8c011-129">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8c011-129">Select **Next**</span></span>
  - <span data-ttu-id="8c011-130">En *Solución*, seleccione "Agregar a solución".</span><span class="sxs-lookup"><span data-stu-id="8c011-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="8c011-131">Elija un nombre para el programa host.</span><span class="sxs-lookup"><span data-stu-id="8c011-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="8c011-132">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="8c011-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="8c011-133">Llamada a Q# desde .NET</span><span class="sxs-lookup"><span data-stu-id="8c011-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="8c011-134">Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q# desde la aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="8c011-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="8c011-135">El compilador de Q# creará clases de .NET para cada operación y función de Q# que le permita ejecutar programas cuánticos en un simulador.</span><span class="sxs-lookup"><span data-stu-id="8c011-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="8c011-136">El [ejemplo de interoperabilidad con .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) incluye el ejemplo siguiente de una operación de Q#:</span><span class="sxs-lookup"><span data-stu-id="8c011-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="8c011-137">Para llamar a esta operación desde .NET en un simulador cuántico, puede usar el método `Run` de la clase `RunAlgorithm` de .NET generada por el compilador de Q#:</span><span class="sxs-lookup"><span data-stu-id="8c011-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="8c011-138">C#</span><span class="sxs-lookup"><span data-stu-id="8c011-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="8c011-139">F#</span><span class="sxs-lookup"><span data-stu-id="8c011-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="8c011-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8c011-140">Next steps</span></span>

<span data-ttu-id="8c011-141">Ahora que tiene el kit de desarrollo de Quantum configurado para los programas de línea de comandos de Q# y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa cuántico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="8c011-141">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
