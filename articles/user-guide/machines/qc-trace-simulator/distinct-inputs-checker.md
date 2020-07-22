---
title: 'Comprobador de entradas DISTINCT: kit de desarrollo de Quantum'
description: Obtenga información sobre el comprobador de entradas distintas de Microsoft QDK, que usa el simulador de seguimiento de Quantum para comprobar el código de preguntas y respuestas potenciales con qubits compartidas.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871151"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="81991-103">Simulador de seguimiento de Quantum: Comprobador de entradas distintas</span><span class="sxs-lookup"><span data-stu-id="81991-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="81991-104">El comprobador de entradas DISTINCT es una parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="81991-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="81991-105">Puede usarlo para detectar posibles errores en el código causados por conflictos con qubits compartidos.</span><span class="sxs-lookup"><span data-stu-id="81991-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="81991-106">Conflictos con qubits compartidos</span><span class="sxs-lookup"><span data-stu-id="81991-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="81991-107">Considere el siguiente fragmento de código de preguntas y respuestas para ilustrar los problemas detectados por el comprobador de entradas distintivo:</span><span class="sxs-lookup"><span data-stu-id="81991-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="81991-108">Al examinar este programa, puede suponer que el orden en el que llama a `op1` y no `op2` importa, ya que `q1` y `q2` son diferentes qubits y operaciones que actúan en diferentes desactivaciones de qubits.</span><span class="sxs-lookup"><span data-stu-id="81991-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="81991-109">Ahora, considere este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="81991-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="81991-110">Tenga en cuenta que `op1` y `op2` se obtienen mediante la aplicación parcial y comparten un qubit.</span><span class="sxs-lookup"><span data-stu-id="81991-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="81991-111">Cuando se llama a `ApplyBoth` en este ejemplo, el resultado de la operación depende del orden de `op1` y `op2` dentro `ApplyBoth` de lo que se espera que suceda.</span><span class="sxs-lookup"><span data-stu-id="81991-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="81991-112">Al habilitar el comprobador de entradas DISTINCT, detecta esas situaciones y produce una excepción `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="81991-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="81991-113">Para obtener más información, consulte <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> en la biblioteca de la API de Q #.</span><span class="sxs-lookup"><span data-stu-id="81991-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="81991-114">Invocar el comprobador de entradas DISTINCT</span><span class="sxs-lookup"><span data-stu-id="81991-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="81991-115">Para ejecutar el simulador de seguimiento de Quantum con el comprobador de entradas DISTINCT, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseDistinctInputsChecker` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="81991-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="81991-116">Usar el comprobador de entradas DISTINCT en un programa host de C#</span><span class="sxs-lookup"><span data-stu-id="81991-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="81991-117">A continuación se proporciona un ejemplo de un programa host de C# que usa el simulador de seguimiento de Quantum con el comprobador de entradas distintivos habilitado:</span><span class="sxs-lookup"><span data-stu-id="81991-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="81991-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="81991-118">See also</span></span>

- <span data-ttu-id="81991-119">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="81991-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="81991-120">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="81991-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="81991-121">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="81991-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="81991-122">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API.</span><span class="sxs-lookup"><span data-stu-id="81991-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
