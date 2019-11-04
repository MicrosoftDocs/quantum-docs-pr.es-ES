---
title: Contador de operaciones primitivas | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184889"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="e2082-103">Contador de operaciones primitivas</span><span class="sxs-lookup"><span data-stu-id="e2082-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="e2082-104">El `Primitive Operations Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="e2082-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="e2082-105">Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="e2082-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="e2082-106">Todas las operaciones de `Microsoft.Quantum.Primitive` se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="e2082-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="e2082-107">Las estadísticas recopiladas se agregan a los bordes del gráfico de llamadas de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e2082-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="e2082-108">Ahora, vamos a contar el número de puertas de `T` que se necesitan para implementar la operación de `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="e2082-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="e2082-109">Usar el contador de operaciones primitivas C# dentro de un programa</span><span class="sxs-lookup"><span data-stu-id="e2082-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="e2082-110">Para comprobar que `CCNOT` realmente requiere 7 `T` puertas y que `CCNOTDriver` ejecuta 8 puertas `T`, podemos usar el código siguiente C# :</span><span class="sxs-lookup"><span data-stu-id="e2082-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="e2082-111">La primera parte del programa ejecuta `CCNOTDriver`.</span><span class="sxs-lookup"><span data-stu-id="e2082-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="e2082-112">En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener el número de T puertas que ejecuta `CCNOTDriver`:</span><span class="sxs-lookup"><span data-stu-id="e2082-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="e2082-113">Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e2082-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="e2082-114">En la operación de ejemplo `Primitive.CCNOT` se llama en `CCNOTDriver` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT,CCNOTDriver>`.</span><span class="sxs-lookup"><span data-stu-id="e2082-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="e2082-115">Para obtener el número de puertas de `CNOT` utilizadas, podemos agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="e2082-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="e2082-116">Finalmente, para generar todas las estadísticas recopiladas por el contador de la puerta en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2082-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="e2082-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2082-117">See also</span></span> ##

- <span data-ttu-id="e2082-118">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="e2082-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
