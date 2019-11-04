---
title: Ancho del contador | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442406"
---
# <a name="width-counter"></a>Ancho (contador)

El `Width Counter` cuenta el número de qubits asignados y prestados por cada operación.
Todas las operaciones del espacio de nombres `Microsoft.Quantum.Primitive` se expresan en términos de rotaciones de qubit individuales, de T, de qubit Clifford, de CNOT y de qubit de Pauli. Algunas de las operaciones primitivas pueden asignar qubits adicionales. Por ejemplo, multiplique las puertas `X` controladas o las puertas de `T` controladas. Vamos a calcular el número de qubits adicionales asignados por la implementación de una puerta de `X` controlada por multiplicación:

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

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
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

La primera parte del programa ejecuta `MultiControlledXDriver`. En la segunda parte usamos el método `QCTraceSimulator.GetMetric` para obtener el número de qubits asignados, así como el número de qubits que se han controlado `X` recibido como entrada. 

Por último, para generar todas las estadísticas recopiladas por el contador de ancho en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
