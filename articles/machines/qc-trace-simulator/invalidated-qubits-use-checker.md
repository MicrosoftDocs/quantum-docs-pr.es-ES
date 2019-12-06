---
title: Comprobador de uso de qubits invalidado | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863187"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="924bd-103">Comprobador de uso de qubits invalidado</span><span class="sxs-lookup"><span data-stu-id="924bd-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="924bd-104">El `Invalidated Qubits Use Checker` es una parte del equipo Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) diseñado para detectar posibles errores en el código.</span><span class="sxs-lookup"><span data-stu-id="924bd-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="924bd-105">Tenga en cuenta la siguiente parte del código de preguntas y respuestas para ilustrar los problemas detectados por el `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="924bd-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="924bd-106">Cuando se aplica `H` a `q[0]` apunta a un qubit ya liberado.</span><span class="sxs-lookup"><span data-stu-id="924bd-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="924bd-107">Esto puede producir un comportamiento indefinido.</span><span class="sxs-lookup"><span data-stu-id="924bd-107">This can cause undefined behavior.</span></span> <span data-ttu-id="924bd-108">Cuando la `Invalidated Qubits Use Checker` está habilitada, se producirá la `InvalidatedQubitsUseCheckerException` de excepción si se aplica una operación a un qubit ya liberado.</span><span class="sxs-lookup"><span data-stu-id="924bd-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="924bd-109">Consulte la documentación de la API en [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="924bd-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="924bd-110">Usar el comprobador de uso de qubits invalidado en el C# programa</span><span class="sxs-lookup"><span data-stu-id="924bd-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="924bd-111">El siguiente es un ejemplo de C# código de controlador para usar el equipo Quantum `Trace
Simulator` con el `Invalidated Qubits Use Checker` habilitado:</span><span class="sxs-lookup"><span data-stu-id="924bd-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="924bd-112">La clase `QCTraceSimulatorConfiguration` almacena la configuración del simulador de seguimiento de equipo Quantum y se puede proporcionar como argumento para el constructor `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="924bd-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="924bd-113">Cuando `useInvalidatedQubitsUseChecker` está establecido en true, el `Invalidated Qubits Use Checker` está habilitado.</span><span class="sxs-lookup"><span data-stu-id="924bd-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="924bd-114">Consulte la documentación de la API en [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) y [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="924bd-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="924bd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="924bd-115">See also</span></span> ##

- <span data-ttu-id="924bd-116">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="924bd-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
