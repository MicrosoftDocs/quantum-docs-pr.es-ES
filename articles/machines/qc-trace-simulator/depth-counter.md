---
title: Contador de profundidad | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184906"
---
# <a name="depth-counter"></a><span data-ttu-id="38582-103">Contador de profundidad</span><span class="sxs-lookup"><span data-stu-id="38582-103">Depth Counter</span></span>

<span data-ttu-id="38582-104">El `Depth Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="38582-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="38582-105">Se usa para recopilar recuentos de la profundidad de cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="38582-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="38582-106">Todas las operaciones de <xref:microsoft.quantum.intrinsic> se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="38582-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="38582-107">Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas mediante el `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="38582-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="38582-108">De forma predeterminada, todas las operaciones tienen la profundidad 0 excepto la puerta T que tiene la profundidad 1.</span><span class="sxs-lookup"><span data-stu-id="38582-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="38582-109">Esto significa que, de forma predeterminada, solo se calcula la profundidad T de las operaciones (lo que suele ser deseable).</span><span class="sxs-lookup"><span data-stu-id="38582-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="38582-110">Las estadísticas recopiladas se agregan a todos los bordes del gráfico de llamadas de operaciones.</span><span class="sxs-lookup"><span data-stu-id="38582-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="38582-111">Ahora, vamos a calcular la profundidad <xref:microsoft.quantum.intrinsic.t> de la operación de <xref:microsoft.quantum.intrinsic.ccnot>.</span><span class="sxs-lookup"><span data-stu-id="38582-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="38582-112">Usaremos el siguiente código de controlador de Q #:</span><span class="sxs-lookup"><span data-stu-id="38582-112">We will use the following Q# driver code:</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="38582-113">Usar el contador de profundidad C# dentro de un programa</span><span class="sxs-lookup"><span data-stu-id="38582-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="38582-114">Para comprobar que `CCNOT` tiene `T` profundidad 5 y `CCNOTDriver` tiene `T` profundidad 6, podemos usar el código C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="38582-114">To check that `CCNOT` has `T` depth 5 and `CCNOTDriver` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="38582-115">La primera parte del programa ejecuta `CCNOTDriver`.</span><span class="sxs-lookup"><span data-stu-id="38582-115">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="38582-116">En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener la profundidad `T` de `CCNOT` y `CCNOTDriver`:</span><span class="sxs-lookup"><span data-stu-id="38582-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `CCNOTDriver`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="38582-117">Por último, para generar todas las estadísticas recopiladas por `Depth Counter` en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38582-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="38582-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="38582-118">See also</span></span> ##

- <span data-ttu-id="38582-119">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="38582-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>