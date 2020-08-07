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
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Simulador de seguimiento de Quantum: contador de operaciones primitivas

El contador de operaciones primitivas forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum. Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum. 

Todas <xref:microsoft.quantum.intrinsic> las operaciones se expresan en términos de rotaciones de un solo qubit, operaciones T, operaciones Clifford de un solo qubit, operaciones CNOT y medidas de qubit Pauli observables. El contador de operaciones primitiva agrega y recopila estadísticas sobre todos los bordes del [gráfico de llamadas](https://en.wikipedia.org/wiki/Call_graph)de la operación.

## <a name="invoking-the-primitive-operation-counter"></a>Invocar el contador de operación primitivo

Para ejecutar el simulador de seguimiento de Quantum con el contador de operaciones primitivas, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UsePrimitiveOperationsCounter` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Usar el contador de operaciones primitivas en un programa host de C#

En el ejemplo de C# que se muestra en esta sección se cuenta el número de <xref:microsoft.quantum.intrinsic.t> operaciones necesarias para implementar la <xref:microsoft.quantum.intrinsic.ccnot> operación, basándose en el Q# código de ejemplo siguiente:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Para comprobar que `CCNOT` requiere siete `T` operaciones y que `ApplySampleWithCCNOT` ejecuta ocho `T` operaciones, use el siguiente código de C#:

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

Se ejecuta la primera parte del programa `ApplySampleWithCCNOT` . La segunda parte usa el [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar el número de `T` operaciones que ejecuta `ApplySampleWithCCNOT` : 

Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas. En el ejemplo anterior, el programa llama a la `Primitive.CCNOT` operación dentro de `ApplySampleWithCCNOT` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Para recuperar el número de `CNOT` operaciones utilizadas, agregue la siguiente línea:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Por último, puede generar todas las estadísticas recopiladas por el contador de operaciones primitivas en formato CSV con lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vea también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API.