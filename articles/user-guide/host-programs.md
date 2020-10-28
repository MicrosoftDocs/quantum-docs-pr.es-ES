---
title: 'Formas de ejecutar un :::no-loc(Q#)::: programa'
description: 'Información general de las diferentes formas de ejecutar :::no-loc(Q#)::: programas. Desde el símbolo del sistema, :::no-loc(Q#)::: cuadernos de Jupyter Notebook y programas host clásico en Python o en un lenguaje .net.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691698"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="de2b9-104">Formas de ejecutar un :::no-loc(Q#)::: programa</span><span class="sxs-lookup"><span data-stu-id="de2b9-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="de2b9-105">Uno de los mayores puntos fuertes del kit de desarrollo de Quantum es su flexibilidad en plataformas y entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="de2b9-106">Sin embargo, esto también significa que los nuevos :::no-loc(Q#)::: usuarios se pueden confundir o saturar mediante las numerosas opciones que se encuentran en la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="de2b9-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="de2b9-107">En esta página, se explica lo que ocurre cuando :::no-loc(Q#)::: se ejecuta un programa y se comparan las distintas formas en que los usuarios pueden hacerlo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="de2b9-108">Una distinción principal es que se :::no-loc(Q#)::: puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="de2b9-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="de2b9-109">como aplicación independiente, donde :::no-loc(Q#)::: es el único lenguaje implicado y el programa se invoca directamente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="de2b9-110">En realidad, dos métodos se encuentran en esta categoría:</span><span class="sxs-lookup"><span data-stu-id="de2b9-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="de2b9-111">la interfaz de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="de2b9-111">the command-line interface</span></span>
  - <span data-ttu-id="de2b9-112">:::no-loc(Q#)::: Cuadernos de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="de2b9-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="de2b9-113">con un *programa host* adicional, escrito en Python o en un lenguaje .net (por ejemplo, C# o F #), que, a continuación, invoca el programa y puede procesar aún más los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="de2b9-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="de2b9-114">Para comprender mejor estos procesos y sus diferencias, se considera un :::no-loc(Q#)::: programa sencillo y se comparan las formas en que se pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="de2b9-115">:::no-loc(Q#):::Programa básico</span><span class="sxs-lookup"><span data-stu-id="de2b9-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="de2b9-116">Un programa Quantum básico puede constar de la preparación de una qubit en una superposición de Estados $ \ket {0} $ y $ \ket {1} $, la medición y la devolución del resultado, que será aleatoriamente uno de estos dos Estados con la misma probabilidad.</span><span class="sxs-lookup"><span data-stu-id="de2b9-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="de2b9-117">En realidad, este proceso es el núcleo de la guía de inicio rápido del [generador de números aleatorios de Quantum](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="de2b9-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="de2b9-118">En :::no-loc(Q#)::: , esto se realizaría mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="de2b9-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="de2b9-119">Sin embargo, este código no puede ejecutarse por sí solo :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="de2b9-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="de2b9-120">Para ello, debe componer el cuerpo de una [operación](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que se ejecuta cuando se llama---directamente o mediante otra operación.</span><span class="sxs-lookup"><span data-stu-id="de2b9-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="de2b9-121">Por lo tanto, puede escribir una operación de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="de2b9-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="de2b9-122">Ha definido una operación, `MeasureSuperposition` , que no toma ninguna entrada y devuelve un valor de tipo [result](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="de2b9-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="de2b9-123">Aunque los ejemplos de esta página solo se componen de :::no-loc(Q#)::: *operaciones* , todos los conceptos que trataremos se refieren igualmente a :::no-loc(Q#)::: *las funciones* y, por tanto, hacemos referencia a ellas colectivamente como *llamadas* .</span><span class="sxs-lookup"><span data-stu-id="de2b9-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="de2b9-124">Sus diferencias se describen en [ :::no-loc(Q#)::: conceptos básicos: operaciones y funciones](xref:microsoft.quantum.guide.basics#q-operations-and-functions), y más detalles sobre cómo definirlas se pueden encontrar en [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="de2b9-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="de2b9-125">Se puede llamar en un :::no-loc(Q#)::: archivo</span><span class="sxs-lookup"><span data-stu-id="de2b9-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="de2b9-126">La llamada invocativa es precisamente lo que se llama y ejecuta :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="de2b9-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="de2b9-127">Sin embargo, requiere algunas adiciones más para incluir un `*.qs` :::no-loc(Q#)::: archivo completo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="de2b9-128">Todos los :::no-loc(Q#)::: tipos y llamadas (que se definen y los intrínsecos al lenguaje) se definen dentro de los *espacios de nombres* , que proporcionan cada nombre completo al que se puede hacer referencia a continuación.</span><span class="sxs-lookup"><span data-stu-id="de2b9-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="de2b9-129">Por ejemplo, las [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operaciones y se encuentran en los [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) espacios de [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) nombres y (parte de las [ :::no-loc(Q#)::: bibliotecas estándar](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="de2b9-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="de2b9-130">Como tal, siempre se les puede llamar a través de sus nombres *completos* `Microsoft.Quantum.Intrinsic.H(<qubit>)` y `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , pero siempre esto provocaría un código muy saturado.</span><span class="sxs-lookup"><span data-stu-id="de2b9-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="de2b9-131">En su lugar, `open` las instrucciones permiten hacer referencia a las llamadas con una abreviatura más concisa, como hemos hecho en el cuerpo de la operación anterior.</span><span class="sxs-lookup"><span data-stu-id="de2b9-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="de2b9-132">:::no-loc(Q#):::Por lo tanto, el archivo completo que contiene nuestra operación consistiría en definir nuestro propio espacio de nombres, abriendo los espacios de nombres de los que se llamaron en la operación y, a continuación, nuestra operación:</span><span class="sxs-lookup"><span data-stu-id="de2b9-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="de2b9-133">También se pueden asignar *alias* a los espacios de nombres cuando se abren, lo que puede resultar útil si se producen conflictos entre los nombres de tipo o los tipos en dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="de2b9-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="de2b9-134">Por ejemplo, en su lugar podríamos usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` anteriormente y, a continuación, llamar a `H` mediante `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-135">Una excepción a todo esto es el [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) espacio de nombres, que siempre se abre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="de2b9-136">Por lo tanto, [`Length`](xref:Microsoft.Quantum.Core.Length) se pueden usar directamente llamadas como siempre.</span><span class="sxs-lookup"><span data-stu-id="de2b9-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="de2b9-137">Ejecutar en máquinas de destino</span><span class="sxs-lookup"><span data-stu-id="de2b9-137">Running on target machines</span></span>

<span data-ttu-id="de2b9-138">Ahora se borra el modelo de ejecución general de un :::no-loc(Q#)::: programa.</span><span class="sxs-lookup"><span data-stu-id="de2b9-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="de2b9-139">En primer lugar, el llamador específico que se va a ejecutar tiene acceso a cualquier otro tipo que se pueda llamar y que se haya definido en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="de2b9-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="de2b9-140">También tiene acceso a los de cualquiera de las [ :::no-loc(Q#)::: bibliotecas](xref:microsoft.quantum.libraries), pero se debe hacer referencia a ellos mediante su nombre completo o mediante el uso de `open` instrucciones descritas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="de2b9-141">A continuación, se puede llamar a en un *[equipo de destino](xref:microsoft.quantum.machines)* .</span><span class="sxs-lookup"><span data-stu-id="de2b9-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="de2b9-142">Estas máquinas de destino pueden ser hardware de Quantum real o varios simuladores disponibles como parte de QDK.</span><span class="sxs-lookup"><span data-stu-id="de2b9-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="de2b9-143">Para nuestros fines aquí, el equipo de destino más útil es una instancia del [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , que calcula el comportamiento del programa como si se estuviera ejecutando en un equipo Quantum sin ruido.</span><span class="sxs-lookup"><span data-stu-id="de2b9-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="de2b9-144">Hasta ahora, hemos descrito lo que ocurre cuando :::no-loc(Q#)::: se ejecuta una función invocable específica.</span><span class="sxs-lookup"><span data-stu-id="de2b9-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="de2b9-145">Con independencia de si :::no-loc(Q#)::: se usa en una aplicación independiente o con un programa host, este proceso general es más o menos el mismo---, por lo tanto, la flexibilidad de QDK.</span><span class="sxs-lookup"><span data-stu-id="de2b9-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="de2b9-146">Por lo tanto, las diferencias entre las formas de llamar al kit de desarrollo de Quantum se revelan en el *modo* en que :::no-loc(Q#)::: se ejecuta la llamada para ejecutarse y en qué manera se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="de2b9-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="de2b9-147">Más concretamente, las diferencias giran en torno a:</span><span class="sxs-lookup"><span data-stu-id="de2b9-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="de2b9-148">Que indica qué :::no-loc(Q#)::: se puede llamar para ejecutarse</span><span class="sxs-lookup"><span data-stu-id="de2b9-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="de2b9-149">Cómo se proporcionan los argumentos que se pueden llamar</span><span class="sxs-lookup"><span data-stu-id="de2b9-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="de2b9-150">Especificar el equipo de destino en el que se va a ejecutar</span><span class="sxs-lookup"><span data-stu-id="de2b9-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="de2b9-151">Cómo se devuelven los resultados</span><span class="sxs-lookup"><span data-stu-id="de2b9-151">How any results are returned</span></span>

<span data-ttu-id="de2b9-152">En primer lugar, se describe cómo hacerlo con la :::no-loc(Q#)::: aplicación independiente desde el símbolo del sistema y, a continuación, se sigue usando los programas host de Python y C#.</span><span class="sxs-lookup"><span data-stu-id="de2b9-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="de2b9-153">Nos reservamos la aplicación independiente de :::no-loc(Q#)::: cuadernos de Jupyter Notebook por última vez, porque a diferencia de las tres primeras, su funcionalidad principal no se centra en un :::no-loc(Q#)::: archivo local.</span><span class="sxs-lookup"><span data-stu-id="de2b9-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-154">Aunque no se muestra en estos ejemplos, una diferencia entre los métodos de ejecución es que todos los mensajes impresos desde dentro del :::no-loc(Q#)::: programa (por [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ejemplo, o, por ejemplo) siempre se imprimirán en la consola correspondiente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="de2b9-155">:::no-loc(Q#)::: desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="de2b9-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="de2b9-156">Una de las maneras más fáciles de empezar a escribir :::no-loc(Q#)::: programas es evitar preocuparse por archivos independientes y un segundo idioma.</span><span class="sxs-lookup"><span data-stu-id="de2b9-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="de2b9-157">El uso de Visual Studio Code o Visual Studio con la extensión QDK permite un flujo de trabajo sin problemas en el que se ejecutan :::no-loc(Q#)::: llamadas desde un solo :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="de2b9-158">Para ello, se ejecutará el programa en última instancia.</span><span class="sxs-lookup"><span data-stu-id="de2b9-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="de2b9-159">en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="de2b9-159">at the command prompt.</span></span>
<span data-ttu-id="de2b9-160">El flujo de trabajo más sencillo es cuando la ubicación del directorio del terminal es igual que el :::no-loc(Q#)::: archivo, que se puede controlar fácilmente junto :::no-loc(Q#)::: con la edición de archivos mediante el terminal integrado en vs Code, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="de2b9-161">Sin embargo, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) acepta numerosas opciones y el programa también se puede ejecutar desde una ubicación diferente, simplemente proporcionando `--project <PATH>` con la ubicación del :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="de2b9-162">Agregar punto de entrada a :::no-loc(Q#)::: archivo</span><span class="sxs-lookup"><span data-stu-id="de2b9-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="de2b9-163">La mayoría :::no-loc(Q#)::: de los archivos contendrán más de una a la que se puede llamar, por lo que es necesario dejar que el compilador sepa *qué* llamadas se ejecutan cuando se proporciona el `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="de2b9-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="de2b9-164">Esto se hace con un simple cambio en el :::no-loc(Q#)::: propio archivo:</span><span class="sxs-lookup"><span data-stu-id="de2b9-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="de2b9-165">Agregue una línea `@EntryPoint()` que preceda directamente a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="de2b9-166">Por lo tanto, el archivo anterior se convertiría en</span><span class="sxs-lookup"><span data-stu-id="de2b9-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="de2b9-167">Ahora, una llamada de `dotnet run` desde el símbolo del sistema conduce a `MeasureSuperposition` ejecutarse y, a continuación, el valor devuelto se imprime directamente en el terminal.</span><span class="sxs-lookup"><span data-stu-id="de2b9-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="de2b9-168">Por lo tanto, verá `One` o `Zero` imprimirá.</span><span class="sxs-lookup"><span data-stu-id="de2b9-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="de2b9-169">Tenga en cuenta que no importa si tiene más llamadas definidas debajo, solo se `MeasureSuperposition` ejecutará.</span><span class="sxs-lookup"><span data-stu-id="de2b9-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="de2b9-170">Además, no hay ningún problema si su llamador incluye [comentarios de documentación](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes de su declaración, el `@EntryPoint()` atributo se puede colocar simplemente encima de ellos.</span><span class="sxs-lookup"><span data-stu-id="de2b9-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="de2b9-171">Argumentos Invocables</span><span class="sxs-lookup"><span data-stu-id="de2b9-171">Callable arguments</span></span>

<span data-ttu-id="de2b9-172">Hasta ahora, solo hemos considerado una operación que no toma ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="de2b9-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="de2b9-173">Supongamos que deseamos realizar una operación similar, pero en varios qubits---el número de que se proporciona como argumento.</span><span class="sxs-lookup"><span data-stu-id="de2b9-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="de2b9-174">Este tipo de operación podría escribirse como</span><span class="sxs-lookup"><span data-stu-id="de2b9-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="de2b9-175">donde el valor devuelto es una matriz de los resultados de la medición.</span><span class="sxs-lookup"><span data-stu-id="de2b9-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="de2b9-176">Tenga en cuenta que [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) y [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) se encuentran en los [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) espacios de [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) nombres y, que requieren `open` instrucciones adicionales para cada uno.</span><span class="sxs-lookup"><span data-stu-id="de2b9-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="de2b9-177">Si movemos el `@EntryPoint()` atributo para que preceda a esta nueva operación (tenga en cuenta que solo puede haber una línea de este tipo en un archivo), intentar ejecutarlo simplemente `dotnet run` genera un mensaje de error que indica qué opciones de línea de comandos adicionales son necesarias y cómo expresarlos.</span><span class="sxs-lookup"><span data-stu-id="de2b9-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="de2b9-178">El formato general de la línea de comandos es realmente `dotnet run [options]` , y los argumentos que se pueden llamar se proporcionan allí.</span><span class="sxs-lookup"><span data-stu-id="de2b9-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="de2b9-179">En este caso, falta el argumento `n` y se muestra que es necesario proporcionar la opción `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="de2b9-180">`MeasureSuperpositionArray` `n=4` Por lo tanto, para ejecutar para qubits, usamos</span><span class="sxs-lookup"><span data-stu-id="de2b9-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="de2b9-181">producir una salida similar a</span><span class="sxs-lookup"><span data-stu-id="de2b9-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="de2b9-182">Esto se extiende a varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="de2b9-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-183">`camelCase`El compilador modifica ligeramente los nombres de argumento definidos en para que se acepten como :::no-loc(Q#)::: entradas.</span><span class="sxs-lookup"><span data-stu-id="de2b9-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="de2b9-184">Por ejemplo, si en lugar de `n` , usamos el nombre `numQubits` anterior, esta entrada se proporcionaría en la línea de comandos mediante en `--num-qubits 4` lugar de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="de2b9-185">El mensaje de error también proporciona otras opciones que se pueden usar, incluida la forma de cambiar la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="de2b9-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="de2b9-186">Distintos equipos de destino</span><span class="sxs-lookup"><span data-stu-id="de2b9-186">Different target machines</span></span>

<span data-ttu-id="de2b9-187">Dado que las salidas de nuestras operaciones hasta ahora han sido los resultados esperados de su acción en qubits reales, está claro que el equipo de destino predeterminado de la línea de comandos es el simulador de Quantum de estado completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="de2b9-188">Sin embargo, podemos indicar a las llamadas que se ejecuten en un equipo de destino específico con la opción `--simulator` (o la abreviatura `-s` ).</span><span class="sxs-lookup"><span data-stu-id="de2b9-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="de2b9-189">Por ejemplo, podríamos ejecutarlo en [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="de2b9-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="de2b9-190">A continuación, la salida impresa es</span><span class="sxs-lookup"><span data-stu-id="de2b9-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="de2b9-191">Para más información sobre lo que indican estas métricas, consulte [estimación de recursos: métricas notificadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="de2b9-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="de2b9-192">Resumen de ejecución de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="de2b9-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="de2b9-193">Opciones no :::no-loc(Q#)::: `dotnet run` disponibles</span><span class="sxs-lookup"><span data-stu-id="de2b9-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="de2b9-194">Como se mencionó brevemente anteriormente con la `--project` opción, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) también acepta opciones no relacionadas con los argumentos a los que se :::no-loc(Q#)::: puede llamar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="de2b9-195">Si se proporcionan ambos tipos de opciones, `dotnet` se deben proporcionar primero las opciones específicas de, seguida de un delimitador `--` y, a continuación, las :::no-loc(Q#)::: Opciones específicas de.</span><span class="sxs-lookup"><span data-stu-id="de2b9-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="de2b9-196">Por ejemplo, la especificación de una ruta de acceso junto con un número qubits para la operación anterior se ejecutaría a través de `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="de2b9-197">:::no-loc(Q#)::: con programas host</span><span class="sxs-lookup"><span data-stu-id="de2b9-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="de2b9-198">Con nuestro :::no-loc(Q#)::: archivo a mano, una alternativa a llamar a una operación o a una función directamente desde el símbolo del sistema es usar un *programa host* en otro idioma clásico.</span><span class="sxs-lookup"><span data-stu-id="de2b9-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="de2b9-199">En concreto, esto se puede hacer con Python o con un lenguaje .NET como C# o F # (por motivos de brevedad, solo se detallará C# aquí).</span><span class="sxs-lookup"><span data-stu-id="de2b9-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="de2b9-200">Se requiere un poco más de configuración para habilitar la interoperabilidad, pero esos detalles se pueden encontrar en las [guías de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="de2b9-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="de2b9-201">En pocas palabras, la situación incluye ahora un archivo de programa host (por ejemplo, `*.py` o `*.cs` ) en la misma ubicación que el :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="de2b9-202">Ahora es el programa *host* que se ejecuta y mientras se está ejecutando, puede llamar a las :::no-loc(Q#)::: operaciones y funciones específicas desde el :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="de2b9-203">El núcleo de la interoperabilidad se basa en el :::no-loc(Q#)::: compilador, por lo que el contenido del :::no-loc(Q#)::: archivo es accesible para el programa host, de modo que se pueda llamar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="de2b9-204">Una de las principales ventajas de usar un programa host es que los datos clásicos devueltos por el :::no-loc(Q#)::: programa se pueden procesar posteriormente en el idioma del host.</span><span class="sxs-lookup"><span data-stu-id="de2b9-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="de2b9-205">Esto puede constar de un procesamiento de datos avanzado (por ejemplo, algo que no se puede realizar internamente en :::no-loc(Q#)::: ) y, a continuación, llamar a acciones adicionales en :::no-loc(Q#)::: función de los resultados, o algo tan sencillo como trazar los :::no-loc(Q#)::: resultados.</span><span class="sxs-lookup"><span data-stu-id="de2b9-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="de2b9-206">Aquí se muestra el esquema general y se describen las implementaciones específicas para Python y C# a continuación.</span><span class="sxs-lookup"><span data-stu-id="de2b9-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="de2b9-207">Puede encontrar un ejemplo de uso de un programa host de F # en los [ejemplos de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="de2b9-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="de2b9-208">El `@EntryPoint()` atributo usado para :::no-loc(Q#)::: las aplicaciones no se puede usar con programas host.</span><span class="sxs-lookup"><span data-stu-id="de2b9-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="de2b9-209">Se producirá un error si está presente en el :::no-loc(Q#)::: archivo al que llama un host.</span><span class="sxs-lookup"><span data-stu-id="de2b9-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="de2b9-210">Para trabajar con distintos programas host, no es necesario realizar ningún cambio en un `*.qs` :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="de2b9-211">Todas las implementaciones del programa host siguientes funcionan con el mismo :::no-loc(Q#)::: archivo:</span><span class="sxs-lookup"><span data-stu-id="de2b9-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="de2b9-212">Seleccione la pestaña correspondiente al idioma de su host de interés.</span><span class="sxs-lookup"><span data-stu-id="de2b9-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="de2b9-213">Python</span><span class="sxs-lookup"><span data-stu-id="de2b9-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="de2b9-214">Un programa host de Python se construye de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="de2b9-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="de2b9-215">Importe el `qsharp` módulo, que registra el cargador de módulos para la :::no-loc(Q#)::: interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="de2b9-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="de2b9-216">Esto permite :::no-loc(Q#)::: que los espacios de nombres aparezcan como módulos de Python, desde los que podemos "importar" a los que se puede :::no-loc(Q#)::: llamar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="de2b9-217">Tenga en cuenta que técnicamente no son las llamadas :::no-loc(Q#)::: que se importan, sino códigos auxiliares de Python que permiten llamar a ellos.</span><span class="sxs-lookup"><span data-stu-id="de2b9-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="de2b9-218">Estos se comportan como objetos de clases de Python.</span><span class="sxs-lookup"><span data-stu-id="de2b9-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="de2b9-219">Usamos métodos en estos objetos para especificar las máquinas de destino a las que se enviará la operación al ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="de2b9-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="de2b9-220">Importe las invocaciones :::no-loc(Q#)::: que llamaremos directamente---en este caso, `MeasureSuperposition` y `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="de2b9-221">Con el `qsharp` módulo importado, también puede importar llamadas directamente desde los espacios de nombres de la :::no-loc(Q#)::: biblioteca.</span><span class="sxs-lookup"><span data-stu-id="de2b9-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="de2b9-222">Entre cualquier otro código de Python, ahora puede llamar a esas llamadas en máquinas de destino específicas y asignar sus retornos a variables (si devuelven un valor) para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="de2b9-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="de2b9-223">Especificar equipos de destino</span><span class="sxs-lookup"><span data-stu-id="de2b9-223">Specifying target machines</span></span>
<span data-ttu-id="de2b9-224">La llamada a una operación que se va a ejecutar en un equipo de destino específico se realiza a través de diferentes métodos de Python en el objeto importado.</span><span class="sxs-lookup"><span data-stu-id="de2b9-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="de2b9-225">Por ejemplo, `.simulate(<args>)` , utiliza `QuantumSimulator` para ejecutar la operación, mientras que `.estimate_resources(<args>)` lo hace en `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="de2b9-226">Pasar entradas a Q\#</span><span class="sxs-lookup"><span data-stu-id="de2b9-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="de2b9-227">Los argumentos de la que se :::no-loc(Q#)::: puede llamar deben proporcionarse en forma de argumento de palabra clave, donde la palabra clave es el nombre del argumento en la definición que se :::no-loc(Q#)::: puede llamar.</span><span class="sxs-lookup"><span data-stu-id="de2b9-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="de2b9-228">Es decir, `MeasureSuperpositionArray.simulate(n=4)` es válido, mientras que `MeasureSuperpositionArray.simulate(4)` produciría un error.</span><span class="sxs-lookup"><span data-stu-id="de2b9-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="de2b9-229">Por lo tanto, el programa host de Python</span><span class="sxs-lookup"><span data-stu-id="de2b9-229">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="de2b9-230">da como resultado una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="de2b9-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="de2b9-231">Usar :::no-loc(Q#)::: código de otros proyectos o paquetes</span><span class="sxs-lookup"><span data-stu-id="de2b9-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="de2b9-232">De forma predeterminada, el `import qsharp` comando carga todos los `.qs` archivos de la carpeta actual y hace que sus :::no-loc(Q#)::: operaciones y funciones estén disponibles para su uso dentro del script de Python.</span><span class="sxs-lookup"><span data-stu-id="de2b9-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="de2b9-233">Para cargar :::no-loc(Q#)::: código desde otra carpeta, la [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) se puede usar para agregar una referencia a un `.csproj` archivo para un :::no-loc(Q#)::: proyecto (es decir, un proyecto que haga referencia a `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="de2b9-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="de2b9-234">Este comando compilará todos `.qs` los archivos de la carpeta que contengan `.csproj` y sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="de2b9-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="de2b9-235">También cargará de forma recursiva los paquetes a los que se hace referencia a través `PackageReference` de o los :::no-loc(Q#)::: proyectos a los que se hace referencia a través `ProjectReference` de en ese `.csproj` archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="de2b9-236">Por ejemplo, el siguiente código de Python importa un proyecto externo, haciendo referencia a su ruta de acceso relativa a la carpeta actual, e invoca una de sus :::no-loc(Q#)::: operaciones:</span><span class="sxs-lookup"><span data-stu-id="de2b9-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="de2b9-237">Esto resulta en una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="de2b9-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="de2b9-238">Para cargar paquetes externos que contienen :::no-loc(Q#)::: código, use la [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="de2b9-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="de2b9-239">Si el :::no-loc(Q#)::: código de la carpeta actual depende de los proyectos o paquetes externos, es posible que vea errores durante `import qsharp` la ejecución, ya que las dependencias no se han cargado todavía.</span><span class="sxs-lookup"><span data-stu-id="de2b9-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="de2b9-240">Para cargar los paquetes o proyectos externos necesarios :::no-loc(Q#)::: durante el `import qsharp` comando, asegúrese de que la carpeta con el script de Python contiene un `.csproj` archivo al que hace referencia `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="de2b9-241">En ese `.csproj` , agregue la propiedad `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="de2b9-242">Esto le indicará :::no-loc(Q#)::: Cómo cargar de forma recursiva `ProjectReference` los `PackageReference` elementos o encontrados en ese elemento `.csproj` durante el `import qsharp` comando.</span><span class="sxs-lookup"><span data-stu-id="de2b9-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="de2b9-243">Por ejemplo, este es un `.csproj` archivo simple que hace que se :::no-loc(Q#)::: cargue el `Microsoft.Quantum.Chemistry` paquete automáticamente:</span><span class="sxs-lookup"><span data-stu-id="de2b9-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="de2b9-244">Actualmente, esta `<IQSharpLoadAutomatically>` propiedad personalizada es necesaria para los hosts de Python, pero en el futuro, esto puede convertirse en el comportamiento predeterminado de un `.csproj` archivo ubicado en la misma carpeta que el script de Python.</span><span class="sxs-lookup"><span data-stu-id="de2b9-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-245">Actualmente el `<QsharpCompile>` valor de `.csproj` se omite en los hosts de Python y `.qs` `.csproj` se cargan y compilan todos los archivos de la carpeta de (incluidas las subcarpetas).</span><span class="sxs-lookup"><span data-stu-id="de2b9-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="de2b9-246">La compatibilidad con `.csproj` la configuración se mejorará en el futuro (consulte [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) para obtener más detalles).</span><span class="sxs-lookup"><span data-stu-id="de2b9-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="de2b9-247">C#</span><span class="sxs-lookup"><span data-stu-id="de2b9-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="de2b9-248">Un programa host de C# tiene varios componentes y funciona muy estrechamente con algunos componentes del QDK, como los simuladores, que se basan en C#.</span><span class="sxs-lookup"><span data-stu-id="de2b9-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="de2b9-249">El :::no-loc(Q#)::: compilador funciona aquí generando un espacio de nombres de C# denominado de forma equivalente a partir del :::no-loc(Q#)::: espacio de nombres en el :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="de2b9-250">Además, genera una clase de C# con nombre equivalente para cada una de las :::no-loc(Q#)::: llamadas o tipos definidos en ella.</span><span class="sxs-lookup"><span data-stu-id="de2b9-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="de2b9-251">En primer lugar, las clases que se usan en nuestro programa host estarán disponibles con `using` instrucciones, que son aproximadamente análogo a las `open` instrucciones del :::no-loc(Q#)::: archivo:</span><span class="sxs-lookup"><span data-stu-id="de2b9-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="de2b9-252">Después, declaramos nuestro espacio de nombres de C#, algunos otros bits y partes (vea el bloque de código completo a continuación) y, después, cualquier programación clásica que nos gustaría (por ejemplo, calculando argumentos para las :::no-loc(Q#)::: llamadas).</span><span class="sxs-lookup"><span data-stu-id="de2b9-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="de2b9-253">Este último no es necesario en nuestro caso, pero se puede encontrar un ejemplo de este uso en el  [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="de2b9-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="de2b9-254">Máquinas de destino</span><span class="sxs-lookup"><span data-stu-id="de2b9-254">Target machines</span></span>

<span data-ttu-id="de2b9-255">Al volver a :::no-loc(Q#)::: , se debe crear una instancia del equipo de destino en el que se ejecutarán nuestras operaciones.</span><span class="sxs-lookup"><span data-stu-id="de2b9-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="de2b9-256">El uso de otras máquinas de destino es tan sencillo como crear una instancia de una diferente, aunque la manera de hacerlo y el procesamiento de las devoluciones puede ser ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="de2b9-257">Por motivos de brevedad, nos centramos [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ahora en y incluimos lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [siguiente](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="de2b9-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="de2b9-258">Cada clase de C# generada a partir de las :::no-loc(Q#)::: operaciones tiene un `Run` método, el primer argumento de que debe ser la instancia del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="de2b9-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="de2b9-259">Por lo tanto, para ejecutar `MeasureSuperposition` en `QuantumSimulator` , usamos `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="de2b9-260">Los resultados devueltos se pueden asignar a las variables en C#:</span><span class="sxs-lookup"><span data-stu-id="de2b9-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="de2b9-261">El `Run` método se ejecuta de forma asincrónica porque es el caso del hardware Quantum real y, por lo tanto, la `await` palabra clave bloquea el procesamiento hasta que se completa la tarea.</span><span class="sxs-lookup"><span data-stu-id="de2b9-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="de2b9-262">Si el que :::no-loc(Q#)::: se puede llamar no tiene ningún resultado (por ejemplo, tiene el tipo de valor devuelto `Unit` ), la ejecución todavía se puede realizar de la misma manera sin asignarla a una variable.</span><span class="sxs-lookup"><span data-stu-id="de2b9-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="de2b9-263">En ese caso, la línea completa simplemente consistiría en</span><span class="sxs-lookup"><span data-stu-id="de2b9-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="de2b9-264">Argumentos</span><span class="sxs-lookup"><span data-stu-id="de2b9-264">Arguments</span></span>

<span data-ttu-id="de2b9-265">Los argumentos de los que :::no-loc(Q#)::: se pueden llamar se pasan simplemente como argumentos adicionales después del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="de2b9-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="de2b9-266">Por lo tanto, los resultados de `MeasureSuperpositionArray` en `n=4` qubits se capturaban mediante</span><span class="sxs-lookup"><span data-stu-id="de2b9-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="de2b9-267">Por tanto, un programa host de C# completo podría ser similar a</span><span class="sxs-lookup"><span data-stu-id="de2b9-267">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="de2b9-268">En la ubicación del archivo de C#, el programa host se puede ejecutar desde el símbolo del sistema. para ello, escriba</span><span class="sxs-lookup"><span data-stu-id="de2b9-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="de2b9-269">y en este caso, verá que la salida se escribe en la consola de forma similar a</span><span class="sxs-lookup"><span data-stu-id="de2b9-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="de2b9-270">Debido a la interoperabilidad del compilador con los espacios de nombres, podríamos hacer que las :::no-loc(Q#)::: llamadas a las llamadas estén disponibles sin la `using NamespaceName;` instrucción y simplemente hacer coincidir el título del espacio de nombres de C# con ella.</span><span class="sxs-lookup"><span data-stu-id="de2b9-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="de2b9-271">Es decir, reemplazando `namespace host` por `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="de2b9-272">Inclusión del estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="de2b9-272">Including the resources estimator</span></span>

<span data-ttu-id="de2b9-273">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requiere una implementación ligeramente diferente para recuperar la salida.</span><span class="sxs-lookup"><span data-stu-id="de2b9-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="de2b9-274">En primer lugar, en lugar de crear instancias de ellas como una variable con una `using` instrucción (como hacemos con `QuantumSimulator` ), se crean instancias de los objetos de la clase directamente a través de</span><span class="sxs-lookup"><span data-stu-id="de2b9-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="de2b9-275">Tenga en cuenta que, en lugar de un único simulador de destino que se va a usar en varias :::no-loc(Q#)::: operaciones, hemos creado una instancia de para cada uno.</span><span class="sxs-lookup"><span data-stu-id="de2b9-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="de2b9-276">Esto se debe a que los propios objetos se modifican cuando se usan como equipos de destino, y los resultados se pueden recuperar posteriormente con el método de clase `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="de2b9-277">Para ejecutar las operaciones en los estimadores de recursos, usamos</span><span class="sxs-lookup"><span data-stu-id="de2b9-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="de2b9-278">y, a continuación, recupere los resultados como valores separados por tabulaciones (TSV) con `estimatorSingleQ.ToTSV()` y `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="de2b9-279">Por lo tanto, un programa host de C# completo que usa `QuantumSimulator` y `ResourcesEstimator` puede tener la forma:</span><span class="sxs-lookup"><span data-stu-id="de2b9-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="de2b9-280">lo que produciría una salida similar a</span><span class="sxs-lookup"><span data-stu-id="de2b9-280">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="de2b9-281">:::no-loc(Q#)::: Cuadernos de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="de2b9-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="de2b9-282">:::no-loc(Q#)::: Los cuadernos de Jupyter Notebook usan el :::no-loc(Q#)::: kernel I, que permite definir, compilar y ejecutar :::no-loc(Q#)::: llamadas en un solo cuaderno---todo, junto con instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="de2b9-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="de2b9-283">Esto significa que, aunque es posible importar y usar el contenido de `*.qs` :::no-loc(Q#)::: los archivos, no son necesarios en el modelo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="de2b9-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="de2b9-284">Aquí veremos cómo ejecutar las :::no-loc(Q#)::: operaciones definidas anteriormente, pero se proporciona una introducción más amplia al uso de :::no-loc(Q#)::: cuadernos de Jupyter notebooks en la [Introducción a los :::no-loc(Q#)::: cuadernos de Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="de2b9-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="de2b9-285">Definir operaciones</span><span class="sxs-lookup"><span data-stu-id="de2b9-285">Defining operations</span></span>

<span data-ttu-id="de2b9-286">En un :::no-loc(Q#)::: Jupyter Notebook, escriba :::no-loc(Q#)::: el código tal y como lo haríamos dentro del espacio de nombres de un :::no-loc(Q#)::: archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="de2b9-287">Por lo tanto, se puede habilitar el acceso a las llamadas desde las [ :::no-loc(Q#)::: bibliotecas estándar](xref:microsoft.quantum.qsharplibintro) con `open` instrucciones para sus respectivos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="de2b9-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="de2b9-288">Al ejecutar una celda con esta instrucción, las definiciones de esos espacios de nombres están disponibles en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-289">Las llamadas de [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic) y [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (por ejemplo, [`H`](xref:Microsoft.Quantum.Intrinsic.H) y [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) están disponibles automáticamente para las operaciones definidas dentro de las celdas de :::no-loc(Q#)::: cuadernos de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="de2b9-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="de2b9-290">Sin embargo, esto no es cierto para el código que se incorpora desde :::no-loc(Q#)::: archivos de origen externos (un proceso que se muestra en los [cuadernos de introducción a :::no-loc(Q#)::: y Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="de2b9-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="de2b9-291">Del mismo modo, la definición de operaciones solo requiere escribir el :::no-loc(Q#)::: código y ejecutar la celda.</span><span class="sxs-lookup"><span data-stu-id="de2b9-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="de2b9-292">A continuación, la salida muestra las operaciones, a las que se puede llamar desde las celdas futuras.</span><span class="sxs-lookup"><span data-stu-id="de2b9-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="de2b9-293">Máquinas de destino</span><span class="sxs-lookup"><span data-stu-id="de2b9-293">Target machines</span></span>

<span data-ttu-id="de2b9-294">La funcionalidad para ejecutar operaciones en máquinas de destino específicas se proporciona a través de [ :::no-loc(Q#)::: comandos mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="de2b9-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="de2b9-295">Por ejemplo, `%simulate` hace uso de `QuantumSimulator` y `%estimate` usa `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="de2b9-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="de2b9-296">Pasar entradas a funciones y operaciones</span><span class="sxs-lookup"><span data-stu-id="de2b9-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="de2b9-297">Para pasar entradas a las :::no-loc(Q#)::: operaciones, los argumentos se pueden pasar como `key=value` pares al comando de ejecución mágica.</span><span class="sxs-lookup"><span data-stu-id="de2b9-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="de2b9-298">Por lo tanto, para ejecutar `MeasureSuperpositionArray` con cuatro qubits, podemos ejecutar `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="de2b9-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="de2b9-299">Este patrón se puede usar de forma similar con `%estimate` y otros comandos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="de2b9-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="de2b9-300">Usar :::no-loc(Q#)::: código de otros proyectos o paquetes</span><span class="sxs-lookup"><span data-stu-id="de2b9-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="de2b9-301">De forma predeterminada, un :::no-loc(Q#)::: Jupyter Notebook carga todos los `.qs` archivos de la carpeta actual y hace que sus :::no-loc(Q#)::: operaciones y funciones estén disponibles para su uso desde dentro del cuaderno.</span><span class="sxs-lookup"><span data-stu-id="de2b9-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="de2b9-302">El [ `%who` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.who) muestra todas las :::no-loc(Q#)::: operaciones y funciones disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="de2b9-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="de2b9-303">Para cargar :::no-loc(Q#)::: código desde otra carpeta, el [ `%project` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) se puede usar para agregar una referencia a un `.csproj` archivo para un :::no-loc(Q#)::: proyecto (es decir, un proyecto que haga referencia a `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="de2b9-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="de2b9-304">Este comando compilará los `.qs` archivos de la carpeta que contengan `.csproj` (y las subcarpetas).</span><span class="sxs-lookup"><span data-stu-id="de2b9-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="de2b9-305">También cargará de forma recursiva los paquetes a los que se hace referencia a través `PackageReference` de o los :::no-loc(Q#)::: proyectos a los que se hace referencia a través `ProjectReference` de en ese `.csproj` archivo.</span><span class="sxs-lookup"><span data-stu-id="de2b9-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="de2b9-306">Como ejemplo, las siguientes celdas simulan una :::no-loc(Q#)::: operación desde un proyecto externo, donde se hace referencia a la ruta de acceso del proyecto en relación con la carpeta actual:</span><span class="sxs-lookup"><span data-stu-id="de2b9-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="de2b9-307">Para cargar paquetes externos que contienen :::no-loc(Q#)::: código, use el [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="de2b9-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="de2b9-308">La carga de un paquete también estará disponible para los comandos mágicos personalizados o para mostrar los codificadores contenidos en los ensamblados que formen parte del paquete.</span><span class="sxs-lookup"><span data-stu-id="de2b9-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="de2b9-309">Para cargar los paquetes externos o :::no-loc(Q#)::: los proyectos en el inicialización del cuaderno, asegúrese de que la carpeta del cuaderno contiene un `.csproj` archivo al que hace referencia `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="de2b9-310">En ese `.csproj` , agregue la propiedad `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="de2b9-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="de2b9-311">Esto le indicará :::no-loc(Q#)::: Cómo cargar de forma recursiva todos los `ProjectReference` `PackageReference` elementos que se encuentren en ese en `.csproj` el momento de la carga del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="de2b9-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="de2b9-312">Por ejemplo, este es un `.csproj` archivo simple que hace que se :::no-loc(Q#)::: cargue el `Microsoft.Quantum.Chemistry` paquete automáticamente:</span><span class="sxs-lookup"><span data-stu-id="de2b9-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="de2b9-313">Actualmente, esta `<IQSharpLoadAutomatically>` propiedad personalizada es necesaria :::no-loc(Q#)::: para los hosts de Jupyter Notebook, pero en el futuro, esto puede convertirse en el comportamiento predeterminado de un `.csproj` archivo ubicado en la misma carpeta que el archivo del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="de2b9-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="de2b9-314">En la actualidad `<QsharpCompile>` `.csproj` , Jupyter Notebook los hosts omiten la configuración de :::no-loc(Q#)::: , y todos los `.qs` archivos de la carpeta de `.csproj` (incluidas las subcarpetas) se cargan y compilan.</span><span class="sxs-lookup"><span data-stu-id="de2b9-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="de2b9-315">La compatibilidad con `.csproj` la configuración se mejorará en el futuro (consulte [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) para obtener más detalles).</span><span class="sxs-lookup"><span data-stu-id="de2b9-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
