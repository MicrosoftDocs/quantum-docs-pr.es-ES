---
title: Comprobador de entradas DISTINCT | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 0df28f6d74279db4678c3485a23a9341680eec52
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184702"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="6d1df-103">Comprobador de entradas DISTINCT</span><span class="sxs-lookup"><span data-stu-id="6d1df-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="6d1df-104">El `Distinct Inputs Checker` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="6d1df-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6d1df-105">Está diseñado para detectar posibles errores en el código.</span><span class="sxs-lookup"><span data-stu-id="6d1df-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="6d1df-106">Tenga en cuenta la siguiente parte del código de preguntas y respuestas para ilustrar los problemas detectados por este paquete:</span><span class="sxs-lookup"><span data-stu-id="6d1df-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="6d1df-107">Cuando el usuario examina este programa, se da por hecho que el orden en el que se llama a `op1` y `op2` no importa porque `q1` y `q2` son qubits diferentes y las operaciones que actúan en diferentes qubits de desactivación.</span><span class="sxs-lookup"><span data-stu-id="6d1df-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="6d1df-108">Ahora veamos un ejemplo en el que se usa esta operación:</span><span class="sxs-lookup"><span data-stu-id="6d1df-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation DisctinctQubitCaptured2Test () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

<span data-ttu-id="6d1df-109">Ahora `op1` y `op2` se obtienen mediante la aplicación parcial y comparten un qubit.</span><span class="sxs-lookup"><span data-stu-id="6d1df-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="6d1df-110">Cuando el usuario llama `DoBoth` en el ejemplo anterior, el resultado de la operación dependerá del orden de `op1` y `op2` dentro de `DoBoth`.</span><span class="sxs-lookup"><span data-stu-id="6d1df-110">When the user calls `DoBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `DoBoth`.</span></span> <span data-ttu-id="6d1df-111">Esto no es lo que el usuario esperaría que ocurriera.</span><span class="sxs-lookup"><span data-stu-id="6d1df-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="6d1df-112">El `Distinct Inputs Checker` detectará tales situaciones cuando se habilite y iniciará `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="6d1df-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="6d1df-113">Consulte la documentación de la API en [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6d1df-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="6d1df-114">Usar el comprobador de entradas C# DISTINCT en el programa</span><span class="sxs-lookup"><span data-stu-id="6d1df-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="6d1df-115">A continuación se proporciona un ejemplo C# de código de controlador para usar el simulador de seguimiento de equipo Quantum con el `Distinct Inputs Checker` habilitado:</span><span class="sxs-lookup"><span data-stu-id="6d1df-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="6d1df-116">La clase `QCTraceSimulatorConfiguration` almacena la configuración del simulador de seguimiento de equipo Quantum y se puede proporcionar como argumento para el constructor `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="6d1df-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="6d1df-117">Cuando `useDistinctInputsChecker` está establecido en true, el `Distinct Inputs Checker` está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6d1df-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="6d1df-118">Consulte la documentación de la API en [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) y [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6d1df-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d1df-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d1df-119">See also</span></span>

- <span data-ttu-id="6d1df-120">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="6d1df-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
