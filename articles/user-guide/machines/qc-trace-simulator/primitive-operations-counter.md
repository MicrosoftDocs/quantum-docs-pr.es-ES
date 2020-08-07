---
title: 'Contador de operación primitiva: kit de desarrollo de Quantum'
description: Obtenga información sobre el contador de operaciones primitivas de Microsoft QDK, que usa el simulador de seguimiento Quantum para realizar el seguimiento de las ejecuciones primitivas utilizadas por las operaciones en un Q# programa.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868243"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="3f417-103">Simulador de seguimiento de Quantum: contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="3f417-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="3f417-104">El contador de operaciones primitivas forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="3f417-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="3f417-105">Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="3f417-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="3f417-106">Todas <xref:microsoft.quantum.intrinsic> las operaciones se expresan en términos de rotaciones de un solo qubit, operaciones T, operaciones Clifford de un solo qubit, operaciones CNOT y medidas de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="3f417-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="3f417-107">El contador de operaciones primitiva agrega y recopila estadísticas sobre todos los bordes del [gráfico de llamadas](https://en.wikipedia.org/wiki/Call_graph)de la operación.</span><span class="sxs-lookup"><span data-stu-id="3f417-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="3f417-108">Invocar el contador de operación primitivo</span><span class="sxs-lookup"><span data-stu-id="3f417-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="3f417-109">Para ejecutar el simulador de seguimiento de Quantum con el contador de operaciones primitivas, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UsePrimitiveOperationsCounter` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="3f417-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="3f417-110">Usar el contador de operaciones primitivas en un programa host de C#</span><span class="sxs-lookup"><span data-stu-id="3f417-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="3f417-111">En el ejemplo de C# que se muestra en esta sección se cuenta el número de <xref:microsoft.quantum.intrinsic.t> operaciones necesarias para implementar la <xref:microsoft.quantum.intrinsic.ccnot> operación, basándose en el Q# código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f417-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="3f417-112">Para comprobar que `CCNOT` requiere siete `T` operaciones y que `ApplySampleWithCCNOT` ejecuta ocho `T` operaciones, use el siguiente código de C#:</span><span class="sxs-lookup"><span data-stu-id="3f417-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="3f417-113">Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="3f417-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="3f417-114">La segunda parte usa el [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar el número de `T` operaciones que ejecuta `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="3f417-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="3f417-115">Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3f417-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="3f417-116">En el ejemplo anterior, el programa llama a la `Primitive.CCNOT` operación dentro de `ApplySampleWithCCNOT` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="3f417-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="3f417-117">Para recuperar el número de `CNOT` operaciones utilizadas, agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="3f417-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="3f417-118">Por último, puede generar todas las estadísticas recopiladas por el contador de operaciones primitivas en formato CSV con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f417-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="3f417-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f417-119">See also</span></span>

- <span data-ttu-id="3f417-120">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="3f417-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="3f417-121">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="3f417-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="3f417-122">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="3f417-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="3f417-123">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API.</span><span class="sxs-lookup"><span data-stu-id="3f417-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>