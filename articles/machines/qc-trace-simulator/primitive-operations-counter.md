---
title: Contador de operaciones primitivas
description: Obtenga información sobre el contador de operaciones primitivas de Microsoft QDK, que realiza un seguimiento del número de ejecuciones primitivas usadas por las operaciones en un programa Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905954"
---
# <a name="primitive-operations-counter"></a>Contador de operaciones primitivas  

El `Primitive Operations Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum. Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum. Todas las operaciones de `Microsoft.Quantum.Intrinsic` se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables. Las estadísticas recopiladas se agregan a los bordes del gráfico de llamadas de operaciones. Ahora, vamos a contar el número de puertas de `T` que se necesitan para implementar la operación de `CCNOT`. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Usar el contador de operaciones primitivas C# dentro de un programa

Para comprobar que `CCNOT` realmente requiere 7 `T` puertas y que `ApplySampleWithCCNOT` ejecuta 8 puertas `T`, podemos usar el código siguiente C# :

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

La primera parte del programa ejecuta `ApplySampleWithCCNOT`. En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener el número de T puertas que ejecuta `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas. En la operación de ejemplo `Primitive.CCNOT` se llama en `ApplySampleWithCCNOT` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT, ApplySampleWithCCNOT>`. 

Para obtener el número de puertas de `CNOT` utilizadas, podemos agregar la siguiente línea:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Finalmente, para generar todas las estadísticas recopiladas por el contador de la puerta en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Consulte también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
