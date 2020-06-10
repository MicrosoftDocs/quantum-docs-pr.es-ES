---
title: Prueba y depuración
description: Aprenda a usar pruebas unitarias, hechos y aserciones y funciones de volcado para probar y depurar programas Quantum.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630030"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="64ecb-103">Prueba y depuración</span><span class="sxs-lookup"><span data-stu-id="64ecb-103">Testing and debugging</span></span>

<span data-ttu-id="64ecb-104">Al igual que con la programación clásica, es esencial poder comprobar que los programas Quantum funcionan según lo previsto y para poder diagnosticar un programa Quantum que no sea correcto.</span><span class="sxs-lookup"><span data-stu-id="64ecb-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="64ecb-105">En esta sección, trataremos las herramientas que ofrece Q # para probar y depurar programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="64ecb-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="64ecb-106">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="64ecb-106">Unit Tests</span></span>

<span data-ttu-id="64ecb-107">Un método común para probar programas clásico es escribir programas pequeños denominados *pruebas unitarias* que ejecutan código en una biblioteca y comparan su salida con alguna salida esperada.</span><span class="sxs-lookup"><span data-stu-id="64ecb-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="64ecb-108">Por ejemplo, es posible que desee asegurarse de que `Square(2)` devuelve `4` , ya que sabemos *un priori* que es $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="64ecb-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="64ecb-109">Q # admite la creación de pruebas unitarias para programas Quantum y que se pueden ejecutar como pruebas en el marco de pruebas unitarias de [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="64ecb-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="64ecb-110">Crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="64ecb-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="64ecb-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="64ecb-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="64ecb-112">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="64ecb-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="64ecb-113">Vaya al `File` menú y seleccione `New`  >  `Project...` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="64ecb-114">En la esquina superior derecha, busque `Q#` y seleccione la `Q# Test Project` plantilla.</span><span class="sxs-lookup"><span data-stu-id="64ecb-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="64ecb-115">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ecb-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="64ecb-116">Desde la línea de comandos favorita, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="64ecb-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="64ecb-117">El nuevo proyecto tendrá un solo archivo `Tests.qs` , lo que proporciona un lugar cómodo para definir nuevas pruebas unitarias de Q #.</span><span class="sxs-lookup"><span data-stu-id="64ecb-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="64ecb-118">Inicialmente, este archivo contiene una prueba unitaria `AllocateQubit` de ejemplo que comprueba que una qubit recién asignada se encuentra en el estado $ \ket {0} $ e imprime un mensaje:</span><span class="sxs-lookup"><span data-stu-id="64ecb-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="64ecb-119">: New: cualquier operación Q # o función que toma un argumento de tipo `Unit` y devuelve `Unit` se puede marcar como una prueba unitaria mediante el `@Test("...")` atributo.</span><span class="sxs-lookup"><span data-stu-id="64ecb-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="64ecb-120">El argumento para ese atributo, `"QuantumSimulator"` arriba, especifica el destino en el que se ejecuta la prueba.</span><span class="sxs-lookup"><span data-stu-id="64ecb-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="64ecb-121">Una sola prueba se puede ejecutar en varios destinos.</span><span class="sxs-lookup"><span data-stu-id="64ecb-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="64ecb-122">Por ejemplo, agregue un atributo `@Test("ResourcesEstimator")` arriba `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="64ecb-123">Guarde el archivo y ejecute todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="64ecb-123">Save the file and execute all tests.</span></span> <span data-ttu-id="64ecb-124">Ahora debería haber dos pruebas unitarias, una en la que AllocateQubit se ejecuta en QuantumSimulator y otra en la que se ejecuta en ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="64ecb-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="64ecb-125">El compilador de Q # reconoce los destinos integrados "QuantumSimulator", "ToffoliSimulator" y "ResourcesEstimator" como destinos de ejecución válidos para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="64ecb-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="64ecb-126">También es posible especificar cualquier nombre completo para definir un destino de ejecución personalizado.</span><span class="sxs-lookup"><span data-stu-id="64ecb-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="64ecb-127">Ejecutar pruebas unitarias de Q #</span><span class="sxs-lookup"><span data-stu-id="64ecb-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="64ecb-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="64ecb-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="64ecb-129">Como configuración de una sola solución, vaya a `Test` menú y seleccione `Test Settings`  >  `Default Processor Architecture`  >  `X64` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="64ecb-130">La configuración predeterminada de la arquitectura del procesador para Visual Studio se almacena en el archivo de opciones de solución ( `.suo` ) para cada solución.</span><span class="sxs-lookup"><span data-stu-id="64ecb-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="64ecb-131">Si elimina este archivo, tendrá que volver a seleccionarlo `X64` como su arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="64ecb-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="64ecb-132">Compile el proyecto, vaya al `Test` menú y seleccione `Windows`  >  `Test Explorer` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="64ecb-133">`AllocateQubit`aparecerá en la lista de pruebas del `Not Run Tests` grupo.</span><span class="sxs-lookup"><span data-stu-id="64ecb-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="64ecb-134">Seleccione `Run All` o ejecute esta prueba individual y debe pasarse.</span><span class="sxs-lookup"><span data-stu-id="64ecb-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="64ecb-135">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ecb-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="64ecb-136">Para ejecutar las pruebas, navegue hasta la carpeta del proyecto (la carpeta que contiene `Tests.csproj` ) y ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="64ecb-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="64ecb-137">Debería obtener una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="64ecb-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="64ecb-138">Las pruebas unitarias se pueden filtrar según su nombre o destino de ejecución:</span><span class="sxs-lookup"><span data-stu-id="64ecb-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="64ecb-139">La función intrínseca <xref:microsoft.quantum.intrinsic.message> tiene el tipo `(String -> Unit)` y permite la creación de mensajes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="64ecb-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="64ecb-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="64ecb-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="64ecb-141">Después de ejecutar una prueba en el explorador de pruebas y hacer clic en la prueba, aparecerá un panel con información sobre la ejecución de pruebas: estado superado/error, tiempo transcurrido y un vínculo de "salida".</span><span class="sxs-lookup"><span data-stu-id="64ecb-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="64ecb-142">Si hace clic en el vínculo "salida", la salida de la prueba se abrirá en una nueva ventana.</span><span class="sxs-lookup"><span data-stu-id="64ecb-142">If you click the "Output" link, test output will open in a new window.</span></span>

![resultados de la prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="64ecb-144">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ecb-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="64ecb-145">El estado de superación o error de cada prueba se imprime en la consola mediante `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="64ecb-146">En el caso de las pruebas con errores, las salidas también se imprimen en la consola para ayudar a diagnosticar el error.</span><span class="sxs-lookup"><span data-stu-id="64ecb-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="64ecb-147">Hechos y aserciones</span><span class="sxs-lookup"><span data-stu-id="64ecb-147">Facts and Assertions</span></span>

<span data-ttu-id="64ecb-148">Dado que las funciones de Q # no tienen efectos secundarios _lógicos_ , cualquier _otro_ tipo de efectos de la ejecución de una función cuyo tipo de salida es la tupla vacía `()` nunca se puede observar desde un programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="64ecb-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="64ecb-149">Es decir, una máquina de destino puede optar por no ejecutar ninguna función que devuelva `()` con la garantía de que esta omisión no modificará el comportamiento de ningún código de Q # siguiente.</span><span class="sxs-lookup"><span data-stu-id="64ecb-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="64ecb-150">Esto hace que las funciones devuelvan `()` (es decir, `Unit` ) una herramienta útil para insertar aserciones y lógica de depuración en programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="64ecb-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="64ecb-151">Veamos un ejemplo sencillo:</span><span class="sxs-lookup"><span data-stu-id="64ecb-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="64ecb-152">Aquí, la palabra clave `fail` indica que el cálculo no debe continuar, generando una excepción en el equipo de destino que ejecuta el programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="64ecb-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="64ecb-153">Por definición, un error de este tipo no se puede observar desde Q #, ya que no se ejecuta más código de Q # después de `fail` alcanzar una instrucción.</span><span class="sxs-lookup"><span data-stu-id="64ecb-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="64ecb-154">Por lo tanto, si continuamos después de una llamada a `PositivityFact` , podemos estar seguros de que su entrada fue positiva.</span><span class="sxs-lookup"><span data-stu-id="64ecb-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="64ecb-155">Tenga en cuenta que se puede implementar el mismo comportamiento que `PositivityFact` el uso [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la función del <xref:microsoft.quantum.diagnostics> espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="64ecb-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="64ecb-156">Por otro lado, las *aserciones*se usan de forma similar a los hechos, pero pueden depender del estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="64ecb-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="64ecb-157">En consecuencia, se definen como operaciones, mientras que los hechos se definen como funciones (como arriba).</span><span class="sxs-lookup"><span data-stu-id="64ecb-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="64ecb-158">Para entender la distinción, considere el siguiente uso de un hecho dentro de una aserción:</span><span class="sxs-lookup"><span data-stu-id="64ecb-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="64ecb-159">Aquí se usa la operación <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver el número de qubits disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="64ecb-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="64ecb-160">Dado que esto depende claramente del estado global del programa y su entorno de ejecución, nuestra definición de `AssertQubitsAreAvailable` también debe ser una operación.</span><span class="sxs-lookup"><span data-stu-id="64ecb-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="64ecb-161">Sin embargo, podemos usar ese estado global para producir un `Bool` valor simple como entrada para la `Fact` función.</span><span class="sxs-lookup"><span data-stu-id="64ecb-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="64ecb-162">Basándose en estas ideas, [el predicho](xref:microsoft.quantum.libraries.standard.prelude) ofrece dos aserciones especialmente útiles <xref:microsoft.quantum.intrinsic.assert> y ambas se <xref:microsoft.quantum.intrinsic.assertprob> modelan como operaciones en `()` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="64ecb-163">Cada una de estas aserciones toma un operador Pauli que describe una medida determinada de interés, un registro Quantum en el que se va a realizar una medida y un resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="64ecb-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="64ecb-164">En las máquinas de destino que funcionan por simulación, no están limitadas por [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem)y pueden realizar tales mediciones sin alterar el registro que se pasa a dichas aserciones.</span><span class="sxs-lookup"><span data-stu-id="64ecb-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="64ecb-165">Un simulador puede, de forma similar a la `PositivityFact` función anterior, anular el cálculo si el resultado hipotético no se observa en la práctica:</span><span class="sxs-lookup"><span data-stu-id="64ecb-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="64ecb-166">En el hardware de Quantum físico, donde el teorema sin clonación impide el examen del estado de Quantum, las `Assert` `AssertProb` operaciones y simplemente devuelven `()` sin ningún otro efecto.</span><span class="sxs-lookup"><span data-stu-id="64ecb-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="64ecb-167">El <xref:microsoft.quantum.diagnostics> espacio de nombres proporciona varias funciones más de la `Assert` familia que nos permiten comprobar condiciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="64ecb-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="64ecb-168">Funciones de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="64ecb-168">Dump Functions</span></span>

<span data-ttu-id="64ecb-169">Para ayudar a solucionar problemas de los programas Quantum, el <xref:microsoft.quantum.diagnostics> espacio de nombres ofrece dos funciones que pueden volcar en un archivo el estado actual del equipo de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> y <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="64ecb-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="64ecb-170">La salida generada de cada depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="64ecb-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="64ecb-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="64ecb-171">DumpMachine</span></span>

<span data-ttu-id="64ecb-172">El simulador de Quantum de estado completo distribuido como parte del kit de desarrollo de Quantum escribe en el archivo la [función de onda](https://en.wikipedia.org/wiki/Wave_function) del sistema Quantum completo, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud de la probabilidad de medir el estado de base de cálculo $ \ket{n} $, donde $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ para bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="64ecb-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="64ecb-173">Por ejemplo, en un equipo con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ al llamar a <xref:microsoft.quantum.diagnostics.dumpmachine> se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="64ecb-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="64ecb-174">La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.</span><span class="sxs-lookup"><span data-stu-id="64ecb-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="64ecb-175">El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{n} $ en formatos cartesianos y polares.</span><span class="sxs-lookup"><span data-stu-id="64ecb-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="64ecb-176">En detalle para la primera fila:</span><span class="sxs-lookup"><span data-stu-id="64ecb-176">In detail for the first row:</span></span>

* <span data-ttu-id="64ecb-177">**`∣0❭:`** esta fila corresponde al `0` Estado de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="64ecb-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="64ecb-178">**`0.707107 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="64ecb-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="64ecb-179">**` == `**: el `equal` signo separa ambas representaciones equivalentes.</span><span class="sxs-lookup"><span data-stu-id="64ecb-179">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="64ecb-180">**`**********  `**: Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.</span><span class="sxs-lookup"><span data-stu-id="64ecb-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="64ecb-181">**`[ 0.500000 ]`**: el valor numérico de la magnitud</span><span class="sxs-lookup"><span data-stu-id="64ecb-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="64ecb-182">**`    ---`**: Representación gráfica de la fase de amplitud (vea más abajo).</span><span class="sxs-lookup"><span data-stu-id="64ecb-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="64ecb-183">**`[ 0.0000 rad ]`**: valor numérico de la fase (en radianes).</span><span class="sxs-lookup"><span data-stu-id="64ecb-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="64ecb-184">Tanto la magnitud como la fase se muestran con una representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="64ecb-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="64ecb-185">La representación de la magnitud es directa: muestra una barra de `*` ; cuanto mayor es la probabilidad, mayor será la barra.</span><span class="sxs-lookup"><span data-stu-id="64ecb-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="64ecb-186">En la fase, se muestran los siguientes símbolos para representar el ángulo en función de los intervalos:</span><span class="sxs-lookup"><span data-stu-id="64ecb-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="64ecb-187">Los ejemplos siguientes muestran `DumpMachine` para algunos Estados comunes:</span><span class="sxs-lookup"><span data-stu-id="64ecb-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="64ecb-188">El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó qubit o su posición dentro de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="64ecb-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="64ecb-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="64ecb-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="64ecb-190">Puede averiguar un identificador de qubit en Visual Studio si coloca un punto de interrupción en el código y inspecciona el valor de una variable de qubit, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64ecb-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostrar el identificador de qubit en Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="64ecb-192">el qubit con el índice `0` de `register2` tiene el identificador = `3` , el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="64ecb-193">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ecb-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="64ecb-194">Puede averiguar un identificador de qubit mediante la <xref:microsoft.quantum.intrinsic.message> función y pasar la variable qubit en el mensaje, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64ecb-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="64ecb-195">Esto podría generar esta salida:</span><span class="sxs-lookup"><span data-stu-id="64ecb-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="64ecb-196">lo que significa que el qubit con el índice `0` de `register2` tiene `3` el identificador =, el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="64ecb-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="64ecb-197"><xref:microsoft.quantum.diagnostics.dumpmachine>forma parte del <xref:microsoft.quantum.diagnostics> espacio de nombres, por lo que, para poder usarlo, debe agregar una `open` instrucción:</span><span class="sxs-lookup"><span data-stu-id="64ecb-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="64ecb-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="64ecb-198">DumpRegister</span></span>

<span data-ttu-id="64ecb-199"><xref:microsoft.quantum.diagnostics.dumpregister>funciona como <xref:microsoft.quantum.diagnostics.dumpmachine> , salvo que también toma una matriz de qubits para limitar la cantidad de información a solo el correspondiente qubits.</span><span class="sxs-lookup"><span data-stu-id="64ecb-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="64ecb-200">Como con <xref:microsoft.quantum.diagnostics.dumpmachine> , la información generada por <xref:microsoft.quantum.diagnostics.dumpregister> depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="64ecb-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="64ecb-201">Para el simulador de Quantum de estado completo, escribe en el archivo la función Wave hasta una fase global del subsistema Quantum generada por el qubits proporcionado en el mismo formato que <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="64ecb-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="64ecb-202">Por ejemplo, vuelva a realizar una máquina con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ) la llamada de \end{align} $ $ que llama <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[0]` genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="64ecb-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="64ecb-203">y al llamar a <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="64ecb-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="64ecb-204">En general, el estado de un registro que está inenredado con otro registro es un estado mixto en lugar de un estado puro.</span><span class="sxs-lookup"><span data-stu-id="64ecb-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="64ecb-205">En este caso, <xref:microsoft.quantum.diagnostics.dumpregister> genera el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="64ecb-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="64ecb-206">En el ejemplo siguiente se muestra cómo puede usar tanto <xref:microsoft.quantum.diagnostics.dumpregister> como <xref:microsoft.quantum.diagnostics.dumpmachine> en el código de Q #:</span><span class="sxs-lookup"><span data-stu-id="64ecb-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="64ecb-207">Depuración</span><span class="sxs-lookup"><span data-stu-id="64ecb-207">Debugging</span></span>

<span data-ttu-id="64ecb-208">Sobre `Assert` `Dump` las funciones y y las operaciones, Q # admite un subconjunto de las funcionalidades de depuración estándar de Visual Studio: [establecer puntos de interrupción de línea](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [ejecutar paso a paso el código con F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspeccionar los valores de las variables clásicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) es posible durante la ejecución del código en el simulador.</span><span class="sxs-lookup"><span data-stu-id="64ecb-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="64ecb-209">La depuración en Visual Studio Code aprovecha las capacidades de depuración proporcionadas por C# para la extensión de Visual Studio Code con tecnología de OmniSharp y requiere la instalación de la [versión más reciente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="64ecb-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
