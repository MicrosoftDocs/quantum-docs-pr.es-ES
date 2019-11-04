---
title: Simulador de seguimiento de equipos cuánticos | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035138"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="4d706-103">Simulador de seguimiento de equipos cuánticos</span><span class="sxs-lookup"><span data-stu-id="4d706-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="4d706-104">El simulador de seguimiento de equipos cuánticos de Microsoft ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="4d706-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="4d706-105">Por esta razón, el simulador de seguimiento puede ejecutar programas cuánticos que usan miles de qubits.</span><span class="sxs-lookup"><span data-stu-id="4d706-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="4d706-106">Esto tiene dos propósitos principales:</span><span class="sxs-lookup"><span data-stu-id="4d706-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="4d706-107">Depurar código clásico que forma parte de un programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="4d706-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="4d706-108">Calcular los recursos necesarios para ejecutar una determinada instancia de un programa cuántico en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="4d706-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="4d706-109">El simulador de seguimiento se basa en la información adicional que proporciona el usuario cuando se deben realizar medidas.</span><span class="sxs-lookup"><span data-stu-id="4d706-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="4d706-110">Consulte la sección [Proporcionar la probabilidad de los resultados de medidas](#providing-the-probability-of-measurement-outcomes) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="4d706-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="4d706-111">Proporcionar la probabilidad de los resultados de medidas</span><span class="sxs-lookup"><span data-stu-id="4d706-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="4d706-112">Hay dos tipos de medidas que aparecen en los algoritmos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="4d706-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="4d706-113">El primer tipo juega un papel auxiliar en el que el usuario normalmente conoce la probabilidad de los resultados.</span><span class="sxs-lookup"><span data-stu-id="4d706-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="4d706-114">En este caso, el usuario puede escribir <xref:microsoft.quantum.primitive.assertprob> en el espacio de nombres <xref:microsoft.quantum.primitive> para expresar este conocimiento.</span><span class="sxs-lookup"><span data-stu-id="4d706-114">In this case the user can write <xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace to express this knowledge.</span></span> <span data-ttu-id="4d706-115">Esto se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d706-115">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="4d706-116">Si el simulador de seguimiento ejecuta `AssertProb`, este registrará que a la medida `PauliZ` en `source` y `ancilla` se le debe dar un resultado de `Zero` con una probabilidad de 0,5.</span><span class="sxs-lookup"><span data-stu-id="4d706-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="4d706-117">Si el simulador ejecuta `M` posteriormente, encontrará los valores registrados de las probabilidades de resultados y `M` devolverá `Zero` o `One` con una probabilidad de 0,5.</span><span class="sxs-lookup"><span data-stu-id="4d706-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="4d706-118">Si se ejecuta el mismo código en un simulador que realiza un seguimiento del estado cuántico, ese simulador comprobará que las probabilidades que se proporcionan en `AssertProb` son correctas.</span><span class="sxs-lookup"><span data-stu-id="4d706-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="4d706-119">Ejecución del programa con el simulador de seguimiento de equipos cuánticos</span><span class="sxs-lookup"><span data-stu-id="4d706-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="4d706-120">El simulador de seguimiento de equipos cuánticos se puede considerar simplemente como otra máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="4d706-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="4d706-121">El programa del controlador de C# para usarlo es muy similar al de cualquier otro simulador cuántico:</span><span class="sxs-lookup"><span data-stu-id="4d706-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="4d706-122">Tenga en cuenta que si hay alguna medida que no se haya anotado mediante `AssertProb`, el simulador devolverá `UnconstrainedMeasurementException` desde el espacio de nombres `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="4d706-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="4d706-123">Consulte la documentación de la API sobre [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) para más información.</span><span class="sxs-lookup"><span data-stu-id="4d706-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="4d706-124">Además de ejecutar programas cuánticos, el simulador de seguimiento incluye cinco componentes para detectar errores en los programas y realizar cálculos sobre los recursos que necesitan los programas cuánticos.</span><span class="sxs-lookup"><span data-stu-id="4d706-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="4d706-125">Comprobador de entradas únicas</span><span class="sxs-lookup"><span data-stu-id="4d706-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="4d706-126">Comprobador de uso de qubits invalidado</span><span class="sxs-lookup"><span data-stu-id="4d706-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="4d706-127">Contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="4d706-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="4d706-128">Contador de profundidad del circuito</span><span class="sxs-lookup"><span data-stu-id="4d706-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="4d706-129">Contador de anchura del circuito</span><span class="sxs-lookup"><span data-stu-id="4d706-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="4d706-130">Cada uno de estos componentes se puede habilitar mediante el establecimiento de las marcas adecuadas en `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="4d706-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="4d706-131">Se puede encontrar más información sobre cada uno de estos componentes en los archivos de referencia correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4d706-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="4d706-132">Consulte la documentación de la API sobre [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obtener detalles más específicos.</span><span class="sxs-lookup"><span data-stu-id="4d706-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d706-133">Otras referencias</span><span class="sxs-lookup"><span data-stu-id="4d706-133">See also</span></span>
<span data-ttu-id="4d706-134">Referencia de C# sobre el [simulador de seguimiento](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) de equipos cuánticos</span><span class="sxs-lookup"><span data-stu-id="4d706-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

