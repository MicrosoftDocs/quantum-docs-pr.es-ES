---
title: 'Contador de profundidad: kit de desarrollo de Quantum'
description: Obtenga información sobre el contador de profundidad de QDK de Microsoft, que usa el simulador de seguimiento de Quantum para recopilar recuentos de la profundidad de cada operación invocada en un Q# programa.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c54f6fc479203d30c68c4958329605d4323f9ea
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868328"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="1db08-103">Simulador de seguimiento de Quantum: contador de profundidad</span><span class="sxs-lookup"><span data-stu-id="1db08-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="1db08-104">El contador de profundidad es una parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="1db08-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="1db08-105">Puede utilizarlo para recopilar recuentos que representan el límite inferior de la profundidad de cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="1db08-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="1db08-106">Valores de profundidad</span><span class="sxs-lookup"><span data-stu-id="1db08-106">Depth values</span></span>

<span data-ttu-id="1db08-107">De forma predeterminada, todas las operaciones tienen una profundidad de **0** excepto la `T` operación, que tiene una profundidad de **1**.</span><span class="sxs-lookup"><span data-stu-id="1db08-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="1db08-108">Esto significa que, de forma predeterminada, solo `T` se calcula la profundidad de las operaciones (lo que suele ser deseable).</span><span class="sxs-lookup"><span data-stu-id="1db08-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="1db08-109">El contador de profundidad agrega y recopila estadísticas sobre todos los bordes del [gráfico de llamadas](https://en.wikipedia.org/wiki/Call_graph)de la operación.</span><span class="sxs-lookup"><span data-stu-id="1db08-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="1db08-110">Todas <xref:microsoft.quantum.intrinsic> las operaciones se expresan en términos de rotaciones de un solo qubit, <xref:microsoft.quantum.intrinsic.t> operaciones, operaciones de Clifford de qubit único, <xref:microsoft.quantum.intrinsic.cnot> operaciones y medidas de Pauli observables de qubit.</span><span class="sxs-lookup"><span data-stu-id="1db08-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="1db08-111">Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas a través del `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="1db08-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="1db08-112">Invocar el contador de profundidad</span><span class="sxs-lookup"><span data-stu-id="1db08-112">Invoking the depth counter</span></span>

<span data-ttu-id="1db08-113">Para ejecutar el simulador de seguimiento de Quantum con el contador de profundidad, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer su `UseDepthCounter` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="1db08-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="1db08-114">Usar el contador de profundidad en un programa host de C#</span><span class="sxs-lookup"><span data-stu-id="1db08-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="1db08-115">En el ejemplo de C# que se muestra a continuación en esta sección se calcula la `T` profundidad de la `CCNOT` operación, basándose en el Q# código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1db08-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="1db08-116">Para comprobar que `CCNOT` tiene `T` la profundidad **5** y `ApplySampleWithCCNOT` tiene `T` la profundidad **6**, use el siguiente código de C#:</span><span class="sxs-lookup"><span data-stu-id="1db08-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="1db08-117">Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="1db08-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="1db08-118">La segunda parte usa el [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar la `T` profundidad de `CCNOT` y `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="1db08-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="1db08-119">Por último, puede generar todas las estadísticas recopiladas por el contador de profundidad en formato CSV con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1db08-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="1db08-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1db08-120">See also</span></span>

- <span data-ttu-id="1db08-121">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="1db08-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="1db08-122">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="1db08-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="1db08-123">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="1db08-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="1db08-124">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API.</span><span class="sxs-lookup"><span data-stu-id="1db08-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
