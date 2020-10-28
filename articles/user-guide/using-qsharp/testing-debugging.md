---
title: Prueba y depuración
description: Aprenda a usar pruebas unitarias, hechos y aserciones y funciones de volcado para probar y depurar programas Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690971"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="af817-103">Prueba y depuración</span><span class="sxs-lookup"><span data-stu-id="af817-103">Testing and debugging</span></span>

<span data-ttu-id="af817-104">Al igual que con la programación clásica, es esencial poder comprobar que los programas Quantum funcionan según lo previsto y para poder diagnosticar un comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="af817-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="af817-105">En esta sección, trataremos las herramientas que ofrece :::no-loc(Q#)::: para probar y depurar programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="af817-105">In this section, we cover the tools offered by :::no-loc(Q#)::: for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="af817-106">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="af817-106">Unit Tests</span></span>

<span data-ttu-id="af817-107">Un enfoque común para probar programas clásico es escribir programas pequeños denominados *pruebas unitarias* , que ejecutan código en una biblioteca y comparan su salida con alguna salida esperada.</span><span class="sxs-lookup"><span data-stu-id="af817-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="af817-108">Por ejemplo, puede asegurarse de que `Square(2)` devuelve `4` desde que conoce *un priori* que es $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="af817-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="af817-109">:::no-loc(Q#)::: admite la creación de pruebas unitarias para programas Quantum y que se pueden ejecutar como pruebas en el marco de pruebas unitarias de [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="af817-109">:::no-loc(Q#)::: supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="af817-110">Crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="af817-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="af817-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="af817-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="af817-112">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="af817-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="af817-113">Vaya al menú **archivo** y seleccione **nuevo > proyecto..** .. En la esquina superior derecha, busque `:::no-loc(Q#):::` y seleccione la plantilla **:::no-loc(Q#)::: proyecto de prueba** .</span><span class="sxs-lookup"><span data-stu-id="af817-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `:::no-loc(Q#):::`, and select the **:::no-loc(Q#)::: Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="af817-114">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="af817-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="af817-115">Desde la línea de comandos favorita, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="af817-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang :::no-loc(Q#)::: -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="af817-116">El nuevo proyecto tiene un único archivo `Tests.qs` , lo que proporciona un lugar cómodo para definir nuevas :::no-loc(Q#)::: pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="af817-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new :::no-loc(Q#)::: unit tests.</span></span>
<span data-ttu-id="af817-117">Inicialmente, este archivo contiene una prueba unitaria `AllocateQubit` de ejemplo que comprueba que una qubit recién asignada se encuentra en el estado $ \ket {0} $ e imprime un mensaje:</span><span class="sxs-lookup"><span data-stu-id="af817-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="af817-118">Cualquier :::no-loc(Q#)::: operación o función que toma un argumento de tipo `Unit` y devuelve `Unit` se puede marcar como una prueba unitaria mediante el `@Test("...")` atributo.</span><span class="sxs-lookup"><span data-stu-id="af817-118">Any :::no-loc(Q#)::: operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="af817-119">En el ejemplo anterior, el argumento para ese atributo, `"QuantumSimulator"` , especifica el destino en el que se ejecuta la prueba.</span><span class="sxs-lookup"><span data-stu-id="af817-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="af817-120">Una sola prueba puede ejecutarse en varios destinos.</span><span class="sxs-lookup"><span data-stu-id="af817-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="af817-121">Por ejemplo, agregue un atributo `@Test("ResourcesEstimator")` delante de `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="af817-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="af817-122">Guarde el archivo y ejecute todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="af817-122">Save the file and run all tests.</span></span> <span data-ttu-id="af817-123">Ahora debería haber dos pruebas unitarias, una en `AllocateQubit` la que se ejecuta en `QuantumSimulator` y otra en la que se ejecuta en `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="af817-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="af817-124">El :::no-loc(Q#)::: compilador reconoce los destinos integrados `"QuantumSimulator"` , `"ToffoliSimulator"` y `"ResourcesEstimator"` como destinos de ejecución válidos para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="af817-124">The :::no-loc(Q#)::: compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="af817-125">También es posible especificar cualquier nombre completo para definir un destino de ejecución personalizado.</span><span class="sxs-lookup"><span data-stu-id="af817-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="af817-126">Ejecutar :::no-loc(Q#)::: pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="af817-126">Running :::no-loc(Q#)::: Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="af817-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="af817-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="af817-128">Como programa de instalación única por solución, vaya al menú **prueba** y seleccione **configuración de pruebas > arquitectura de procesador predeterminada > x64** .</span><span class="sxs-lookup"><span data-stu-id="af817-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="af817-129">La configuración predeterminada de la arquitectura del procesador para Visual Studio se almacena en el archivo de opciones de solución ( `.suo` ) para cada solución.</span><span class="sxs-lookup"><span data-stu-id="af817-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="af817-130">Si elimina este archivo, deberá seleccionar **x64** como su arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="af817-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="af817-131">Compile el proyecto, abra el menú **prueba** y seleccione **Windows > explorador de pruebas** .</span><span class="sxs-lookup"><span data-stu-id="af817-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="af817-132">**AllocateQubit** se muestra en la lista de pruebas en el grupo **pruebas no ejecutadas** .</span><span class="sxs-lookup"><span data-stu-id="af817-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="af817-133">Seleccione **ejecutar todas** o ejecutar esta prueba individual.</span><span class="sxs-lookup"><span data-stu-id="af817-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="af817-134">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="af817-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="af817-135">Para ejecutar las pruebas, navegue hasta la carpeta del proyecto (la carpeta que contiene `Tests.csproj` ) y ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="af817-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="af817-136">Debería obtener una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="af817-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="af817-137">Las pruebas unitarias se pueden filtrar según su nombre o destino de ejecución:</span><span class="sxs-lookup"><span data-stu-id="af817-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="af817-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="af817-138">\*\*_</span></span>

<span data-ttu-id="af817-139">La función intrínseca <xref:Microsoft.Quantum.Intrinsic.Message> tiene el tipo `(String -> Unit)` y permite la creación de mensajes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="af817-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="af817-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="af817-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="af817-141">Después de ejecutar una prueba en el explorador de pruebas y hacer clic en la prueba, se muestra un panel con información sobre la serie de pruebas: estado de superación/error, tiempo transcurrido y un vínculo a la salida.</span><span class="sxs-lookup"><span data-stu-id="af817-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="af817-142">Haga clic en _ *Output* \* para abrir la salida de la prueba en una nueva ventana.</span><span class="sxs-lookup"><span data-stu-id="af817-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![resultados de la prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="af817-144">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="af817-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="af817-145">El estado de superación o error de cada prueba se imprime en la consola mediante `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="af817-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="af817-146">En el caso de las pruebas con errores, las salidas también se imprimen en la consola para ayudar a diagnosticar el error.</span><span class="sxs-lookup"><span data-stu-id="af817-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="af817-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="af817-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="af817-148">Hechos y aserciones</span><span class="sxs-lookup"><span data-stu-id="af817-148">Facts and Assertions</span></span>

<span data-ttu-id="af817-149">Dado que las funciones de :::no-loc(Q#)::: no tienen efectos secundarios _lógicos_ , nunca puede observar, desde dentro de un :::no-loc(Q#)::: programa, cualquier otro tipo de efecto de ejecutar una función cuyo tipo de salida sea la tupla vacía `()` .</span><span class="sxs-lookup"><span data-stu-id="af817-149">Because functions in :::no-loc(Q#)::: have no _logical_ side effects, you can never observe, from within a :::no-loc(Q#)::: program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="af817-150">Es decir, una máquina de destino puede elegir no ejecutar ninguna función que devuelva `()` con la garantía de que esta omisión no modificará el comportamiento de ningún :::no-loc(Q#)::: código siguiente.</span><span class="sxs-lookup"><span data-stu-id="af817-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following :::no-loc(Q#)::: code.</span></span>
<span data-ttu-id="af817-151">Este comportamiento hace que las funciones devuelvan `()` (como `Unit` ) una herramienta útil para insertar aserciones y lógica de depuración en :::no-loc(Q#)::: programas.</span><span class="sxs-lookup"><span data-stu-id="af817-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into :::no-loc(Q#)::: programs.</span></span> 

<span data-ttu-id="af817-152">Veamos un ejemplo sencillo:</span><span class="sxs-lookup"><span data-stu-id="af817-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="af817-153">Aquí, la palabra clave `fail` indica que el cálculo no debe continuar y genera una excepción en el equipo de destino que ejecuta el :::no-loc(Q#)::: programa.</span><span class="sxs-lookup"><span data-stu-id="af817-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the :::no-loc(Q#)::: program.</span></span>
<span data-ttu-id="af817-154">Por definición, un error de este tipo no se puede observar desde dentro :::no-loc(Q#)::: , ya que el equipo de destino ya no ejecuta el :::no-loc(Q#)::: código después de alcanzar una `fail` instrucción.</span><span class="sxs-lookup"><span data-stu-id="af817-154">By definition, a failure of this kind cannot be observed from within :::no-loc(Q#):::, as the target machine no longer runs the :::no-loc(Q#)::: code after reaching a `fail` statement.</span></span>
<span data-ttu-id="af817-155">Por lo tanto, si continuamos después de una llamada a `PositivityFact` , podemos estar seguros de que su entrada fue positiva.</span><span class="sxs-lookup"><span data-stu-id="af817-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="af817-156">Tenga en cuenta que se puede implementar el mismo comportamiento que `PositivityFact` el uso [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) de la función del <xref:Microsoft.Quantum.Diagnostics> espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="af817-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="af817-157">_Assertions \*, por otro lado, se usan de forma similar a los hechos, pero pueden depender del estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="af817-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="af817-158">En consecuencia, se definen como operaciones, mientras que los hechos se definen como funciones (como en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="af817-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="af817-159">Para entender la distinción, considere el siguiente uso de un hecho dentro de una aserción:</span><span class="sxs-lookup"><span data-stu-id="af817-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="af817-160">Aquí se usa la operación <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> para devolver el número de qubits disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="af817-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="af817-161">Dado que esto depende del estado global del programa y su entorno de ejecución, nuestra definición de `AssertQubitsAreAvailable` también debe ser una operación.</span><span class="sxs-lookup"><span data-stu-id="af817-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="af817-162">Sin embargo, podemos usar ese estado global para producir un `Bool` valor simple como entrada para la `Fact` función.</span><span class="sxs-lookup"><span data-stu-id="af817-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="af817-163">[El](xref:microsoft.quantum.libraries.standard.prelude)preparativo, que se basa en estas ideas, ofrece dos aserciones especialmente útiles <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> y <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> ambas se modelan como operaciones en `()` .</span><span class="sxs-lookup"><span data-stu-id="af817-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="af817-164">Cada una de estas aserciones toma un operador Pauli que describe una medida determinada de interés, un registro Quantum en el que se realiza una medida y un resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="af817-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="af817-165">Los equipos de destino que funcionan por simulación no están limitados por [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem)y pueden realizar tales mediciones sin alterar el registro que pasa a dichas aserciones.</span><span class="sxs-lookup"><span data-stu-id="af817-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="af817-166">Un simulador puede, de forma similar a la `PositivityFact` función anterior, detener el cálculo si el resultado hipotético no se observa en la práctica:</span><span class="sxs-lookup"><span data-stu-id="af817-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in :::no-loc(Q#):::,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="af817-167">En el hardware de Quantum físico, donde el teorema sin clonación impide el examen de un estado de Quantum, las `AssertMeasurement` `AssertMeasurementProbability` operaciones y simplemente devuelven `()` sin ningún otro efecto.</span><span class="sxs-lookup"><span data-stu-id="af817-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="af817-168">El <xref:Microsoft.Quantum.Diagnostics> espacio de nombres proporciona varias funciones más de la `Assert` familia, con las que puede comprobar condiciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="af817-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="af817-169">Funciones de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="af817-169">Dump Functions</span></span>

<span data-ttu-id="af817-170">Para ayudar a solucionar problemas de los programas Quantum, el <xref:Microsoft.Quantum.Diagnostics> espacio de nombres ofrece dos funciones que pueden volcar en un archivo el estado actual del equipo de destino: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> y <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="af817-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="af817-171">La salida generada de cada depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="af817-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="af817-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="af817-172">DumpMachine</span></span>

<span data-ttu-id="af817-173">El simulador de Quantum de estado completo distribuido como parte del kit de desarrollo de Quantum escribe en el archivo la [función de onda](https://en.wikipedia.org/wiki/Wave_function) del sistema Quantum completo, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud de la probabilidad de medir el estado de base de cálculo $ \ket{n} $, donde $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ para bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="af817-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="af817-174">Por ejemplo, en un equipo con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ al llamar a <xref:Microsoft.Quantum.Diagnostics.DumpMachine> se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="af817-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="af817-175">La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.</span><span class="sxs-lookup"><span data-stu-id="af817-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="af817-176">El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{n} $ en formatos cartesianos y polares.</span><span class="sxs-lookup"><span data-stu-id="af817-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="af817-177">En detalle para la primera fila:</span><span class="sxs-lookup"><span data-stu-id="af817-177">In detail for the first row:</span></span>

* <span data-ttu-id="af817-178">**`∣0❭:`** esta fila corresponde al `0` Estado de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="af817-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="af817-179">**`0.707107 +  0.000000 i`** : la amplitud de probabilidad en formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="af817-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="af817-180">**` == `** : el `equal` signo separa ambas representaciones equivalentes.</span><span class="sxs-lookup"><span data-stu-id="af817-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="af817-181">**`**********  `** : Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.</span><span class="sxs-lookup"><span data-stu-id="af817-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="af817-182">**`[ 0.500000 ]`** : el valor numérico de la magnitud</span><span class="sxs-lookup"><span data-stu-id="af817-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="af817-183">**`    ---`** : Una representación gráfica de la fase de amplitud (vea la salida siguiente).</span><span class="sxs-lookup"><span data-stu-id="af817-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="af817-184">**`[ 0.0000 rad ]`** : valor numérico de la fase (en radianes).</span><span class="sxs-lookup"><span data-stu-id="af817-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="af817-185">Tanto la magnitud como la fase se muestran con una representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="af817-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="af817-186">La representación de la magnitud es directa: muestra una barra de `*` ; cuanto mayor es la probabilidad, mayor será la barra.</span><span class="sxs-lookup"><span data-stu-id="af817-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="af817-187">En la fase, se muestran los siguientes símbolos para representar el ángulo en función de los intervalos:</span><span class="sxs-lookup"><span data-stu-id="af817-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="af817-188">Los ejemplos siguientes muestran `DumpMachine` para algunos Estados comunes:</span><span class="sxs-lookup"><span data-stu-id="af817-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="af817-189">El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó qubit o su posición dentro de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="af817-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="af817-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="af817-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="af817-191">Para buscar un identificador de qubit en Visual Studio, coloque un punto de interrupción en el código e inspeccione el valor de una variable qubit, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="af817-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostrar el identificador de qubit en Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="af817-193">el qubit con el índice `0` de `register2` tiene el identificador = `3` , el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="af817-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="af817-194">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="af817-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="af817-195">Puede buscar un identificador de qubit mediante la <xref:Microsoft.Quantum.Intrinsic.Message> función y pasar la variable qubit en el mensaje, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="af817-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="af817-196">Esto podría generar esta salida:</span><span class="sxs-lookup"><span data-stu-id="af817-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="af817-197">lo que significa que el qubit con el índice `0` de `register2` tiene `3` el identificador =, el qubit con el índice `1` tiene el identificador = `2` .</span><span class="sxs-lookup"><span data-stu-id="af817-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="af817-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="af817-198">\*\*_</span></span>

<span data-ttu-id="af817-199">Dado que <xref:Microsoft.Quantum.Diagnostics.DumpMachine> forma parte del  <xref:Microsoft.Quantum.Diagnostics> espacio de nombres, debe agregar una `open` instrucción para tener acceso a ella:</span><span class="sxs-lookup"><span data-stu-id="af817-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="af817-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="af817-200">DumpRegister</span></span>

<span data-ttu-id="af817-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> funciona como <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , salvo que también toma una matriz de qubits para limitar la cantidad de información a solo el correspondiente qubits.</span><span class="sxs-lookup"><span data-stu-id="af817-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="af817-202">Como con <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , la información generada por <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="af817-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="af817-203">Para el simulador de Quantum de estado completo, escribe en el archivo la función Wave hasta una fase global del subsistema Quantum generada por el qubits proporcionado en el mismo formato que <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="af817-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="af817-204">Por ejemplo, vuelva a realizar una máquina con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ) la llamada de \end{align} $ $ que llama <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a `qubit[0]` genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="af817-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="af817-205">y al llamar a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> para `qubit[1]` se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="af817-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="af817-206">En general, el estado de un registro que está inenredado con otro registro es un estado mixto en lugar de un estado puro.</span><span class="sxs-lookup"><span data-stu-id="af817-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="af817-207">En este caso, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> genera el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="af817-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="af817-208">En el ejemplo siguiente se muestra cómo puede usar <xref:Microsoft.Quantum.Diagnostics.DumpRegister> y <xref:Microsoft.Quantum.Diagnostics.DumpMachine> en el :::no-loc(Q#)::: código:</span><span class="sxs-lookup"><span data-stu-id="af817-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your :::no-loc(Q#)::: code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="af817-209">Depuración</span><span class="sxs-lookup"><span data-stu-id="af817-209">Debugging</span></span>

<span data-ttu-id="af817-210">Sobre `Assert` `Dump` las funciones y y las operaciones, :::no-loc(Q#)::: admite un subconjunto de capacidades de depuración estándar de Visual Studio: [establecer puntos de interrupción de línea](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [recorrer paso a paso el código mediante F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)y [inspeccionar los valores de las variables clásicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) es posible al ejecutar el código en el simulador.</span><span class="sxs-lookup"><span data-stu-id="af817-210">On top of `Assert` and `Dump` functions and operations, :::no-loc(Q#)::: supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="af817-211">La depuración en Visual Studio Code aprovecha las capacidades de depuración proporcionadas por C# para la extensión de Visual Studio Code con tecnología de OmniSharp y requiere la instalación de la [versión más reciente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="af817-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
