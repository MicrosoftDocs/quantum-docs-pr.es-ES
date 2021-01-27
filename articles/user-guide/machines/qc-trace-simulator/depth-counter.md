---
title: 'Contador de profundidad: kit de desarrollo de Quantum'
description: Obtenga información sobre el contador de profundidad de QDK de Microsoft, que usa el simulador de seguimiento de Quantum para recopilar recuentos de la profundidad de cada operación invocada en un Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859046"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Simulador de seguimiento de Quantum: contador de profundidad

El contador de profundidad es una parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum.
Puede utilizarlo para recopilar recuentos que representan el límite inferior de la profundidad de cada operación invocada en un programa Quantum. 

## <a name="depth-values"></a>Valores de profundidad

De forma predeterminada, todas las operaciones tienen una profundidad de **0** excepto la `T` operación, que tiene una profundidad de **1**. Esto significa que, de forma predeterminada, solo `T` se calcula la profundidad de las operaciones (lo que suele ser deseable). El contador de profundidad agrega y recopila estadísticas sobre todos los bordes del [gráfico de llamadas](https://en.wikipedia.org/wiki/Call_graph)de la operación.

Todas <xref:Microsoft.Quantum.Intrinsic> las operaciones se expresan en términos de rotaciones de un solo qubit, <xref:Microsoft.Quantum.Intrinsic.T> operaciones, operaciones de Clifford de qubit único, <xref:Microsoft.Quantum.Intrinsic.CNOT> operaciones y medidas de Pauli observables de qubit. Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas a través del `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Invocar el contador de profundidad

Para ejecutar el simulador de seguimiento de Quantum con el contador de profundidad, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer su `UseDepthCounter` propiedad en **true** y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Usar el contador de profundidad en un programa host de C#

En el ejemplo de C# que se muestra a continuación en esta sección se calcula la `T` profundidad de la `CCNOT` operación, basándose en el Q# código de ejemplo siguiente:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Para comprobar que `CCNOT` tiene `T` la profundidad **5** y `ApplySampleWithCCNOT` tiene `T` la profundidad **6**, use el siguiente código de C#:

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

Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` . La segunda parte usa el [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar la `T` profundidad de `CCNOT` y `ApplySampleWithCCNOT` . 

Por último, puede generar todas las estadísticas recopiladas por el contador de profundidad en formato CSV con lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Consulte también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API.
