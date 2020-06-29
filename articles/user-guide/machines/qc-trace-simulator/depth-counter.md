---
title: Contador de profundidad
description: Obtenga información sobre el contador de profundidad de QDK de Microsoft, que recopila recuentos de la profundidad de cada operación invocada en un programa Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415275"
---
# <a name="depth-counter"></a>Contador de profundidad

La `Depth Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum.
Se utiliza para recopilar recuentos que representan el límite inferior de la profundidad de cada operación invocada en un programa Quantum. Todas las operaciones de <xref:microsoft.quantum.intrinsic> se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli. Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas a través del `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

De forma predeterminada, todas las operaciones tienen la profundidad 0 excepto la puerta T que tiene la profundidad 1. Esto significa que, de forma predeterminada, solo se calcula la profundidad T de las operaciones (lo que suele ser deseable). Las estadísticas recopiladas se agregan a todos los bordes del gráfico de llamadas de operaciones. 

Ahora, vamos a calcular la <xref:microsoft.quantum.intrinsic.t> profundidad de la <xref:microsoft.quantum.intrinsic.ccnot> operación. Usaremos el siguiente código de ejemplo de Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Usar el contador de profundidad en un programa de C#

Para comprobar que `CCNOT` tiene `T` la profundidad 5 y `ApplySampleWithCCNOT` tiene `T` la profundidad 6, podemos usar el siguiente código de C#:

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

Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` . En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener la `T` profundidad de `CCNOT` y `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Por último, para generar todas las estadísticas recopiladas por `Depth Counter` en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Consulte también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
