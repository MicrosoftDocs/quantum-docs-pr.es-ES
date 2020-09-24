---
title: 'Simulador de seguimiento cuántico: Kit de desarrollo de Microsoft Quantum'
description: Obtenga información sobre cómo usar el simulador de seguimiento cuántico de Microsoft para depurar código clásico y calcular los requisitos de recursos de un programa de Q#.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54a1f63461cfcc8146f7dc4d18d321238d77454d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833360"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="b4ce0-103">Simulador de seguimiento cuántico del kit de desarrollo de Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="b4ce0-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="b4ce0-104">La clase <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> de QDK ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="b4ce0-105">Por esta razón, el simulador de seguimiento cuántico puede ejecutar programas cuánticos que usan miles de cúbits.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="b4ce0-106">Esto tiene dos propósitos principales:</span><span class="sxs-lookup"><span data-stu-id="b4ce0-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="b4ce0-107">Depurar código clásico que forma parte de un programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="b4ce0-108">Calcular los recursos necesarios para ejecutar una determinada instancia de un programa cuántico en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="b4ce0-109">De hecho, el [estimador de recursos](xref:microsoft.quantum.machines.resources-estimator), que proporciona un conjunto de métricas más limitado, se basa en el simulador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="b4ce0-110">Invocación del simulador de seguimiento cuántico</span><span class="sxs-lookup"><span data-stu-id="b4ce0-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="b4ce0-111">Puede usar el simulador de seguimiento cuántico para ejecutar cualquier operación de Q#.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="b4ce0-112">Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `QCTraceSimulator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b4ce0-113">Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `QCTraceSimulator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b4ce0-114">Probabilidad de los resultados de una medición</span><span class="sxs-lookup"><span data-stu-id="b4ce0-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="b4ce0-115">Como el simulador de seguimiento cuántico no simula el estado cuántico real, no puede calcular la probabilidad de los resultados de una medición dentro de una operación.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="b4ce0-116">Por consiguiente, si una operación incluye mediciones, debe proporcionar explícitamente estas probabilidades con la operación <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> del espacio de nombres <xref:microsoft.quantum.diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="b4ce0-117">Esto se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4ce0-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="b4ce0-118">Si el simulador de seguimiento cuántico se encuentra con `AssertMeasurementProbability`, registrará que la medición de `PauliZ` en `source` y `q` dará un resultado de `Zero`, con una probabilidad de **0,5**.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="b4ce0-119">Más adelante, cuando ejecuta la operación `M`, busca los valores registrados de las probabilidades de resultado y `M` devuelve `Zero` o `One`, con una probabilidad de **0,5**.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="b4ce0-120">Si se ejecuta el mismo código en un simulador que realiza un seguimiento del estado cuántico, ese simulador comprueba que las probabilidades que se proporcionan en `AssertMeasurementProbability` sean correctas.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="b4ce0-121">Tenga en cuenta que si hay al menos una operación de medición que no se haya anotado mediante `AssertMeasurementProbability`, el simulador activará [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="b4ce0-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="b4ce0-122">Herramientas del simulador de seguimiento cuántico</span><span class="sxs-lookup"><span data-stu-id="b4ce0-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="b4ce0-123">El QDK incluye cinco herramientas que se pueden usar con el simulador de seguimiento cuántico para detectar errores en los programas y calcular los recursos de los programas cuánticos:</span><span class="sxs-lookup"><span data-stu-id="b4ce0-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="b4ce0-124">Herramienta</span><span class="sxs-lookup"><span data-stu-id="b4ce0-124">Tool</span></span> | <span data-ttu-id="b4ce0-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4ce0-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="b4ce0-126">Comprobador de entradas únicas</span><span class="sxs-lookup"><span data-stu-id="b4ce0-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="b4ce0-127">Comprueba posibles conflictos con los cúbits compartidos</span><span class="sxs-lookup"><span data-stu-id="b4ce0-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="b4ce0-128">Comprobador de uso de cúbits invalidado</span><span class="sxs-lookup"><span data-stu-id="b4ce0-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="b4ce0-129">Comprueba si el programa aplica una operación a un cúbit que ya se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="b4ce0-130">Contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="b4ce0-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="b4ce0-131">Cuenta el número de procesos primitivos utilizados por cada operación invocada en un programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-131">Counts the number of primitive processes used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="b4ce0-132">Contador de profundidad</span><span class="sxs-lookup"><span data-stu-id="b4ce0-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="b4ce0-133">Recopila recuentos que representan el límite inferior de la profundidad de cada operación invocada en un programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="b4ce0-134">Contador de ancho</span><span class="sxs-lookup"><span data-stu-id="b4ce0-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="b4ce0-135">Cuenta el número de cúbits asignados y prestados por cada operación en un programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="b4ce0-136">Para habilitar cada una de estas herramientas, hay que establecer las marcas correspondientes en `QCTraceSimulatorConfiguration` y, a continuación, pasar la configuración a la declaración de `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="b4ce0-137">Para más información sobre el uso de cada una de estas herramientas, consulte los vínculos de la lista anterior.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="b4ce0-138">Para más información sobre la configuración de `QCTraceSimulator`, consulte [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b4ce0-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="b4ce0-139">Métodos de QCTraceSimulator</span><span class="sxs-lookup"><span data-stu-id="b4ce0-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="b4ce0-140">`QCTraceSimulator` tiene varios métodos integrados para recuperar los valores de las métricas de las que se realiza un seguimiento durante una operación cuántica.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="b4ce0-141">Se pueden encontrar ejemplos de los métodos [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) y [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) en los artículos [Contador de operaciones primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) y [Contador de ancho](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="b4ce0-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="b4ce0-142">Para más información sobre todos los métodos disponibles, consulte [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) en la referencia de la API de Q#.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4ce0-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4ce0-143">See also</span></span>

- [<span data-ttu-id="b4ce0-144">Estimador de recursos cuánticos</span><span class="sxs-lookup"><span data-stu-id="b4ce0-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="b4ce0-145">Simulador cuántico de Toffoli</span><span class="sxs-lookup"><span data-stu-id="b4ce0-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="b4ce0-146">Simulador cuántico de estado completo</span><span class="sxs-lookup"><span data-stu-id="b4ce0-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 