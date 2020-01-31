---
title: Contador de profundidad | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820477"
---
# <a name="depth-counter"></a><span data-ttu-id="2acef-103">Contador de profundidad</span><span class="sxs-lookup"><span data-stu-id="2acef-103">Depth Counter</span></span>

<span data-ttu-id="2acef-104">El `Depth Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="2acef-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="2acef-105">Se usa para recopilar recuentos de la profundidad de cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="2acef-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="2acef-106">Todas las operaciones de <xref:microsoft.quantum.intrinsic> se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="2acef-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="2acef-107">Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas mediante el `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="2acef-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="2acef-108">De forma predeterminada, todas las operaciones tienen la profundidad 0 excepto la puerta T que tiene la profundidad 1.</span><span class="sxs-lookup"><span data-stu-id="2acef-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="2acef-109">Esto significa que, de forma predeterminada, solo se calcula la profundidad T de las operaciones (lo que suele ser deseable).</span><span class="sxs-lookup"><span data-stu-id="2acef-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="2acef-110">Las estadísticas recopiladas se agregan a todos los bordes del gráfico de llamadas de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2acef-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="2acef-111">Ahora, vamos a calcular la profundidad <xref:microsoft.quantum.intrinsic.t> de la operación de <xref:microsoft.quantum.intrinsic.ccnot>.</span><span class="sxs-lookup"><span data-stu-id="2acef-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="2acef-112">Usaremos el siguiente código de ejemplo de Q #:</span><span class="sxs-lookup"><span data-stu-id="2acef-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="2acef-113">Usar el contador de profundidad C# dentro de un programa</span><span class="sxs-lookup"><span data-stu-id="2acef-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="2acef-114">Para comprobar que `CCNOT` tiene `T` profundidad 5 y `ApplySampleWithCCNOT` tiene `T` profundidad 6, podemos usar el código C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="2acef-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="2acef-115">La primera parte del programa ejecuta `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="2acef-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="2acef-116">En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener la profundidad `T` de `CCNOT` y `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="2acef-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="2acef-117">Por último, para generar todas las estadísticas recopiladas por `Depth Counter` en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2acef-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="2acef-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2acef-118">See also</span></span> ##

- <span data-ttu-id="2acef-119">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="2acef-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
