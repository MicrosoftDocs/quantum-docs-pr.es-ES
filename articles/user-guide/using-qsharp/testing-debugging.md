---
title: Prueba y depuración
description: Aprenda a usar pruebas unitarias, hechos y aserciones y funciones de volcado para probar y depurar programas Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833167"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="19cbd-103">Prueba y depuración</span><span class="sxs-lookup"><span data-stu-id="19cbd-103">Testing and debugging</span></span>

<span data-ttu-id="19cbd-104">Al igual que con la programación clásica, es esencial poder comprobar que los programas Quantum funcionan según lo previsto y para poder diagnosticar un comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="19cbd-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="19cbd-105">En esta sección, trataremos las herramientas que ofrece Q# para probar y depurar programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="19cbd-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="19cbd-106">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="19cbd-106">Unit Tests</span></span>

<span data-ttu-id="19cbd-107">Un enfoque común para probar programas clásico es escribir programas pequeños denominados *pruebas unitarias*, que ejecutan código en una biblioteca y comparan su salida con alguna salida esperada.</span><span class="sxs-lookup"><span data-stu-id="19cbd-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="19cbd-108">Por ejemplo, puede asegurarse de que `Square(2)` devuelve `4` desde que conoce *un priori* que es $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="19cbd-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="19cbd-109">Q# admite la creación de pruebas unitarias para programas Quantum y que se pueden ejecutar como pruebas en el marco de pruebas unitarias de [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="19cbd-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="19cbd-110">Crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="19cbd-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="19cbd-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="19cbd-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="19cbd-112">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="19cbd-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="19cbd-113">Vaya al menú **archivo** y seleccione **nuevo > proyecto..**.. En la esquina superior derecha, busque `Q#` y seleccione la plantilla \*\* Q# proyecto de prueba\*\* .</span><span class="sxs-lookup"><span data-stu-id="19cbd-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="19cbd-114">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="19cbd-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="19cbd-115">Desde la línea de comandos favorita, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="19cbd-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="19cbd-116">El nuevo proyecto tiene un único archivo `Tests.qs` , lo que proporciona un lugar cómodo para definir nuevas Q# pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="19cbd-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="19cbd-117">Inicialmente, este archivo contiene una prueba unitaria `AllocateQubit` de ejemplo que comprueba que una qubit recién asignada se encuentra en el estado $ \ket {0} $ e imprime un mensaje:</span><span class="sxs-lookup"><span data-stu-id="19cbd-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="19cbd-118">Cualquier Q# operación o función que toma un argumento de tipo `Unit` y devuelve `Unit` se puede marcar como una prueba unitaria mediante el `@Test("...")` atributo.</span><span class="sxs-lookup"><span data-stu-id="19cbd-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="19cbd-119">En el ejemplo anterior, el argumento para ese atributo, `"QuantumSimulator"` , especifica el destino en el que se ejecuta la prueba.</span><span class="sxs-lookup"><span data-stu-id="19cbd-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="19cbd-120">Una sola prueba puede ejecutarse en varios destinos.</span><span class="sxs-lookup"><span data-stu-id="19cbd-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="19cbd-121">Por ejemplo, agregue un atributo `@Test("ResourcesEstimator")` delante de `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="19cbd-122">Guarde el archivo y ejecute todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="19cbd-122">Save the file and run all tests.</span></span> <span data-ttu-id="19cbd-123">Ahora debería haber dos pruebas unitarias, una en `AllocateQubit` la que se ejecuta en `QuantumSimulator` y otra en la que se ejecuta en `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="19cbd-124">El Q# compilador reconoce los destinos integrados `"QuantumSimulator"` , `"ToffoliSimulator"` y `"ResourcesEstimator"` como destinos de ejecución válidos para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="19cbd-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="19cbd-125">También es posible especificar cualquier nombre completo para definir un destino de ejecución personalizado.</span><span class="sxs-lookup"><span data-stu-id="19cbd-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="19cbd-126">Ejecutar Q# pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="19cbd-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="19cbd-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="19cbd-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="19cbd-128">Como programa de instalación única por solución, vaya al menú **prueba** y seleccione **configuración de pruebas > arquitectura de procesador predeterminada > x64**.</span><span class="sxs-lookup"><span data-stu-id="19cbd-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="19cbd-129">La configuración predeterminada de la arquitectura del procesador para Visual Studio se almacena en el archivo de opciones de solución ( `.suo` ) para cada solución.</span><span class="sxs-lookup"><span data-stu-id="19cbd-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="19cbd-130">Si elimina este archivo, deberá seleccionar **x64** como su arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="19cbd-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="19cbd-131">Compile el proyecto, abra el menú **prueba** y seleccione **Windows > explorador de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="19cbd-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="19cbd-132">**AllocateQubit** se muestra en la lista de pruebas en el grupo **pruebas no ejecutadas** .</span><span class="sxs-lookup"><span data-stu-id="19cbd-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="19cbd-133">Seleccione **ejecutar todas** o ejecutar esta prueba individual.</span><span class="sxs-lookup"><span data-stu-id="19cbd-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="19cbd-134">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="19cbd-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="19cbd-135">Para ejecutar las pruebas, navegue hasta la carpeta del proyecto (la carpeta que contiene `Tests.csproj` ) y ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="19cbd-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="19cbd-136">Debería obtener una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="19cbd-136">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="19cbd-137">Las pruebas unitarias se pueden filtrar según su nombre o destino de ejecución:</span><span class="sxs-lookup"><span data-stu-id="19cbd-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="19cbd-138">La función intrínseca <xref:microsoft.quantum.intrinsic.message> tiene el tipo `(String -> Unit)` y permite la creación de mensajes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="19cbd-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="19cbd-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="19cbd-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="19cbd-140">Después de ejecutar una prueba en el explorador de pruebas y hacer clic en la prueba, se muestra un panel con información sobre la serie de pruebas: estado de superación/error, tiempo transcurrido y un vínculo a la salida.</span><span class="sxs-lookup"><span data-stu-id="19cbd-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="19cbd-141">Haga clic en **salida** para abrir la salida de la prueba en una nueva ventana.</span><span class="sxs-lookup"><span data-stu-id="19cbd-141">Click **Output** to open the test output in a new window.</span></span>

![resultados de la prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="19cbd-143">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="19cbd-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="19cbd-144">El estado de superación o error de cada prueba se imprime en la consola mediante `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="19cbd-145">En el caso de las pruebas con errores, las salidas también se imprimen en la consola para ayudar a diagnosticar el error.</span><span class="sxs-lookup"><span data-stu-id="19cbd-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="19cbd-146">Hechos y aserciones</span><span class="sxs-lookup"><span data-stu-id="19cbd-146">Facts and Assertions</span></span>

<span data-ttu-id="19cbd-147">Dado que las funciones de Q# no tienen efectos secundarios _lógicos_ , nunca puede observar, desde dentro de un Q# programa, cualquier otro tipo de efecto de ejecutar una función cuyo tipo de salida sea la tupla vacía `()` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="19cbd-148">Es decir, una máquina de destino puede elegir no ejecutar ninguna función que devuelva `()` con la garantía de que esta omisión no modificará el comportamiento de ningún Q# código siguiente.</span><span class="sxs-lookup"><span data-stu-id="19cbd-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="19cbd-149">Este comportamiento hace que las funciones devuelvan `()` (como `Unit` ) una herramienta útil para insertar aserciones y lógica de depuración en Q# programas.</span><span class="sxs-lookup"><span data-stu-id="19cbd-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="19cbd-150">Veamos un ejemplo sencillo:</span><span class="sxs-lookup"><span data-stu-id="19cbd-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="19cbd-151">Aquí, la palabra clave `fail` indica que el cálculo no debe continuar y genera una excepción en el equipo de destino que ejecuta el Q# programa.</span><span class="sxs-lookup"><span data-stu-id="19cbd-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="19cbd-152">Por definición, un error de este tipo no se puede observar desde dentro Q# , ya que el equipo de destino ya no ejecuta el Q# código después de alcanzar una `fail` instrucción.</span><span class="sxs-lookup"><span data-stu-id="19cbd-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="19cbd-153">Por lo tanto, si continuamos después de una llamada a `PositivityFact` , podemos estar seguros de que su entrada fue positiva.</span><span class="sxs-lookup"><span data-stu-id="19cbd-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="19cbd-154">Tenga en cuenta que se puede implementar el mismo comportamiento que `PositivityFact` el uso [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la función del <xref:microsoft.quantum.diagnostics> espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="19cbd-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="19cbd-155">Por otro lado, las *aserciones*se usan de forma similar a los hechos, pero pueden depender del estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="19cbd-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="19cbd-156">En consecuencia, se definen como operaciones, mientras que los hechos se definen como funciones (como en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="19cbd-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="19cbd-157">Para entender la distinción, considere el siguiente uso de un hecho dentro de una aserción:</span><span class="sxs-lookup"><span data-stu-id="19cbd-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="19cbd-158">Aquí se usa la operación <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver el número de qubits disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="19cbd-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="19cbd-159">Dado que esto depende del estado global del programa y su entorno de ejecución, nuestra definición de `AssertQubitsAreAvailable` también debe ser una operación.</span><span class="sxs-lookup"><span data-stu-id="19cbd-159">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="19cbd-160">Sin embargo, podemos usar ese estado global para producir un `Bool` valor simple como entrada para la `Fact` función.</span><span class="sxs-lookup"><span data-stu-id="19cbd-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="19cbd-161">[El](xref:microsoft.quantum.libraries.standard.prelude)preparativo, que se basa en estas ideas, ofrece dos aserciones especialmente útiles <xref:microsoft.quantum.diagnostics.assertmeasurement> y <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> ambas se modelan como operaciones en `()` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="19cbd-162">Cada una de estas aserciones toma un operador Pauli que describe una medida determinada de interés, un registro Quantum en el que se realiza una medida y un resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="19cbd-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="19cbd-163">Los equipos de destino que funcionan por simulación no están limitados por [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem)y pueden realizar tales mediciones sin alterar el registro que pasa a dichas aserciones.</span><span class="sxs-lookup"><span data-stu-id="19cbd-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="19cbd-164">Un simulador puede, de forma similar a la `PositivityFact` función anterior, detener el cálculo si el resultado hipotético no se observa en la práctica:</span><span class="sxs-lookup"><span data-stu-id="19cbd-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="19cbd-165">En el hardware de Quantum físico, donde el teorema sin clonación impide el examen de un estado de Quantum, las `AssertMeasurement` `AssertMeasurementProbability` operaciones y simplemente devuelven `()` sin ningún otro efecto.</span><span class="sxs-lookup"><span data-stu-id="19cbd-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="19cbd-166">El <xref:microsoft.quantum.diagnostics> espacio de nombres proporciona varias funciones más de la `Assert` familia, con las que puede comprobar condiciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="19cbd-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="19cbd-167">Funciones de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="19cbd-167">Dump Functions</span></span>

<span data-ttu-id="19cbd-168">Para ayudar a solucionar problemas de los programas Quantum, el <xref:microsoft.quantum.diagnostics> espacio de nombres ofrece dos funciones que pueden volcar en un archivo el estado actual del equipo de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> y <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="19cbd-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="19cbd-169">La salida generada de cada depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="19cbd-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="19cbd-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="19cbd-170">DumpMachine</span></span>

<span data-ttu-id="19cbd-171">El simulador de Quantum de estado completo distribuido como parte del kit de desarrollo de Quantum escribe en el archivo la [función de onda](https://en.wikipedia.org/wiki/Wave_function) del sistema Quantum completo, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud de la probabilidad de medir el estado de base de cálculo $ \ket{n} $, donde $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ para bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="19cbd-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="19cbd-172">Por ejemplo, en un equipo con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ al llamar a <xref:microsoft.quantum.diagnostics.dumpmachine> se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="19cbd-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="19cbd-173">La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.</span><span class="sxs-lookup"><span data-stu-id="19cbd-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="19cbd-174">El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{n} $ en formatos cartesianos y polares.</span><span class="sxs-lookup"><span data-stu-id="19cbd-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="19cbd-175">En detalle para la primera fila:</span><span class="sxs-lookup"><span data-stu-id="19cbd-175">In detail for the first row:</span></span>

* <span data-ttu-id="19cbd-176">**`∣0❭:`** esta fila corresponde al `0` Estado de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="19cbd-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="19cbd-177">**`0.707107 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="19cbd-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="19cbd-178">**` == `**: el `equal` signo separa ambas representaciones equivalentes.</span><span class="sxs-lookup"><span data-stu-id="19cbd-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="19cbd-179">**`**********  `**: Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.</span><span class="sxs-lookup"><span data-stu-id="19cbd-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="19cbd-180">**`[ 0.500000 ]`**: el valor numérico de la magnitud</span><span class="sxs-lookup"><span data-stu-id="19cbd-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="19cbd-181">**`    ---`**: Una representación gráfica de la fase de amplitud (vea la salida siguiente).</span><span class="sxs-lookup"><span data-stu-id="19cbd-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="19cbd-182">**`[ 0.0000 rad ]`**: valor numérico de la fase (en radianes).</span><span class="sxs-lookup"><span data-stu-id="19cbd-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="19cbd-183">Tanto la magnitud como la fase se muestran con una representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="19cbd-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="19cbd-184">La representación de la magnitud es directa: muestra una barra de `*` ; cuanto mayor es la probabilidad, mayor será la barra.</span><span class="sxs-lookup"><span data-stu-id="19cbd-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="19cbd-185">En la fase, se muestran los siguientes símbolos para representar el ángulo en función de los intervalos:</span><span class="sxs-lookup"><span data-stu-id="19cbd-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="19cbd-186">Los ejemplos siguientes muestran `DumpMachine` para algunos Estados comunes:</span><span class="sxs-lookup"><span data-stu-id="19cbd-186">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="19cbd-187">El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó qubit o su posición dentro de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="19cbd-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="19cbd-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="19cbd-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="19cbd-189">Para buscar un identificador de qubit en Visual Studio, coloque un punto de interrupción en el código e inspeccione el valor de una variable qubit, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19cbd-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostrar el identificador de qubit en Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="19cbd-191">el qubit con el índice `0` de `register2` tiene el identificador = `3` , el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="19cbd-192">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="19cbd-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="19cbd-193">Puede buscar un identificador de qubit mediante la <xref:microsoft.quantum.intrinsic.message> función y pasar la variable qubit en el mensaje, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19cbd-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="19cbd-194">Esto podría generar esta salida:</span><span class="sxs-lookup"><span data-stu-id="19cbd-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="19cbd-195">lo que significa que el qubit con el índice `0` de `register2` tiene `3` el identificador =, el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="19cbd-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="19cbd-196">Dado que <xref:microsoft.quantum.diagnostics.dumpmachine> forma parte del  <xref:microsoft.quantum.diagnostics> espacio de nombres, debe agregar una `open` instrucción para tener acceso a ella:</span><span class="sxs-lookup"><span data-stu-id="19cbd-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="19cbd-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="19cbd-197">DumpRegister</span></span>

<span data-ttu-id="19cbd-198"><xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine> , salvo que también toma una matriz de qubits para limitar la cantidad de información a solo el correspondiente qubits.</span><span class="sxs-lookup"><span data-stu-id="19cbd-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="19cbd-199">Como con <xref:microsoft.quantum.diagnostics.dumpmachine> , la información generada por <xref:microsoft.quantum.diagnostics.dumpregister> depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="19cbd-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="19cbd-200">Para el simulador de Quantum de estado completo, escribe en el archivo la función Wave hasta una fase global del subsistema Quantum generada por el qubits proporcionado en el mismo formato que <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="19cbd-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="19cbd-201">Por ejemplo, vuelva a realizar una máquina con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ) la llamada de \end{align} $ $ que llama <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[0]` genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="19cbd-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="19cbd-202">y al llamar a <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="19cbd-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="19cbd-203">En general, el estado de un registro que está inenredado con otro registro es un estado mixto en lugar de un estado puro.</span><span class="sxs-lookup"><span data-stu-id="19cbd-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="19cbd-204">En este caso, <xref:microsoft.quantum.diagnostics.dumpregister> genera el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="19cbd-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="19cbd-205">En el ejemplo siguiente se muestra cómo puede usar <xref:microsoft.quantum.diagnostics.dumpregister> y <xref:microsoft.quantum.diagnostics.dumpmachine> en el Q# código:</span><span class="sxs-lookup"><span data-stu-id="19cbd-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="19cbd-206">Depuración</span><span class="sxs-lookup"><span data-stu-id="19cbd-206">Debugging</span></span>

<span data-ttu-id="19cbd-207">Sobre `Assert` `Dump` las funciones y y las operaciones, Q# admite un subconjunto de capacidades de depuración estándar de Visual Studio: [establecer puntos de interrupción de línea](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [recorrer paso a paso el código mediante F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)y [inspeccionar los valores de las variables clásicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) es posible al ejecutar el código en el simulador.</span><span class="sxs-lookup"><span data-stu-id="19cbd-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="19cbd-208">La depuración en Visual Studio Code aprovecha las capacidades de depuración proporcionadas por C# para la extensión de Visual Studio Code con tecnología de OmniSharp y requiere la instalación de la [versión más reciente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="19cbd-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
