---
title: 'Técnicas de Q #: pruebas y depuración | Microsoft Docs'
description: 'Técnicas de Q #: pruebas y depuración'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183495"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="4eb66-103">Pruebas y depuración</span><span class="sxs-lookup"><span data-stu-id="4eb66-103">Testing and Debugging</span></span>

<span data-ttu-id="4eb66-104">Al igual que con la programación clásica, es esencial poder comprobar que los programas Quantum funcionan según lo previsto y para poder diagnosticar un programa Quantum que no sea correcto.</span><span class="sxs-lookup"><span data-stu-id="4eb66-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="4eb66-105">En esta sección, trataremos las herramientas que ofrece Q # para probar y depurar programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="4eb66-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="4eb66-106">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="4eb66-106">Unit Tests</span></span>

<span data-ttu-id="4eb66-107">Un método común para probar programas clásico es escribir programas pequeños denominados *pruebas unitarias* que ejecutan código en una biblioteca y comparan su salida con alguna salida esperada.</span><span class="sxs-lookup"><span data-stu-id="4eb66-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="4eb66-108">Por ejemplo, es posible que deseemos asegurarse de que `Square(2)` devuelve `4`, ya que sabemos *un priori* que es $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="4eb66-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="4eb66-109">Q # admite la creación de pruebas unitarias para programas Quantum y que se pueden ejecutar como pruebas en el marco de pruebas unitarias de [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="4eb66-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="4eb66-110">Crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="4eb66-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4eb66-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eb66-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eb66-112">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="4eb66-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="4eb66-113">Vaya al menú `File` y seleccione `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="4eb66-114">En el explorador de plantillas de proyecto, en `Installed` > `Visual C#`, seleccione la plantilla `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4eb66-115">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eb66-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eb66-116">Desde la línea de comandos favorita, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4eb66-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="4eb66-117">En cualquier caso, el nuevo proyecto tendrá dos archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="4eb66-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="4eb66-118">El primer archivo, `Tests.qs`, proporciona un lugar cómodo para definir nuevas pruebas unitarias de Q #.</span><span class="sxs-lookup"><span data-stu-id="4eb66-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="4eb66-119">Inicialmente, este archivo contiene una prueba unitaria de ejemplo `AllocateQubitTest` que comprueba que una qubit recién asignada se encuentra en $ \ket{0}$ State e imprime un mensaje:</span><span class="sxs-lookup"><span data-stu-id="4eb66-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="4eb66-120">Cualquier operación Q # compatible con el tipo `(Unit => Unit)` o la función compatible con `(Unit -> Unit)` se puede ejecutar como una prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="4eb66-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="4eb66-121">El segundo archivo, `TestSuiteRunner.cs` contiene un método que detecta y ejecuta las pruebas unitarias de Q #.</span><span class="sxs-lookup"><span data-stu-id="4eb66-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="4eb66-122">Este es el método `TestTarget` anotado con `OperationDriver` atributo.</span><span class="sxs-lookup"><span data-stu-id="4eb66-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="4eb66-123">El atributo `OperationDriver` forma parte de la biblioteca de extensiones xUnit Microsoft. Quantum. Simulation. xUnit.</span><span class="sxs-lookup"><span data-stu-id="4eb66-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="4eb66-124">El marco de pruebas unitarias llama a `TestTarget` método para cada prueba unitaria de Q # que ha descubierto.</span><span class="sxs-lookup"><span data-stu-id="4eb66-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="4eb66-125">El marco de trabajo pasa la descripción de la prueba unitaria al método a través de `op` argumento.</span><span class="sxs-lookup"><span data-stu-id="4eb66-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="4eb66-126">La siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="4eb66-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="4eb66-127">ejecuta la prueba unitaria en `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="4eb66-128">De forma predeterminada, el mecanismo de detección de pruebas unitarias busca todas las funciones Q # u operaciones de tipo compatible que satisfagan las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4eb66-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="4eb66-129">Se encuentra en el mismo ensamblado que el método anotado con el atributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="4eb66-130">Se encuentra en el mismo espacio de nombres que el método anotado con el atributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="4eb66-131">Tiene un nombre que termina en `Test`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="4eb66-132">Se puede establecer un ensamblado, un espacio de nombres y un sufijo para las funciones y operaciones de pruebas unitarias mediante parámetros opcionales del atributo `OperationDriver`:</span><span class="sxs-lookup"><span data-stu-id="4eb66-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="4eb66-133">`AssemblyName` parámetro establece el nombre del ensamblado que se busca en las pruebas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="4eb66-134">`TestNamespace` parámetro establece el nombre del espacio de nombres en el que se buscan las pruebas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="4eb66-135">`Suffix` establece el sufijo de los nombres de operación o función que se consideran pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="4eb66-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="4eb66-136">Además, el parámetro opcional `TestCasePrefix` permite establecer un prefijo para el nombre del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="4eb66-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="4eb66-137">El prefijo delante del nombre de la operación aparecerá en la lista de casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="4eb66-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="4eb66-138">Por ejemplo, `TestCasePrefix = "QSim:"` hará que `AllocateQubitTest` aparezca como `QSim:AllocateQubitTest` en la lista de pruebas encontradas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="4eb66-139">Esto puede ser útil para indicar, por ejemplo, el simulador que se utiliza para ejecutar una prueba.</span><span class="sxs-lookup"><span data-stu-id="4eb66-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="4eb66-140">Ejecutar pruebas unitarias de Q #</span><span class="sxs-lookup"><span data-stu-id="4eb66-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4eb66-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eb66-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eb66-142">Como configuración única por solución, vaya a `Test` menú y seleccione `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="4eb66-143">La configuración predeterminada de la arquitectura del procesador para Visual Studio se almacena en el archivo de opciones de solución (`.suo`) de cada solución.</span><span class="sxs-lookup"><span data-stu-id="4eb66-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="4eb66-144">Si elimina este archivo, tendrá que volver a seleccionar `X64` como su arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="4eb66-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="4eb66-145">Compile el proyecto, vaya al menú de `Test` y seleccione `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="4eb66-146">`AllocateQubitTest` se mostrará en la lista de pruebas en el grupo de `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="4eb66-147">Seleccione `Run All` o ejecute esta prueba individual y debe pasarse.</span><span class="sxs-lookup"><span data-stu-id="4eb66-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4eb66-148">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eb66-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eb66-149">Para ejecutar pruebas, navegue a la carpeta del proyecto (la carpeta que contiene `Tests.csproj`) y ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="4eb66-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="4eb66-150">Debería obtener una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4eb66-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="4eb66-151">Registro y aserciones</span><span class="sxs-lookup"><span data-stu-id="4eb66-151">Logging and Assertions</span></span>

<span data-ttu-id="4eb66-152">Una consecuencia importante del hecho de que las funciones en Q # no tienen efectos secundarios es que los efectos de ejecutar una función cuyo tipo de salida sea la tupla vacía `()` nunca se pueden observar desde un programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="4eb66-153">Es decir, una máquina de destino puede elegir no ejecutar ninguna función que devuelva `()` con la garantía de que esta omisión no modificará el comportamiento de ningún código de Q # siguiente.</span><span class="sxs-lookup"><span data-stu-id="4eb66-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="4eb66-154">Esto hace que las funciones devuelvan `()` una herramienta útil para insertar aserciones y lógica de depuración en programas de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="4eb66-155">Registro</span><span class="sxs-lookup"><span data-stu-id="4eb66-155">Logging</span></span>

<span data-ttu-id="4eb66-156">La función intrínseca <xref:microsoft.quantum.intrinsic.message> tiene el tipo `(String -> Unit)` y permite la creación de mensajes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="4eb66-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="4eb66-157">La acción de `onLog` de `QuantumSimulator` se puede usar para definir las acciones que se realizan cuando se llama a `Message`de Q # Code.</span><span class="sxs-lookup"><span data-stu-id="4eb66-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="4eb66-158">De forma predeterminada, los mensajes registrados se imprimen en la salida estándar.</span><span class="sxs-lookup"><span data-stu-id="4eb66-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="4eb66-159">Al definir un conjunto de pruebas unitarias, los mensajes registrados se pueden dirigir a la salida de la prueba.</span><span class="sxs-lookup"><span data-stu-id="4eb66-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="4eb66-160">Cuando se crea un proyecto a partir de la plantilla de proyecto de prueba de Q #, esta redirección está preconfigurada para el conjunto y se crea de forma predeterminada de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4eb66-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4eb66-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eb66-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eb66-162">Después de ejecutar una prueba en el explorador de pruebas y hacer clic en la prueba, aparecerá un panel con información sobre la ejecución de pruebas: estado superado/error, tiempo transcurrido y un vínculo de "salida".</span><span class="sxs-lookup"><span data-stu-id="4eb66-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="4eb66-163">Si hace clic en el vínculo "salida", la salida de la prueba se abrirá en una nueva ventana.</span><span class="sxs-lookup"><span data-stu-id="4eb66-163">If you click the "Output" link, test output will open in a new window.</span></span>

![resultados de la prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4eb66-165">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eb66-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eb66-166">El estado de superación o error de cada prueba se imprime en la consola mediante `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="4eb66-167">En el caso de las pruebas con errores, las salidas registradas como resultado de la `output.WriteLine(msg)` llamada anterior también se imprimen en la consola de para ayudar a diagnosticar el error.</span><span class="sxs-lookup"><span data-stu-id="4eb66-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="4eb66-168">Aserciones</span><span class="sxs-lookup"><span data-stu-id="4eb66-168">Assertions</span></span>

<span data-ttu-id="4eb66-169">Se puede aplicar la misma lógica a la implementación de aserciones.</span><span class="sxs-lookup"><span data-stu-id="4eb66-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="4eb66-170">Veamos un ejemplo sencillo:</span><span class="sxs-lookup"><span data-stu-id="4eb66-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="4eb66-171">Aquí, la palabra clave `fail` indica que el cálculo no debe continuar, con lo que se genera una excepción en el equipo de destino que ejecuta el programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="4eb66-172">Por definición, un error de este tipo no se puede observar desde Q #, ya que no se ejecuta más código de Q # después de que se alcance una instrucción de `fail`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="4eb66-173">Por lo tanto, si continuamos después de una llamada a `AssertPositive`, podemos estar seguros de que su entrada fue positiva.</span><span class="sxs-lookup"><span data-stu-id="4eb66-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="4eb66-174">Basándose en estas ideas, [el predicho](xref:microsoft.quantum.libraries.standard.prelude) ofrece dos aserciones especialmente útiles, <xref:microsoft.quantum.intrinsic.assert> y <xref:microsoft.quantum.intrinsic.assertprob> modeladas como operaciones en `()`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="4eb66-175">Cada una de estas aserciones toma un operador Pauli que describe una medida determinada de interés, un registro Quantum en el que se va a realizar una medida y un resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="4eb66-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="4eb66-176">En las máquinas de destino que funcionan por simulación, no están limitadas por [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem)y pueden realizar tales mediciones sin alterar el registro que se pasa a dichas aserciones.</span><span class="sxs-lookup"><span data-stu-id="4eb66-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="4eb66-177">Un simulador puede, de forma similar a la función `AssertPositive` anterior, anular el cálculo si el resultado hipotético no se observa en la práctica:</span><span class="sxs-lookup"><span data-stu-id="4eb66-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="4eb66-178">En el hardware de Quantum físico, donde el teorema sin clonación impide el examen del estado de Quantum, las operaciones de `Assert` y `AssertProb` simplemente devuelven `()` sin ningún otro efecto.</span><span class="sxs-lookup"><span data-stu-id="4eb66-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="4eb66-179">El espacio de nombres <xref:microsoft.quantum.diagnostics> proporciona varias funciones más de la familia de `Assert` que nos permiten comprobar condiciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="4eb66-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="4eb66-180">Funciones de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="4eb66-180">Dump Functions</span></span>

<span data-ttu-id="4eb66-181">Para ayudar a solucionar problemas de los programas Quantum, el espacio de nombres <xref:microsoft.quantum.diagnostics> ofrece dos funciones que pueden volcar en un archivo el estado actual del equipo de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> y <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="4eb66-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="4eb66-182">La salida generada de cada depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4eb66-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="4eb66-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="4eb66-183">DumpMachine</span></span>

<span data-ttu-id="4eb66-184">El simulador de Quantum de estado completo distribuido como parte del kit de desarrollo de Quantum escribe en el archivo la [función de onda](https://en.wikipedia.org/wiki/Wave_function) del sistema de Quantum completo, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud del probabilidad de medir el estado de la base de cálculo $ \ket{n} $, donde $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ para bits $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="4eb66-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="4eb66-185">Por ejemplo, en un equipo con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ al llamar a <xref:microsoft.quantum.diagnostics.dumpmachine> se genera este resultado. :</span><span class="sxs-lookup"><span data-stu-id="4eb66-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4eb66-186">La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.</span><span class="sxs-lookup"><span data-stu-id="4eb66-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="4eb66-187">El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{n} $ en formatos cartesianos y polares.</span><span class="sxs-lookup"><span data-stu-id="4eb66-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="4eb66-188">En detalle para la primera fila:</span><span class="sxs-lookup"><span data-stu-id="4eb66-188">In detail for the first row:</span></span>

* <span data-ttu-id="4eb66-189">**`∣0❭:`** esta fila corresponde al estado base de cálculo de `0`</span><span class="sxs-lookup"><span data-stu-id="4eb66-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="4eb66-190">**`0.707107 +  0.000000 i`** : la amplitud de probabilidad en formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="4eb66-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="4eb66-191">**` == `** : el signo de `equal` separado por ambas representaciones equivalentes.</span><span class="sxs-lookup"><span data-stu-id="4eb66-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="4eb66-192">**`**********  `** : una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.</span><span class="sxs-lookup"><span data-stu-id="4eb66-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="4eb66-193">**`[ 0.500000 ]`** : el valor numérico de la magnitud</span><span class="sxs-lookup"><span data-stu-id="4eb66-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="4eb66-194">**`    ---`** : una representación gráfica de la fase de amplitud (consulte a continuación).</span><span class="sxs-lookup"><span data-stu-id="4eb66-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="4eb66-195">**`[ 0.0000 rad ]`** : valor numérico de la fase (en radianes).</span><span class="sxs-lookup"><span data-stu-id="4eb66-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="4eb66-196">Tanto la magnitud como la fase se muestran con una representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="4eb66-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="4eb66-197">La representación de la magnitud es directa: muestra una barra de `*`. cuanto mayor sea la probabilidad, mayor será la barra.</span><span class="sxs-lookup"><span data-stu-id="4eb66-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="4eb66-198">En la fase, se muestran los siguientes símbolos para representar el ángulo en función de los intervalos:</span><span class="sxs-lookup"><span data-stu-id="4eb66-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="4eb66-199">Los ejemplos siguientes muestran `DumpMachine` para algunos Estados comunes:</span><span class="sxs-lookup"><span data-stu-id="4eb66-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="4eb66-200">El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó qubit o su posición dentro de un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="4eb66-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4eb66-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eb66-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="4eb66-202">Puede averiguar un identificador de qubit en Visual Studio si coloca un punto de interrupción en el código y inspecciona el valor de una variable de qubit, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb66-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostrar el identificador de qubit en Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="4eb66-204">el qubit con el índice `0` en `register2` tiene el identificador =`3`, el qubit con el índice `1` tiene el identificador =`2`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="4eb66-205">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eb66-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="4eb66-206">Puede averiguar un identificador de qubit mediante la función <xref:microsoft.quantum.intrinsic.message> y pasar la variable qubit en el mensaje, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb66-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="4eb66-207">Esto podría generar esta salida:</span><span class="sxs-lookup"><span data-stu-id="4eb66-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="4eb66-208">lo que significa que el qubit con el índice `0` en `register2` tiene el identificador =`3`, el qubit con el índice `1` tiene el identificador =`2`.</span><span class="sxs-lookup"><span data-stu-id="4eb66-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="4eb66-209"><xref:microsoft.quantum.diagnostics.dumpmachine> forma parte del espacio de nombres <xref:microsoft.quantum.diagnostics>, por lo que para poder usarlo debe agregar una instrucción `open`:</span><span class="sxs-lookup"><span data-stu-id="4eb66-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="4eb66-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="4eb66-210">DumpRegister</span></span>

<span data-ttu-id="4eb66-211"><xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine>, salvo que también toma una matriz de qubits para limitar la cantidad de información a solo el correspondiente qubits.</span><span class="sxs-lookup"><span data-stu-id="4eb66-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="4eb66-212">Como con <xref:microsoft.quantum.diagnostics.dumpmachine>, la información generada por <xref:microsoft.quantum.diagnostics.dumpregister> depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4eb66-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="4eb66-213">Para el simulador de Quantum de estado completo, escribe en el archivo la función Wave hasta una fase global del subsistema Quantum generada por el qubits proporcionado en el mismo formato que <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="4eb66-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="4eb66-214">Por ejemplo, vuelva a realizar una máquina con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ les{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ al llamar a <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="4eb66-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4eb66-215">y al llamar a <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` se genera este resultado:</span><span class="sxs-lookup"><span data-stu-id="4eb66-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="4eb66-216">En general, el estado de un registro que está inenredado con otro registro es un estado mixto en lugar de un estado puro.</span><span class="sxs-lookup"><span data-stu-id="4eb66-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="4eb66-217">En este caso, <xref:microsoft.quantum.diagnostics.dumpregister> genera el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="4eb66-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="4eb66-218">En el ejemplo siguiente se muestra cómo puede usar tanto <xref:microsoft.quantum.diagnostics.dumpregister> como <xref:microsoft.quantum.diagnostics.dumpmachine> en el código de preguntas y respuestas:</span><span class="sxs-lookup"><span data-stu-id="4eb66-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="4eb66-219">Depuración</span><span class="sxs-lookup"><span data-stu-id="4eb66-219">Debugging</span></span>

<span data-ttu-id="4eb66-220">Sobre las funciones y operaciones de `Assert` y `Dump`, Q # admite un subconjunto de las funcionalidades de depuración estándar de Visual Studio: [establecer puntos de interrupción de línea](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [recorrer el código mediante F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspeccionar valores de variables clásicas. ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)es posible durante la ejecución del código en el simulador.</span><span class="sxs-lookup"><span data-stu-id="4eb66-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="4eb66-221">Todavía no se admite la depuración en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4eb66-221">Debugging in Visual Studio Code is not yet supported.</span></span>

