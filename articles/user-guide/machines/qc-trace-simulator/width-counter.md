---
title: 'Contador de ancho: kit de desarrollo de Quantum'
description: Obtenga información sobre el contador de ancho de QDK de Microsoft, que usa el simulador de seguimiento de Quantum para contar el número de operaciones de qubits asignadas y prestadas por el Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835951"
---
# <a name="quantum-trace-simulator-width-counter"></a>Simulador de seguimiento de Quantum: contador de ancho

El contador de ancho forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum. Puede usarlo para contar el número de qubits asignados y prestados por cada operación en un Q# programa. Algunas operaciones primitivas pueden asignar qubits adicionales, por ejemplo, las operaciones controladas de multiplicación `X` o `T` las operaciones controladas.

## <a name="invoking-the-width-counter"></a>Invocar el contador de ancho

Para ejecutar el simulador de seguimiento de Quantum con el contador de ancho, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseWidthCounter` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Usar el contador de ancho en un programa host de C#

En el ejemplo de C# que se muestra a continuación en esta sección se calcula el número de qubits adicionales asignados por la implementación de una operación controlada multiplicación <xref:microsoft.quantum.intrinsic.x> , basándose en el Q# código de ejemplo siguiente:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

La operación de multiplicación controlada <xref:microsoft.quantum.intrinsic.x> actúa en un total de cinco qubits, asigna dos [qubits auxiliares](xref:microsoft.quantum.glossary#ancilla)y tiene un ancho de entrada de **5**. Use el siguiente programa de C# para comprobar los recuentos:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

La primera parte del programa ejecuta la `ApplyMultiControlledX` operación. La segunda parte usa el [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar el número de qubits asignados, así como el número de qubits que la `Controlled X` operación recibió como entrada. 

Por último, puede generar todas las estadísticas recopiladas por el contador de ancho en formato CSV con lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vea también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API.
