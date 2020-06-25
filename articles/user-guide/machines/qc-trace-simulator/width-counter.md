---
title: Ancho (contador)
description: Obtenga información sobre el contador de ancho de QDK de Microsoft, que cuenta el número de qubits asignado y prestado por cada operación en un programa Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275565"
---
# <a name="width-counter"></a>Ancho (contador)

`Width Counter`Cuenta el número de qubits asignados y prestados por cada operación.
Todas las operaciones del `Microsoft.Quantum.Intrinsic` espacio de nombres se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT de qubit Pauli. Algunas de las operaciones primitivas pueden asignar qubits adicionales. Por ejemplo, multiplique las `X` puertas controladas o las puertas controladas `T` . Vamos a calcular el número de qubits adicionales asignados por la implementación de una puerta controlada por multiplicación `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Usar el contador de ancho en un programa de C#

La multiplicación controlada `X` por un total de 5 qubits asignará 2 qubits auxiliares y el ancho de entrada será 5. Para comprobar que este es el caso, podemos usar el siguiente programa de C#:

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

Se ejecuta la primera parte del programa `ApplyMultiControlledX` . En la segunda parte usamos el método `QCTraceSimulator.GetMetric` para obtener el número de qubits asignados, así como el número de qubits que se `X` han controlado como entrada. 

Por último, para generar todas las estadísticas recopiladas por el contador de ancho en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
