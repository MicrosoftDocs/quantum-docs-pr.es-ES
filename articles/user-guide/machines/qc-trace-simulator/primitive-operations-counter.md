---
title: Contador de operaciones primitivas
description: Obtenga información sobre el contador de operaciones primitivas de Microsoft QDK, que realiza un seguimiento del número de ejecuciones primitivas usadas por las operaciones en un programa Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275554"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="c30c0-103">Contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="c30c0-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="c30c0-104">La `Primitive Operations Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="c30c0-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c30c0-105">Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="c30c0-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="c30c0-106">Todas las operaciones de `Microsoft.Quantum.Intrinsic` se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="c30c0-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="c30c0-107">Las estadísticas recopiladas se agregan a los bordes del gráfico de llamadas de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c30c0-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="c30c0-108">Ahora, vamos `T` a contar el número de puertas necesarias para implementar la `CCNOT` operación.</span><span class="sxs-lookup"><span data-stu-id="c30c0-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="c30c0-109">Usar el contador de operaciones primitivas en un programa de C#</span><span class="sxs-lookup"><span data-stu-id="c30c0-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="c30c0-110">Para comprobar que `CCNOT` realmente requiere 7 `T` puertas y que `ApplySampleWithCCNOT` ejecuta 8 `T` puertas, podemos usar el siguiente código de C#:</span><span class="sxs-lookup"><span data-stu-id="c30c0-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="c30c0-111">Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="c30c0-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="c30c0-112">En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener el número de T puertas ejecutadas por `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="c30c0-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="c30c0-113">Cuando `GetMetric` se llama a con dos parámetros de tipo, devuelve el valor de la métrica asociada a un borde de gráfico de llamadas determinado.</span><span class="sxs-lookup"><span data-stu-id="c30c0-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="c30c0-114">En la operación de ejemplo `Primitive.CCNOT` se llama a dentro de `ApplySampleWithCCNOT` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="c30c0-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="c30c0-115">Para obtener el número de `CNOT` puertas usadas, podemos agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="c30c0-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="c30c0-116">Finalmente, para generar todas las estadísticas recopiladas por el contador de la puerta en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c30c0-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="c30c0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c30c0-117">See also</span></span> ##

- <span data-ttu-id="c30c0-118">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="c30c0-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
