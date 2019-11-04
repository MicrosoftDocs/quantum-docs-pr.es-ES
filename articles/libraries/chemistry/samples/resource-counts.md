---
title: Obtención de recuentos de recursos | Microsoft Docs
description: Obtención de documentos de recuentos de recursos
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: f9311c1987ced4336c4e98bdb984fbee009e9acc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442462"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="15c88-103">Obtención de recuentos de recursos</span><span class="sxs-lookup"><span data-stu-id="15c88-103">Obtaining resource counts</span></span>

<span data-ttu-id="15c88-104">El costo de simular $n $ qubits en equipos clásico escala exponencialmente con $n $.</span><span class="sxs-lookup"><span data-stu-id="15c88-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="15c88-105">Esto limita en gran medida el tamaño de una simulación de química de Quantum que se puede llevar a cabo con el simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="15c88-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="15c88-106">En el caso de instancias grandes de química, podemos obtener información útil.</span><span class="sxs-lookup"><span data-stu-id="15c88-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="15c88-107">En este caso, veremos cómo los costos de recursos, como el número de puertas de T o de CNOT, para simular la química se pueden obtener de manera automatizada mediante el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="15c88-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="15c88-108">Esta información nos informa de cuándo los equipos Quantum pueden ser lo suficientemente grandes como para ejecutar estos algoritmos de química de Quantum.</span><span class="sxs-lookup"><span data-stu-id="15c88-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="15c88-109">Como referencia, vea el ejemplo de `GetGateCount` proporcionado.</span><span class="sxs-lookup"><span data-stu-id="15c88-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="15c88-110">Supongamos que ya tenemos una instancia de `FermionHamiltonian`, por ejemplo, que se carga desde el esquema Broombridge, como se describe en el ejemplo de [carga de archivos](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="15c88-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="15c88-111">La sintaxis para obtener estimaciones de recursos es casi idéntica a la ejecución del algoritmo en el simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="15c88-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="15c88-112">Simplemente elegiremos un equipo de destino diferente.</span><span class="sxs-lookup"><span data-stu-id="15c88-112">We simply choose a different target machine.</span></span> <span data-ttu-id="15c88-113">Para los fines de las estimaciones de recursos, basta con evaluar el costo de un solo paso de Trotter o un recorrido de Quantum creado por la técnica de Qubitization.</span><span class="sxs-lookup"><span data-stu-id="15c88-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="15c88-114">La forma reutilizable para invocar estos algoritmos es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="15c88-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="15c88-115">Ahora se configura el simulador de seguimiento para realizar un seguimiento de los recursos que le interesan.</span><span class="sxs-lookup"><span data-stu-id="15c88-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="15c88-116">En este caso, se cuentan las operaciones de Quantum primitivas estableciendo la marca de `usePrimitiveOperationsCounter` en `true`.</span><span class="sxs-lookup"><span data-stu-id="15c88-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="15c88-117">Un `throwOnUnconstraintMeasurement` de detalles técnicos se establece en `false` para evitar excepciones en los casos en los que el código de Q # no valida correctamente la probabilidad de los resultados de la medición, si se realizan.</span><span class="sxs-lookup"><span data-stu-id="15c88-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="15c88-118">Ahora ejecutamos el algoritmo Quantum desde el programa de controlador como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="15c88-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```