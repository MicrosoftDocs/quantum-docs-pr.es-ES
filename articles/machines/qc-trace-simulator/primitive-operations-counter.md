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
# <a name="primitive-operations-counter"></a>Contador de operaciones primitivas  

El `Primitive Operations Counter` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipo Quantum. Cuenta el número de ejecuciones primitivas utilizadas por cada operación invocada en un programa Quantum. Todas las operaciones de `Microsoft.Quantum.Primitive` se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT y de qubit Pauli observables. Las estadísticas recopiladas se agregan a los bordes del gráfico de llamadas de operaciones. Ahora, vamos a contar el número de puertas de `T` que se necesitan para implementar la operación de `CCNOT`. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Usar el contador de operaciones primitivas C# dentro de un programa

Para comprobar que `CCNOT` realmente requiere 7 `T` puertas y que `CCNOTDriver` ejecuta 8 puertas `T`, podemos usar el código siguiente C# :

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

La primera parte del programa ejecuta `CCNOTDriver`. En la segunda parte, usamos el método `QCTraceSimulator.GetMetric` para obtener el número de T puertas que ejecuta `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Cuando se llama a `GetMetric` con dos parámetros de tipo, devuelve el valor de la métrica asociada a un determinado borde del gráfico de llamadas. En la operación de ejemplo `Primitive.CCNOT` se llama en `CCNOTDriver` y, por tanto, el gráfico de llamadas contiene el borde `<Primitive.CCNOT,CCNOTDriver>`. 

Para obtener el número de puertas de `CNOT` utilizadas, podemos agregar la siguiente línea:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Finalmente, para generar todas las estadísticas recopiladas por el contador de la puerta en formato CSV, podemos usar lo siguiente:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
