---
title: Formas de ejecutar un programa de preguntas y respuestas
description: 'Información general de las diferentes formas de ejecutar programas de Q #. Desde la línea de comandos, p # Jupyter notebooks y los programas host clásico en Python o en un lenguaje .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887735"
---
# <a name="ways-to-run-a-q-program"></a><span data-ttu-id="bbafd-104">Formas de ejecutar un programa de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="bbafd-104">Ways to run a Q# program</span></span>

<span data-ttu-id="bbafd-105">Uno de los mayores puntos fuertes del kit de desarrollo de Quantum es su flexibilidad en plataformas y entornos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="bbafd-106">Sin embargo, esto también significa que los nuevos usuarios de preguntas y respuestas se pueden confundir o saturar mediante las numerosas opciones que se encuentran en la [Guía de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="bbafd-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="bbafd-107">En esta página, se explica lo que ocurre cuando se ejecuta un programa de preguntas y respuestas, y se comparan las distintas formas en que los usuarios pueden hacerlo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="bbafd-108">Una distinción principal es que se puede ejecutar Q #:</span><span class="sxs-lookup"><span data-stu-id="bbafd-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="bbafd-109">como aplicación independiente, donde Q # es el único lenguaje implicado y el programa se invoca directamente.</span><span class="sxs-lookup"><span data-stu-id="bbafd-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="bbafd-110">En realidad, dos métodos se encuentran en esta categoría:</span><span class="sxs-lookup"><span data-stu-id="bbafd-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="bbafd-111">la interfaz de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="bbafd-111">the command line interface</span></span>
  - <span data-ttu-id="bbafd-112">Cuadernos de Jupyter Notebook de Q#</span><span class="sxs-lookup"><span data-stu-id="bbafd-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="bbafd-113">con un *programa host*adicional, escrito en Python o en un lenguaje .net (por ejemplo, C# o F #), que, a continuación, invoca el programa y puede procesar aún más los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="bbafd-114">Para comprender mejor estos procesos y sus diferencias, se considera un programa sencillo de Q # y se comparan las formas en que se pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="bbafd-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-q-program"></a><span data-ttu-id="bbafd-115">Programa Basic Q #</span><span class="sxs-lookup"><span data-stu-id="bbafd-115">Basic Q# program</span></span>

<span data-ttu-id="bbafd-116">Un programa Quantum básico puede constar de la preparación de una qubit en una superposición de Estados $ \ket {0} $ y $ \ket {1} $, la medición y la devolución del resultado, que será aleatoriamente uno de estos dos Estados con la misma probabilidad.</span><span class="sxs-lookup"><span data-stu-id="bbafd-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="bbafd-117">En realidad, este proceso es el núcleo de la guía de inicio rápido del [generador de números aleatorios de Quantum](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="bbafd-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="bbafd-118">En Q #, esto se realizaría mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbafd-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="bbafd-119">Sin embargo, este código no se puede ejecutar por sí.</span><span class="sxs-lookup"><span data-stu-id="bbafd-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="bbafd-120">Para ello, debe componer el cuerpo de una [operación](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que se ejecuta cuando se llama---directamente o mediante otra operación.</span><span class="sxs-lookup"><span data-stu-id="bbafd-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="bbafd-121">Por lo tanto, puede escribir una operación de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="bbafd-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="bbafd-122">Ha definido una operación, `MeasureSuperposition` , que no toma ninguna entrada y devuelve un valor de tipo [result](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="bbafd-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="bbafd-123">Aunque los ejemplos de esta página solo se componen de *operaciones*de preguntas y respuestas, todos los conceptos que trataremos se refieren igualmente a *las funciones*de q # y, por lo tanto, hacemos referencia a ellos de forma colectiva como *llamadas*.</span><span class="sxs-lookup"><span data-stu-id="bbafd-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="bbafd-124">Sus diferencias se describen en [preguntas y respuestas básicas: las operaciones y las funciones](xref:microsoft.quantum.guide.basics#q-operations-and-functions), y más detalles sobre cómo definirlas se pueden encontrar en [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="bbafd-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-q-file"></a><span data-ttu-id="bbafd-125">Se puede llamar en un archivo de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="bbafd-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="bbafd-126">A la que se puede llamar es precisamente lo que se llama y ejecuta en Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="bbafd-127">Sin embargo, requiere unas cuantas adiciones más para incluir un archivo de `*.qs` preguntas # completo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="bbafd-128">En los *espacios de nombres*se definen todos los tipos Q # y se pueden llamar (ambos definidos y los intrínsecos al lenguaje), que proporcionan cada nombre completo al que se puede hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="bbafd-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="bbafd-129">Por ejemplo, las [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operaciones y se encuentran en los [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) espacios de [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) nombres y (parte de las bibliotecas de preguntas y [respuestas](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="bbafd-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="bbafd-130">Como tal, siempre se les puede llamar a través de sus nombres *completos* `Microsoft.Quantum.Intrinsic.H(<qubit>)` y `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , pero siempre esto provocaría un código muy saturado.</span><span class="sxs-lookup"><span data-stu-id="bbafd-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="bbafd-131">En su lugar, `open` las instrucciones permiten hacer referencia a las llamadas con una abreviatura más concisa, como hemos hecho en el cuerpo de la operación anterior.</span><span class="sxs-lookup"><span data-stu-id="bbafd-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="bbafd-132">El archivo de preguntas y respuestas completo que contiene nuestra operación consistiría en definir nuestro propio espacio de nombres, abriendo los espacios de nombres de los que se llamaron en la operación y, a continuación, nuestra operación:</span><span class="sxs-lookup"><span data-stu-id="bbafd-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="bbafd-133">También se pueden asignar *alias* a los espacios de nombres cuando se abren, lo que puede resultar útil si se producen conflictos entre los nombres de tipo o los tipos en dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="bbafd-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="bbafd-134">Por ejemplo, en su lugar podríamos usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` anteriormente y, a continuación, llamar a `H` mediante `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="bbafd-135">Una excepción a todo esto es el [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) espacio de nombres, que siempre se abre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bbafd-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="bbafd-136">Por lo tanto, [`Length`](xref:microsoft.quantum.core.length) se pueden usar directamente llamadas como siempre.</span><span class="sxs-lookup"><span data-stu-id="bbafd-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="bbafd-137">Ejecución en equipos de destino</span><span class="sxs-lookup"><span data-stu-id="bbafd-137">Execution on target machines</span></span>

<span data-ttu-id="bbafd-138">Ahora el modelo de ejecución general de un programa de preguntas y respuestas está claro.</span><span class="sxs-lookup"><span data-stu-id="bbafd-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="bbafd-139">En primer lugar, el llamador específico que se va a ejecutar tiene acceso a cualquier otro tipo que se pueda llamar y que se haya definido en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bbafd-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="bbafd-140">También tiene acceso a los de cualquiera de las [bibliotecas de preguntas y respuestas](xref:microsoft.quantum.libraries), pero se debe hacer referencia a ellos mediante su nombre completo, o bien mediante el uso de `open` instrucciones descritas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bbafd-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="bbafd-141">A continuación, se puede llamar a en un *[equipo de destino](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="bbafd-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="bbafd-142">Estas máquinas de destino pueden ser hardware de Quantum real o varios simuladores disponibles como parte de QDK.</span><span class="sxs-lookup"><span data-stu-id="bbafd-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="bbafd-143">Para nuestros fines aquí, el equipo de destino más útil es una instancia del [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , que calcula el comportamiento del programa como si se ejecutara en un equipo Quantum sin ruido.</span><span class="sxs-lookup"><span data-stu-id="bbafd-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="bbafd-144">Hasta ahora, hemos descrito lo que sucede cuando se ejecuta una acción Callable concreta.</span><span class="sxs-lookup"><span data-stu-id="bbafd-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="bbafd-145">Independientemente de si se usa Q # en una aplicación independiente o con un programa host, este proceso general es más o menos el mismo---, por lo tanto, la flexibilidad de QDK.</span><span class="sxs-lookup"><span data-stu-id="bbafd-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="bbafd-146">Por lo tanto, las diferencias entre las diferentes formas de llamar al kit de desarrollo de Quantum se revelan en el *modo* en que se llama a Q # Callable y en qué manera se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="bbafd-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="bbafd-147">Más concretamente, las diferencias giran en torno a</span><span class="sxs-lookup"><span data-stu-id="bbafd-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="bbafd-148">que indica qué Q # Callable se va a ejecutar,</span><span class="sxs-lookup"><span data-stu-id="bbafd-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="bbafd-149">Cómo se proporcionan los posibles argumentos a los que se puede llamar,</span><span class="sxs-lookup"><span data-stu-id="bbafd-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="bbafd-150">especificar el equipo de destino en el que se va a ejecutar y</span><span class="sxs-lookup"><span data-stu-id="bbafd-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="bbafd-151">Cómo se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="bbafd-151">how any results are returned.</span></span>

<span data-ttu-id="bbafd-152">En primer lugar, se describe cómo hacerlo con la aplicación de preguntas y respuestas independientes desde la línea de comandos y, a continuación, se sigue usando los programas host de Python y C#.</span><span class="sxs-lookup"><span data-stu-id="bbafd-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="bbafd-153">Nos reservamos la aplicación independiente de cuadernos de Jupyter Notebook en último lugar, ya que, a diferencia de las tres primeras, su funcionalidad principal no se centra en un archivo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="bbafd-154">Aunque no se muestra en estos ejemplos, una diferencia entre los métodos de ejecución es que todos los mensajes impresos desde dentro del programa de preguntas y respuestas (por [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ejemplo, o, por ejemplo) se imprimirán normalmente en la consola correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbafd-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="q-from-the-command-line"></a><span data-ttu-id="bbafd-155">Q # desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="bbafd-155">Q# from the command line</span></span>
<span data-ttu-id="bbafd-156">Una de las formas más sencillas de empezar a escribir programas de preguntas y respuestas es evitar tener que preocuparse por los archivos independientes y un segundo idioma.</span><span class="sxs-lookup"><span data-stu-id="bbafd-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="bbafd-157">El uso de Visual Studio Code o Visual Studio con la extensión QDK permite un flujo de trabajo sin problemas en el que se ejecutan Q # Calling desde un solo archivo Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="bbafd-158">Para ello, se invocará en última instancia la ejecución del programa escribiendo</span><span class="sxs-lookup"><span data-stu-id="bbafd-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="bbafd-159">en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-159">in the command line.</span></span>
<span data-ttu-id="bbafd-160">El flujo de trabajo más sencillo es cuando la ubicación del directorio del terminal es igual que el archivo de preguntas y respuestas, que se puede controlar fácilmente junto con la edición de archivos de preguntas y respuestas mediante el terminal integrado de VS Code, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="bbafd-161">Sin embargo, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) acepta numerosas opciones y el programa también se puede ejecutar desde una ubicación diferente, simplemente proporcionando `--project <PATH>` con la ubicación del archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-q-file"></a><span data-ttu-id="bbafd-162">Agregar punto de entrada al archivo de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="bbafd-162">Add entry point to Q# file</span></span>

<span data-ttu-id="bbafd-163">La mayoría de los archivos Q # contendrán más de un invocable, por lo que es necesario dejar que el compilador sepa *qué* llamadas se deben ejecutar cuando se proporciona el `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="bbafd-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="bbafd-164">Esto se hace con un cambio sencillo en el propio archivo de preguntas #:</span><span class="sxs-lookup"><span data-stu-id="bbafd-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="bbafd-165">Agregue una línea `@EntryPoint()` que preceda directamente a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="bbafd-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="bbafd-166">Por lo tanto, el archivo anterior se convertiría en</span><span class="sxs-lookup"><span data-stu-id="bbafd-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="bbafd-167">Ahora, una llamada de `dotnet run` desde la línea de comandos conduce a `MeasureSuperposition` ejecutarse y, a continuación, el valor devuelto se imprime directamente en el terminal.</span><span class="sxs-lookup"><span data-stu-id="bbafd-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="bbafd-168">Por lo tanto, verá `One` o `Zero` imprimirá.</span><span class="sxs-lookup"><span data-stu-id="bbafd-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="bbafd-169">Tenga en cuenta que no importa si tiene más llamadas definidas debajo, solo se `MeasureSuperposition` ejecutará.</span><span class="sxs-lookup"><span data-stu-id="bbafd-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="bbafd-170">Además, no hay ningún problema si su llamador incluye [comentarios de documentación](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes de su declaración, el `@EntryPoint()` atributo se puede colocar simplemente encima de ellos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="bbafd-171">Argumentos Invocables</span><span class="sxs-lookup"><span data-stu-id="bbafd-171">Callable arguments</span></span>

<span data-ttu-id="bbafd-172">Hasta ahora, solo hemos considerado una operación que no toma ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="bbafd-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="bbafd-173">Supongamos que deseamos realizar una operación similar, pero en varios qubits---el número de que se proporciona como argumento.</span><span class="sxs-lookup"><span data-stu-id="bbafd-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="bbafd-174">Este tipo de operación podría escribirse como</span><span class="sxs-lookup"><span data-stu-id="bbafd-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="bbafd-175">donde el valor devuelto es una matriz de los resultados de la medición.</span><span class="sxs-lookup"><span data-stu-id="bbafd-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="bbafd-176">Tenga en cuenta que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) y [`ForEach`](xref:microsoft.quantum.arrays.foreach) se encuentran en los [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) espacios de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nombres y, que requieren `open` instrucciones adicionales para cada uno.</span><span class="sxs-lookup"><span data-stu-id="bbafd-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="bbafd-177">Si movemos el `@EntryPoint()` atributo para que preceda a esta nueva operación (tenga en cuenta que solo puede haber una de estas líneas en un archivo), intentar ejecutarlo simplemente `dotnet run` genera un mensaje de error que indica qué opciones de línea de comandos adicionales son necesarias y cómo expresarlos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="bbafd-178">El formato general de la línea de comandos es realmente `dotnet run [options]` , y los argumentos que se pueden llamar se proporcionan allí.</span><span class="sxs-lookup"><span data-stu-id="bbafd-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="bbafd-179">En este caso, falta el argumento `n` y se muestra que es necesario proporcionar la opción `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="bbafd-180">`MeasureSuperpositionArray` `n=4` Por lo tanto, para ejecutar para qubits, usamos</span><span class="sxs-lookup"><span data-stu-id="bbafd-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="bbafd-181">producir una salida similar a</span><span class="sxs-lookup"><span data-stu-id="bbafd-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="bbafd-182">Esto se extiende a varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="bbafd-183">`camelCase`El compilador modifica ligeramente los nombres de argumento definidos en para que se acepten como entradas de Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="bbafd-184">Por ejemplo, si en lugar de `n` , usamos el nombre `numQubits` anterior, esta entrada se proporcionaría en la línea de comandos mediante en `--num-qubits 4` lugar de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="bbafd-185">El mensaje de error también proporciona otras opciones que se pueden usar, incluida la forma de cambiar la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="bbafd-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="bbafd-186">Distintos equipos de destino</span><span class="sxs-lookup"><span data-stu-id="bbafd-186">Different target machines</span></span>

<span data-ttu-id="bbafd-187">Dado que las salidas de nuestras operaciones hasta ahora han sido los resultados esperados de su acción en qubits reales, está claro que el equipo de destino predeterminado de la línea de comandos es el simulador de quauntum de estado completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="bbafd-188">Sin embargo, podemos indicar a las llamadas que se ejecuten en un equipo de destino específico con la opción `--simulator` (o la abreviatura `-s` ).</span><span class="sxs-lookup"><span data-stu-id="bbafd-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="bbafd-189">Por ejemplo, podríamos ejecutarlo en [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="bbafd-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="bbafd-190">A continuación, la salida impresa es</span><span class="sxs-lookup"><span data-stu-id="bbafd-190">The printed output is then</span></span>

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

<span data-ttu-id="bbafd-191">Para más información sobre lo que indican estas métricas, consulte [estimación de recursos: métricas notificadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="bbafd-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="bbafd-192">Resumen de ejecución de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="bbafd-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a><span data-ttu-id="bbafd-193">Opciones que no son de Q # `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="bbafd-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="bbafd-194">Como se mencionó brevemente anteriormente con la `--project` opción, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) también acepta opciones no relacionadas con los argumentos de Q # Callable.</span><span class="sxs-lookup"><span data-stu-id="bbafd-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="bbafd-195">Si se proporcionan ambos tipos de opciones, `dotnet` se deben proporcionar primero las opciones específicas de, seguida de un delimitador `--` y, a continuación, las opciones específicas de Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="bbafd-196">Por ejemplo, si se especifica una ruta de acceso junto con un número qubits para la operación anterior, se ejecutaría a través de `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="q-with-host-programs"></a><span data-ttu-id="bbafd-197">Preguntas # con programas host</span><span class="sxs-lookup"><span data-stu-id="bbafd-197">Q# with host programs</span></span>

<span data-ttu-id="bbafd-198">Con el archivo Q # a mano, una alternativa a llamar a una operación o función directamente desde la línea de comandos es usar un *programa host* en otro lenguaje clásico.</span><span class="sxs-lookup"><span data-stu-id="bbafd-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="bbafd-199">En concreto, esto se puede hacer con Python o con un lenguaje .NET como C# o F # (por motivos de brevedad, solo se detallará C# aquí).</span><span class="sxs-lookup"><span data-stu-id="bbafd-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="bbafd-200">Se requiere un poco más de configuración para habilitar la interoperabilidad, pero esos detalles se pueden encontrar en las [guías de instalación](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="bbafd-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="bbafd-201">En pocas palabras, la situación incluye ahora un archivo de programa de host (por ejemplo, `*.py` o `*.cs` ) en la misma ubicación que el archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="bbafd-202">Ahora es el programa *host* que se ejecuta y, en el transcurso de su ejecución, puede llamar a funciones y operaciones de q # específicas desde el archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="bbafd-203">El núcleo de la interoperabilidad se basa en el compilador de Q #, de modo que el contenido del archivo Q # es accesible para el programa host, de forma que se pueda llamar.</span><span class="sxs-lookup"><span data-stu-id="bbafd-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="bbafd-204">Una de las principales ventajas de usar un programa host es que los datos clásicos devueltos por el programa de preguntas y respuestas se pueden procesar posteriormente en el idioma del host.</span><span class="sxs-lookup"><span data-stu-id="bbafd-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="bbafd-205">Esto puede constar de un procesamiento de datos avanzado (por ejemplo, algo que no se puede realizar internamente en Q #) y, después, llamar a más acciones de Q # en función de los resultados, o algo tan sencillo como trazar los resultados de Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="bbafd-206">Aquí se muestra el esquema general y se describen las implementaciones específicas para Python y C# a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbafd-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="bbafd-207">Puede encontrar un ejemplo de uso de un programa host de F # en los [ejemplos de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="bbafd-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="bbafd-208">El `@EntryPoint()` atributo usado para las aplicaciones de línea de comandos de Q # no se puede usar con programas host.</span><span class="sxs-lookup"><span data-stu-id="bbafd-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="bbafd-209">Se producirá un error si está presente en el archivo Q # al que llama un host.</span><span class="sxs-lookup"><span data-stu-id="bbafd-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="bbafd-210">Para trabajar con distintos programas host, no es necesario realizar ningún cambio en un `*.qs` archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="bbafd-211">Todas las implementaciones del programa host siguientes funcionan con el mismo archivo de preguntas #:</span><span class="sxs-lookup"><span data-stu-id="bbafd-211">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="bbafd-212">Seleccione la pestaña correspondiente al idioma de su host de interés.</span><span class="sxs-lookup"><span data-stu-id="bbafd-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="bbafd-213">Python</span><span class="sxs-lookup"><span data-stu-id="bbafd-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="bbafd-214">Un programa host de Python se construye de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bbafd-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="bbafd-215">Importe el `qsharp` módulo, que registra el cargador de módulos para la interoperabilidad de Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="bbafd-216">Esto permite que los espacios de nombres de Q # aparezcan como módulos de Python, desde los que se pueden "importar" preguntas # Invocables.</span><span class="sxs-lookup"><span data-stu-id="bbafd-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="bbafd-217">Tenga en cuenta que técnicamente no son las llamadas a preguntas y respuestas que se importan, sino códigos auxiliares de Python que permiten llamar a ellos.</span><span class="sxs-lookup"><span data-stu-id="bbafd-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="bbafd-218">Estos se comportan como objetos de las clases de Python, en los que usamos métodos para especificar las máquinas de destino a las que se debe enviar la operación para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="bbafd-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="bbafd-219">Importe estas Q # Callable que llamaremos directamente---en este caso, `MeasureSuperposition` y `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="bbafd-220">Con el `qsharp` módulo importado, también puede importar llamadas directamente desde los espacios de nombres de la biblioteca de Q #.</span><span class="sxs-lookup"><span data-stu-id="bbafd-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="bbafd-221">Entre cualquier otro código de Python, ahora puede llamar a esas llamadas en máquinas de destino específicas y asignar sus retornos a variables (si devuelven un valor) para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="bbafd-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="bbafd-222">Especificar equipos de destino</span><span class="sxs-lookup"><span data-stu-id="bbafd-222">Specifying target machines</span></span>
<span data-ttu-id="bbafd-223">La llamada a una operación que se va a ejecutar en un equipo de destino específico se realiza a través de diferentes métodos de Python en el objeto importado.</span><span class="sxs-lookup"><span data-stu-id="bbafd-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="bbafd-224">Por ejemplo, `.simulate(<args>)` , utiliza `QuantumSimulator` para ejecutar la operación, mientras que `.estimate_resources(<args>)` lo hace en `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="bbafd-225">Pasar entradas a Q\#</span><span class="sxs-lookup"><span data-stu-id="bbafd-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="bbafd-226">Los argumentos de Q # Callable se deben proporcionar en forma de argumento de palabra clave, donde la palabra clave es el nombre del argumento en la definición de Q # Callable.</span><span class="sxs-lookup"><span data-stu-id="bbafd-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="bbafd-227">Es decir, `MeasureSuperpositionArray.simulate(n=4)` es válido, mientras que `MeasureSuperpositionArray.simulate(4)` produciría un error.</span><span class="sxs-lookup"><span data-stu-id="bbafd-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="bbafd-228">Por lo tanto, el programa host de Python</span><span class="sxs-lookup"><span data-stu-id="bbafd-228">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="bbafd-229">da como resultado una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbafd-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="bbafd-230">C#</span><span class="sxs-lookup"><span data-stu-id="bbafd-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="bbafd-231">Un programa host de C# tiene varios componentes y funciona muy estrechamente con algunos componentes del QDK, como los simuladores, que se basan en C#.</span><span class="sxs-lookup"><span data-stu-id="bbafd-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="bbafd-232">El compilador de preguntas # funciona aquí mediante la generación de un espacio de nombres de C# denominado de forma equivalente a partir del espacio de nombres de Q # en nuestro archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="bbafd-233">Además, genera una clase de C# con el nombre equivalente para cada uno de los tipos de Q # Callable o los tipos definidos en ella.</span><span class="sxs-lookup"><span data-stu-id="bbafd-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="bbafd-234">En primer lugar, las clases usadas en nuestro programa host estarán disponibles con `using` instrucciones, que son aproximadamente análogo a las `open` instrucciones del archivo de preguntas #:</span><span class="sxs-lookup"><span data-stu-id="bbafd-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="bbafd-235">A continuación, se declara el espacio de nombres de C#, algunos otros bits y partes (vea el bloque de código completo a continuación) y, después, cualquier programación clásica que nos gustaría (por ejemplo, calculando argumentos para las llamadas a Q #).</span><span class="sxs-lookup"><span data-stu-id="bbafd-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="bbafd-236">Este último no es necesario en nuestro caso, pero se puede encontrar un ejemplo de este uso en el [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="bbafd-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="bbafd-237">Máquinas de destino</span><span class="sxs-lookup"><span data-stu-id="bbafd-237">Target machines</span></span>

<span data-ttu-id="bbafd-238">Al volver a Q #, se debe crear una instancia del equipo de destino en el que se ejecutarán nuestras operaciones.</span><span class="sxs-lookup"><span data-stu-id="bbafd-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="bbafd-239">El uso de otras máquinas de destino es tan sencillo como crear una instancia de una diferente, aunque la manera de hacerlo y el procesamiento de las devoluciones puede ser ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="bbafd-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="bbafd-240">Por motivos de brevedad, nos centramos [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ahora en y incluimos lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [siguiente](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="bbafd-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="bbafd-241">Cada clase de C# generada a partir de las operaciones de Q # tiene un `Run` método, el primer argumento de que debe ser la instancia del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="bbafd-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="bbafd-242">Por lo tanto, para ejecutar `MeasureSuperposition` en `QuantumSimulator` , usamos `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="bbafd-243">Los resultados devueltos se pueden asignar a las variables en C#:</span><span class="sxs-lookup"><span data-stu-id="bbafd-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="bbafd-244">El `Run` método se ejecuta de forma asincrónica porque es el caso del hardware Quantum real y, por lo tanto, la `await` palabra clave bloquea la ejecución hasta que se completa la tarea.</span><span class="sxs-lookup"><span data-stu-id="bbafd-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="bbafd-245">Si Q # Callable no tiene ningún resultado (es decir, tiene el tipo de valor devuelto `Unit` ), la ejecución todavía se puede realizar de la misma manera sin asignarla a una variable.</span><span class="sxs-lookup"><span data-stu-id="bbafd-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="bbafd-246">En ese caso, la línea completa simplemente consistiría en</span><span class="sxs-lookup"><span data-stu-id="bbafd-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="bbafd-247">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bbafd-247">Arguments</span></span>

<span data-ttu-id="bbafd-248">Los argumentos de la t # Callable simplemente se pasan como argumentos adicionales tras el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="bbafd-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="bbafd-249">Por lo tanto, los resultados de `MeasureSuperpositionArray` en `n=4` qubits se capturaban mediante</span><span class="sxs-lookup"><span data-stu-id="bbafd-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="bbafd-250">Por tanto, un programa host de C# completo podría ser similar a</span><span class="sxs-lookup"><span data-stu-id="bbafd-250">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="bbafd-251">En la ubicación del archivo de C#, el programa host se puede ejecutar desde la línea de comandos escribiendo</span><span class="sxs-lookup"><span data-stu-id="bbafd-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="bbafd-252">y en este caso, verá que la salida se escribe en la consola de forma similar a</span><span class="sxs-lookup"><span data-stu-id="bbafd-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="bbafd-253">Debido a la interoperabilidad del compilador con los espacios de nombres, podríamos hacer que nuestras llamadas de Q # estén disponibles sin la `using NamespaceName;` instrucción y simplemente buscar en ella el título del espacio de nombres de C#.</span><span class="sxs-lookup"><span data-stu-id="bbafd-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="bbafd-254">Es decir, reemplazando `namespace host` por `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="bbafd-255">Inclusión del estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="bbafd-255">Including the resources estimator</span></span>

<span data-ttu-id="bbafd-256">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requiere una implementación ligeramente diferente para recuperar la salida.</span><span class="sxs-lookup"><span data-stu-id="bbafd-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="bbafd-257">En primer lugar, en lugar de crear instancias de ellas como una variable con una `using` instrucción (como hacemos con `QuantumSimulator` ), se crean instancias de los objetos de la clase directamente a través de</span><span class="sxs-lookup"><span data-stu-id="bbafd-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="bbafd-258">Tenga en cuenta que, en lugar de un único simulador de destino que se va a usar en varias operaciones de Q #, hemos creado una instancia de para cada uno.</span><span class="sxs-lookup"><span data-stu-id="bbafd-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="bbafd-259">Esto se debe a que los propios objetos se modifican cuando se usan como equipos de destino, y los resultados se pueden recuperar posteriormente con el método de clase `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="bbafd-260">Para ejecutar las operaciones en los estimadores de recursos, usamos</span><span class="sxs-lookup"><span data-stu-id="bbafd-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="bbafd-261">y, a continuación, recupere los resultados como valores separados por tabulaciones (TSV) con `estimatorSingleQ.ToTSV()` y `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="bbafd-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="bbafd-262">Por lo tanto, un programa host de C# completo que usa `QuantumSimulator` y `ResourcesEstimator` puede tener la forma:</span><span class="sxs-lookup"><span data-stu-id="bbafd-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="bbafd-263">lo que produciría una salida similar a</span><span class="sxs-lookup"><span data-stu-id="bbafd-263">which would yield output similar to</span></span>

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

## <a name="q-jupyter-notebooks"></a><span data-ttu-id="bbafd-264">Cuadernos de Jupyter Notebook de Q#</span><span class="sxs-lookup"><span data-stu-id="bbafd-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="bbafd-265">Los cuadernos de Jupyter Notebook usan el kernel de IQ #, que permite definir, compilar y ejecutar Q # Callable en un solo cuaderno---todo junto a instrucciones, notas y otro contenido.</span><span class="sxs-lookup"><span data-stu-id="bbafd-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="bbafd-266">Esto significa que, aunque es posible importar y usar el contenido de `*.qs` los archivos de Q #, no son necesarios en el modelo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bbafd-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="bbafd-267">Aquí veremos cómo ejecutar las operaciones de Q # definidas anteriormente, pero se proporciona una introducción más amplia al uso de cuadernos de Jupyter Notebook en la [Introducción a los cuadernos de preguntas y respuestas de Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="bbafd-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="bbafd-268">Definir operaciones</span><span class="sxs-lookup"><span data-stu-id="bbafd-268">Defining operations</span></span>

<span data-ttu-id="bbafd-269">En un Jupyter Notebook de preguntas y respuestas, se escribe el código de Q # como se haría desde dentro del espacio de nombres de un archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="bbafd-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="bbafd-270">Por lo tanto, podemos habilitar el acceso a las llamadas desde las [bibliotecas de preguntas # estándar](xref:microsoft.quantum.qsharplibintro) con `open` instrucciones para sus respectivos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="bbafd-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="bbafd-271">Al ejecutar una celda con esta instrucción, las definiciones de esos espacios de nombres están disponibles en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bbafd-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="bbafd-272">Las llamadas de [Microsoft. Quantum. Intrinsic](xref:microsoft.quantum.intrinsic) y [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (por ejemplo, [`H`](xref:microsoft.quantum.intrinsic.h) y [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) están disponibles automáticamente para las operaciones definidas dentro de las celdas de los cuadernos de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="bbafd-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="bbafd-273">Sin embargo, esto no es cierto para el código traído de archivos de código fuente de Q # externos (un proceso que se muestra en la [Introducción a los cuadernos de preguntas y respuestas de Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="bbafd-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="bbafd-274">Del mismo modo, la definición de operaciones solo requiere escribir el código Q # y ejecutar la celda.</span><span class="sxs-lookup"><span data-stu-id="bbafd-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="bbafd-275">A continuación, la salida muestra las operaciones, a las que se puede llamar desde las celdas futuras.</span><span class="sxs-lookup"><span data-stu-id="bbafd-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="bbafd-276">Máquinas de destino</span><span class="sxs-lookup"><span data-stu-id="bbafd-276">Target machines</span></span>

<span data-ttu-id="bbafd-277">La funcionalidad para ejecutar operaciones en equipos de destino específicos se proporciona a través de [comandos de IQ # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="bbafd-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="bbafd-278">Por ejemplo, `%simulate` hace uso de `QuantumSimulator` y `%estimate` usa `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="bbafd-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="bbafd-279">Pasar entradas a funciones y operaciones</span><span class="sxs-lookup"><span data-stu-id="bbafd-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="bbafd-280">Actualmente, los comandos mágicos de ejecución solo se pueden usar con operaciones que no toman ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="bbafd-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="bbafd-281">Por lo tanto, para ejecutar `MeasureSuperpositionArray` , es necesario definir una operación de "contenedor" que, a continuación, llame a la operación con los argumentos:</span><span class="sxs-lookup"><span data-stu-id="bbafd-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="bbafd-282">Esta operación puede usarse de forma similar con `%estimate` y otros comandos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bbafd-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
