---
title: Ancho del contador | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820375"
---
# <a name="width-counter"></a>Ancho (contador)

El `Width Counter` cuenta el número de qubits asignados y prestados por cada operación.
Todas las operaciones del espacio de nombres `Microsoft.Quantum.Intrinsic` se expresan en términos de rotaciones de qubit individuales, de T, de qubit Clifford, de CNOT y de qubit de Pauli. Algunas de las operaciones primitivas pueden asignar qubits adicionales. Por ejemplo, multiplique las puertas `X` controladas o las puertas de `T` controladas. Vamos a calcular el número de qubits adicionales asignados por la implementación de una puerta de `X` controlada por multiplicación:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Usar el contador de ancho C# en un programa

La multiplicación controlada `X` que actúe en un total de 5 qubits asignará 2 qubits auxiliares y el ancho de entrada será 5. Para comprobar que este es el caso, podemos usar el siguiente C# programa:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

La primera parte del programa ejecuta `ApplyMultiControlledX`. En la segunda parte usamos el método `QCTraceSimulator.GetMetric` para obtener el número de qubits asignados, así como el número de qubits que se han controlado `X` recibido como entrada. 

Por último, para generar todas las estadísticas recopiladas por el contador de ancho en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
