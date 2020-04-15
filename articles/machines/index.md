---
title: Simuladores cuánticos y aplicaciones host | Microsoft Docs
description: Describe cómo impulsar los simuladores cuánticos con un lenguaje informático clásico .NET, por lo general C# o Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442222"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="98816-103">Simuladores cuánticos y aplicaciones host</span><span class="sxs-lookup"><span data-stu-id="98816-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="98816-104">Temas que se abordarán</span><span class="sxs-lookup"><span data-stu-id="98816-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="98816-105">Ejecución de algoritmos cuánticos</span><span class="sxs-lookup"><span data-stu-id="98816-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="98816-106">Simuladores cuánticos incluidos en esta versión</span><span class="sxs-lookup"><span data-stu-id="98816-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="98816-107">Escritura de un controlador C# para un algoritmo cuántico</span><span class="sxs-lookup"><span data-stu-id="98816-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="98816-108">El modelo de ejecución de Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="98816-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="98816-109">En [Escritura de un programa cuántico](xref:microsoft.quantum.write-program), ejecutamos el algoritmo cuántico al pasar un objeto `QuantumSimulator` al método `Run` de la clase del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="98816-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="98816-110">La clase `QuantumSimulator` ejecuta el algoritmo cuántico mediante la simulación completa del vector de estado cuántico, que es ideal para ejecutar y probar `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="98816-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="98816-111">Consulte la [Guía de conceptos](xref:microsoft.quantum.concepts.intro) para más información sobre los vectores de estados cuánticos.</span><span class="sxs-lookup"><span data-stu-id="98816-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="98816-112">Se pueden usar otras máquinas de destino para ejecutar un algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="98816-113">La máquina es responsable de proporcionar las implementaciones de primitivas cuánticas del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="98816-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="98816-114">Esto incluye operaciones primitivas como H, CNOT y Measure, así como el seguimiento y la administración de cúbits.</span><span class="sxs-lookup"><span data-stu-id="98816-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="98816-115">Las distintas clases de máquinas cuánticas representan modelos de ejecución diferentes para el mismo algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="98816-116">Cada tipo de máquina cuántica puede ofrecer distintas implementaciones de estas operaciones primitivas.</span><span class="sxs-lookup"><span data-stu-id="98816-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="98816-117">Por ejemplo, el simulador de seguimiento de equipos cuánticos incluido en el kit de desarrollo no realiza ninguna simulación en lo absoluto.</span><span class="sxs-lookup"><span data-stu-id="98816-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="98816-118">En su lugar, hace un seguimiento del uso de puertas, cúbits y otros recursos para el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="98816-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="98816-119">Máquinas cuánticas</span><span class="sxs-lookup"><span data-stu-id="98816-119">Quantum Machines</span></span>

<span data-ttu-id="98816-120">En el futuro, se definirán clases de máquinas cuánticas adicionales para admitir otros tipos de simulación y la ejecución en equipos cuánticos topológicos.</span><span class="sxs-lookup"><span data-stu-id="98816-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="98816-121">Permitir que el algoritmo permanezca constante mientras varía la implementación de la máquina subyacente permite facilitar la prueba y depuración de un algoritmo en la simulación y, después, ejecutarlo en hardware real con la confianza de que el algoritmo no haya cambiado.</span><span class="sxs-lookup"><span data-stu-id="98816-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="98816-122">Lo que incluye esta versión</span><span class="sxs-lookup"><span data-stu-id="98816-122">What's Included in this Release</span></span>

<span data-ttu-id="98816-123">Esta versión de Quantum Developer Kit incluye varias clases de máquinas cuánticas.</span><span class="sxs-lookup"><span data-stu-id="98816-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="98816-124">Todas ellas se definen en el espacio de nombres `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="98816-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="98816-125">Un [simulador de vector de estado completo](xref:microsoft.quantum.machines.full-state-simulator), la clase `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="98816-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="98816-126">Un [estimador de recursos sencillo](xref:microsoft.quantum.machines.resources-estimator), la clase `ResourcesEstimator`, permite un análisis de nivel superior de los recursos necesarios para ejecutar un algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="98816-127">Un [estimador de recursos basado en seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro), la clase `QCTraceSimulator`, permite un análisis de nivel superior de los recursos necesarios para ejecutar un algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="98816-128">Un [simulador de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), la clase `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="98816-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="98816-129">Escritura de una aplicación host</span><span class="sxs-lookup"><span data-stu-id="98816-129">Writing a host application</span></span>

<span data-ttu-id="98816-130">En [Escritura de un programa cuántico](xref:microsoft.quantum.write-program), escribimos un controlador C# sencillo para el algoritmo de teletransporte.</span><span class="sxs-lookup"><span data-stu-id="98816-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="98816-131">Un controlador C# tiene 4 propósitos principales:</span><span class="sxs-lookup"><span data-stu-id="98816-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="98816-132">Construir la máquina de destino</span><span class="sxs-lookup"><span data-stu-id="98816-132">Constructing the target machine</span></span>
* <span data-ttu-id="98816-133">Calcular los argumentos necesarios para el algoritmo cuántico</span><span class="sxs-lookup"><span data-stu-id="98816-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="98816-134">Ejecutar el algoritmo cuántico mediante el simulador</span><span class="sxs-lookup"><span data-stu-id="98816-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="98816-135">Procesar el resultado de la operación</span><span class="sxs-lookup"><span data-stu-id="98816-135">Processing the result of the operation</span></span>

<span data-ttu-id="98816-136">Aquí analizaremos cada paso con más detalle.</span><span class="sxs-lookup"><span data-stu-id="98816-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="98816-137">Construcción de la máquina de destino</span><span class="sxs-lookup"><span data-stu-id="98816-137">Constructing the Target Machine</span></span>

<span data-ttu-id="98816-138">Las máquinas cuánticas son instancias de las clases .NET normales, por lo que se crean mediante la invocación de su constructor, del mismo modo que cualquier clase .NET.</span><span class="sxs-lookup"><span data-stu-id="98816-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="98816-139">Algunos simuladores, incluido `QuantumSimulator`, implementan la interfaz <xref:System.IDisposable?displayProperty=nameWithType> de .NET, por lo que se deben encapsular en una instrucción `using` de C#.</span><span class="sxs-lookup"><span data-stu-id="98816-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="98816-140">Cálculo de argumentos para el algoritmo</span><span class="sxs-lookup"><span data-stu-id="98816-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="98816-141">En el ejemplo de `Teleport`, calculamos algunos argumentos relativamente artificiales para pasar al algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="98816-142">Sin embargo, por lo general, el algoritmo cuántico requiere muchos datos y es fácil proporcionarlos desde el controlador clásico.</span><span class="sxs-lookup"><span data-stu-id="98816-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="98816-143">Por ejemplo, al realizar simulaciones químicas, el algoritmo cuántico requiere una tabla grande de integrales de interacción orbital molecular.</span><span class="sxs-lookup"><span data-stu-id="98816-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="98816-144">Por lo general, se leen desde un archivo que se proporciona al ejecutar el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="98816-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="98816-145">Como Q# no tiene un mecanismo para acceder al sistema de archivos, este tipo de datos lo recopila de mejor manera el controlador clásico y, luego, se pasa al método `Run` del algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="98816-146">Otro caso en el que el controlador clásico desempeña un papel clave es en los métodos variacionales.</span><span class="sxs-lookup"><span data-stu-id="98816-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="98816-147">En esta clase de algoritmos, un estado cuántico se prepara en función de algunos parámetros clásicos y ese estado se usa para calcular algún valor de interés.</span><span class="sxs-lookup"><span data-stu-id="98816-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="98816-148">Los parámetros se ajustan en función de algún tipo de algoritmo de aprendizaje automático o de escalada y el algoritmo cuántico se vuelve a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="98816-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="98816-149">En estos algoritmos, el algoritmo de escalada en sí se implementa mejor como una función puramente clásica a la que llama el controlador clásico; los resultados del algoritmo de escalada entonces se pasa a la ejecución siguiente del algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="98816-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="98816-150">Ejecución del algoritmo cuántico</span><span class="sxs-lookup"><span data-stu-id="98816-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="98816-151">Esta parte suele ser muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="98816-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="98816-152">Cada operación de Q # se compila en una clase que proporciona un método `Run` estático.</span><span class="sxs-lookup"><span data-stu-id="98816-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="98816-153">Los argumentos para este método los proporciona la tupla plana de argumento de la operación misma, además de un primer argumento adicional, que es el simulador con el cual se realiza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="98816-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="98816-154">Para una operación que espera la tupla denominada de tipo `(a: String, (b: Double, c: Double))`, su contraparte plana es de tipo `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="98816-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="98816-155">Existen algunos matices al pasar argumentos a un método `Run`:</span><span class="sxs-lookup"><span data-stu-id="98816-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="98816-156">Las matrices se deben encapsular en un objeto `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="98816-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="98816-157">Una clase `QArray` tiene un constructor que puede tomar cualquier colección ordenada (`IEnumerable<T>`) de los objetos adecuados.</span><span class="sxs-lookup"><span data-stu-id="98816-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="98816-158">La tupla vacía, `()` en Q#, se representa con `QVoid.Instance` en C#.</span><span class="sxs-lookup"><span data-stu-id="98816-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="98816-159">Las tuplas no vacías se representan como instancias `ValueTuple` de .NET.</span><span class="sxs-lookup"><span data-stu-id="98816-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="98816-160">Los tipos de Q# definidos por el usuario se pasan como su tipo base.</span><span class="sxs-lookup"><span data-stu-id="98816-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="98816-161">Para pasar una operación o función a un método `Run`, debe obtener una instancia de la clase de la operación o una clase de la función, a través del método `Get<>` del simulador.</span><span class="sxs-lookup"><span data-stu-id="98816-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="98816-162">Procesamiento de los resultados</span><span class="sxs-lookup"><span data-stu-id="98816-162">Processing the Results</span></span>

<span data-ttu-id="98816-163">Los resultados del algoritmo cuántico se devuelven desde el método `Run`.</span><span class="sxs-lookup"><span data-stu-id="98816-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="98816-164">El método `Run` se ejecuta de manera asincrónica, por lo que devuelva una instancia de <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="98816-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="98816-165">Hay varias maneras de obtener los resultados reales de la operación.</span><span class="sxs-lookup"><span data-stu-id="98816-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="98816-166">La más simple es mediante la propiedad [`Result` de`Task`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span><span class="sxs-lookup"><span data-stu-id="98816-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="98816-167">pero otras técnicas, como usar el [`Wait` método](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) o la [`await` palabra clave](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) de C# también funcionarán.</span><span class="sxs-lookup"><span data-stu-id="98816-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="98816-168">Al igual que con los argumentos, las tuplas de Q# se representan como instancias `ValueTuple` y las matrices de Q#, como instancias `QArray`.</span><span class="sxs-lookup"><span data-stu-id="98816-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="98816-169">Los tipos definidos por el usuario se devuelven como sus tipo bases.</span><span class="sxs-lookup"><span data-stu-id="98816-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="98816-170">La tupla vacía, `()`, se devuelve como una instancia de la clase `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="98816-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="98816-171">Muchos algoritmos cuánticos requieren un procesamiento posterior sustancial para derivar respuestas útiles.</span><span class="sxs-lookup"><span data-stu-id="98816-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="98816-172">Por ejemplo, la parte cuántica del algoritmo de Shor es solo el comienzo de un cálculo que busca los factores de un número.</span><span class="sxs-lookup"><span data-stu-id="98816-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="98816-173">En la mayoría de los casos, es más sencillo y más fácil realizar este tipo de procesamiento posterior en el controlador clásico.</span><span class="sxs-lookup"><span data-stu-id="98816-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="98816-174">Solo el controlador clásico puede informar de los resultados al usuario o escribirlos en el disco.</span><span class="sxs-lookup"><span data-stu-id="98816-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="98816-175">El controlador clásico tendrá acceso a las bibliotecas de análisis y a otras funciones matemáticas que no se exponen en Q#.</span><span class="sxs-lookup"><span data-stu-id="98816-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="98816-176">Errores</span><span class="sxs-lookup"><span data-stu-id="98816-176">Failures</span></span>

<span data-ttu-id="98816-177">Cuando la instrucción `fail` de Q# se alcanza durante la ejecución de una operación, se genera una excepción `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="98816-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="98816-178">Debido al uso de `System.Task` en el método `Run`, la excepción que se genera como resultado de una instrucción `fail` se encapsulará en una excepción `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="98816-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="98816-179">Para encontrar la razón real del error, debe iterar en `AggregateException` 
`InnerExceptions`, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98816-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="98816-180">Otros lenguajes clásicos</span><span class="sxs-lookup"><span data-stu-id="98816-180">Other Classical Languages</span></span>

<span data-ttu-id="98816-181">Aunque los ejemplos que proporcionamos se encuentran en C#, F# y Python, Quantum Development Kit también admite la escritura de programas host clásicos en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="98816-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="98816-182">Por ejemplo, si quiere escribir un programa host en Visual Basic, [debería funcionar correctamente](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="98816-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
