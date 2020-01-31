---
title: Contador de operaciones primitivas | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820426"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="15a66-103">Contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="15a66-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="15a66-104">El `Primitive Operations Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="15a66-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="15a66-105">Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="15a66-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="15a66-106">Todas las operaciones de `Microsoft.Quantum.Intrinsic` se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="15a66-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="15a66-107">Las estadísticas recopiladas se agregan a los bordes del gráfico de llamadas de operaciones.</span><span class="sxs-lookup"><span data-stu-id="15a66-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="15a66-108">Ahora, vamos a contar el número de puertas de `T` que se necesitan para implementar la operación de `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="15a66-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="15a66-109">Usar el contador de operaciones primitivas C# dentro de un programa</span><span class="sxs-lookup"><span data-stu-id="15a66-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="15a66-110">Para comprobar que `CCNOT` realmente requiere 7 `T` puertas y que `ApplySampleWithCCNOT` ejecuta 8 puertas `T`, podemos usar el código siguiente C# :</span><span class="sxs-lookup"><span data-stu-id="15a66-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="15a66-111">La primera parte del programa ejecuta `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="15a66-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="15a66-112">En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener el número de T puertas que ejecuta `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="15a66-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="15a66-113">Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas.</span><span class="sxs-lookup"><span data-stu-id="15a66-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="15a66-114">En la operación de ejemplo `Primitive.CCNOT` se llama en `ApplySampleWithCCNOT` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="15a66-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="15a66-115">Para obtener el número de puertas de `CNOT` utilizadas, podemos agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="15a66-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="15a66-116">Finalmente, para generar todas las estadísticas recopiladas por el contador de la puerta en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15a66-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="15a66-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="15a66-117">See also</span></span> ##

- <span data-ttu-id="15a66-118">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="15a66-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
