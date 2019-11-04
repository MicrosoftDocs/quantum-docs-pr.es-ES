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
# <a name="depth-counter"></a>Contador de profundidad

El `Depth Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum.
Se usa para recopilar recuentos de la profundidad de cada operación invocada en un programa Quantum. Todas las operaciones de <xref:microsoft.quantum.intrinsic> se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables. Los usuarios pueden establecer la profundidad de cada una de las operaciones primitivas mediante el `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

De forma predeterminada, todas las operaciones tienen la profundidad 0 excepto la puerta T que tiene la profundidad 1. Esto significa que, de forma predeterminada, solo se calcula la profundidad T de las operaciones (lo que suele ser deseable). Las estadísticas recopiladas se agregan a todos los bordes del gráfico de llamadas de operaciones. 

Ahora, vamos a calcular la profundidad <xref:microsoft.quantum.intrinsic.t> de la operación de <xref:microsoft.quantum.intrinsic.ccnot>. Usaremos el siguiente código de controlador de Q #: 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Usar el contador de profundidad C# dentro de un programa

Para comprobar que `CCNOT` tiene `T` profundidad 5 y `CCNOTDriver` tiene `T` profundidad 6, podemos usar el código C# siguiente:

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

La primera parte del programa ejecuta `CCNOTDriver`. En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener la profundidad `T` de `CCNOT` y `CCNOTDriver`: 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Por último, para generar todas las estadísticas recopiladas por `Depth Counter` en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
