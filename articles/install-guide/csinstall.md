---
title: Desarrollo con Q# y C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680163"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="315e0-102">Usar Q # con C\# y F\#</span><span class="sxs-lookup"><span data-stu-id="315e0-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="315e0-103">Q # está diseñado para reproducirse bien con lenguajes .NET como C# y F #.</span><span class="sxs-lookup"><span data-stu-id="315e0-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="315e0-104">En esta guía, mostraremos cómo usar Q # con un programa host escrito en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="315e0-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="315e0-105">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="315e0-105">Prerequisites</span></span>

- <span data-ttu-id="315e0-106">Instale el kit de desarrollo [de Quantum para su uso con proyectos de línea de comandos de Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="315e0-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="315e0-107">Creación de una biblioteca de Q # y un host de .NET</span><span class="sxs-lookup"><span data-stu-id="315e0-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="315e0-108">El primer paso es crear proyectos para la biblioteca de preguntas y respuestas, y para el host de .NET que llamará a las operaciones y funciones definidas en la biblioteca de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="315e0-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="315e0-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="315e0-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="315e0-110">Creación de una nueva biblioteca de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="315e0-110">Create a new Q# library</span></span>
  - <span data-ttu-id="315e0-111">Ir a **archivo** -> **nuevo** -> **proyecto**</span><span class="sxs-lookup"><span data-stu-id="315e0-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="315e0-112">Escriba "Q #" en el cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="315e0-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="315e0-113">Seleccionar **biblioteca de preguntas #**</span><span class="sxs-lookup"><span data-stu-id="315e0-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="315e0-114">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="315e0-114">Select **Next**</span></span>
  - <span data-ttu-id="315e0-115">Elegir un nombre y una ubicación para la biblioteca</span><span class="sxs-lookup"><span data-stu-id="315e0-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="315e0-116">Asegúrese de que la casilla "colocar proyecto y solución en el mismo directorio" esté **desactivada** .</span><span class="sxs-lookup"><span data-stu-id="315e0-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="315e0-117">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="315e0-117">Select **Create**</span></span>
- <span data-ttu-id="315e0-118">Crear un nuevo programa host de C# o F #</span><span class="sxs-lookup"><span data-stu-id="315e0-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="315e0-119">Ir a **archivo** → **nuevo** → **proyecto**</span><span class="sxs-lookup"><span data-stu-id="315e0-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="315e0-120">Seleccione "aplicación de consola (.NET Core") "para C# o F #</span><span class="sxs-lookup"><span data-stu-id="315e0-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="315e0-121">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="315e0-121">Select **Next**</span></span>
  - <span data-ttu-id="315e0-122">En *solución*, seleccione "Agregar a solución".</span><span class="sxs-lookup"><span data-stu-id="315e0-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="315e0-123">Elegir un nombre para el programa host</span><span class="sxs-lookup"><span data-stu-id="315e0-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="315e0-124">Seleccione **Crear**</span><span class="sxs-lookup"><span data-stu-id="315e0-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="315e0-125">Visual Studio Code o línea de comandos</span><span class="sxs-lookup"><span data-stu-id="315e0-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="315e0-126">Creación de una nueva biblioteca de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="315e0-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="315e0-127">Crear un nuevo proyecto de consola de C# o F #</span><span class="sxs-lookup"><span data-stu-id="315e0-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="315e0-128">Incorporación de la biblioteca de preguntas y respuestas desde el programa host</span><span class="sxs-lookup"><span data-stu-id="315e0-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="315e0-129">Opta Crear una solución para ambos proyectos</span><span class="sxs-lookup"><span data-stu-id="315e0-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="315e0-130">Llamar a Q # desde .NET</span><span class="sxs-lookup"><span data-stu-id="315e0-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="315e0-131">Una vez que haya configurado los proyectos siguiendo las instrucciones anteriores, puede llamar a Q # desde la aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="315e0-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="315e0-132">El compilador de Q # creará clases .NET para cada operación Q # y función que le permita ejecutar programas Quantum en un simulador.</span><span class="sxs-lookup"><span data-stu-id="315e0-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="315e0-133">Por ejemplo, el [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) incluye el ejemplo siguiente de una operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="315e0-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="315e0-134">Para llamar a esta operación desde .NET en un simulador de Quantum, puede `Run` usar el método `RunAlgorithm` de la clase .net generada por el compilador de preguntas y respuestas:</span><span class="sxs-lookup"><span data-stu-id="315e0-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="315e0-135">C#</span><span class="sxs-lookup"><span data-stu-id="315e0-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="315e0-136">F#</span><span class="sxs-lookup"><span data-stu-id="315e0-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="315e0-137">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="315e0-137">What's next?</span></span>

<span data-ttu-id="315e0-138">Ahora que tiene el kit de desarrollo de Quantum configurado para los programas de línea de comandos de Q # y para la interoperabilidad con .NET, puede escribir y ejecutar [su primer programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="315e0-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
