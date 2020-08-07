---
title: 'Comprobador de uso de qubits invalidado: kit de desarrollo de Quantum'
description: Obtenga información sobre el comprobador de uso invalidado de qubits de Microsoft QDK, que usa el simulador de seguimiento de Quantum para comprobar el Q# código en busca de qubits no válidos.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868294"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="f7245-103">Simulador de seguimiento de Quantum: Comprobador de uso de qubits invalidado</span><span class="sxs-lookup"><span data-stu-id="f7245-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="f7245-104">El comprobador de uso de qubits invalidado forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f7245-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="f7245-105">Puede usarlo para detectar posibles errores en el código causado por qubits no válidos.</span><span class="sxs-lookup"><span data-stu-id="f7245-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="f7245-106">Qubits no válido</span><span class="sxs-lookup"><span data-stu-id="f7245-106">Invalid qubits</span></span>

<span data-ttu-id="f7245-107">Considere el siguiente fragmento de Q# código para ilustrar los problemas detectados por el comprobador de uso de qubits invalidado:</span><span class="sxs-lookup"><span data-stu-id="f7245-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="f7245-108">Cuando se aplica la `H` operación a `q[0]` , apunta a un qubit ya liberado, lo que puede provocar un comportamiento indefinido.</span><span class="sxs-lookup"><span data-stu-id="f7245-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="f7245-109">Cuando el comprobador de uso de qubits invalidado está habilitado, produce la excepción `InvalidatedQubitsUseCheckerException` si el programa aplica una operación a un qubit ya liberado.</span><span class="sxs-lookup"><span data-stu-id="f7245-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="f7245-110">Para obtener más información, vea <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="f7245-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="f7245-111">Invocar el comprobador de uso de qubits invalidado</span><span class="sxs-lookup"><span data-stu-id="f7245-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="f7245-112">Para ejecutar el simulador de seguimiento de Quantum con el comprobador de uso de qubits invalidado, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseInvalidatedQubitsUseChecker` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="f7245-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="f7245-113">Usar el comprobador de uso de qubits invalidado en un programa host de C#</span><span class="sxs-lookup"><span data-stu-id="f7245-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="f7245-114">A continuación se proporciona un ejemplo de programas host de C# que usan el simulador de seguimiento de Quantum con el comprobador de uso de qubits invalidado habilitado:</span><span class="sxs-lookup"><span data-stu-id="f7245-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f7245-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7245-115">See also</span></span>

- <span data-ttu-id="f7245-116">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f7245-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="f7245-117">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="f7245-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="f7245-118">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="f7245-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="f7245-119">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API.</span><span class="sxs-lookup"><span data-stu-id="f7245-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>