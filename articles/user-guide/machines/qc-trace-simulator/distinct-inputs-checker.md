---
title: Comprobador de entradas DISTINCT
description: Obtenga información sobre el comprobador de entradas de Microsoft QDK DISTINCT, que comprueba el código de preguntas y respuestas potenciales con qubits compartidas.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275618"
---
# <a name="distinct-inputs-checker"></a>Comprobador de entradas DISTINCT

La `Distinct Inputs Checker` forma parte del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de equipos Quantum. Está diseñado para detectar posibles errores en el código. Tenga en cuenta la siguiente parte del código de preguntas y respuestas para ilustrar los problemas detectados por este paquete:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Cuando el usuario examina este programa, se da por hecho que el orden en el que `op1` se llama a y no es `op2` importante porque `q1` y `q2` son diferentes qubits y operaciones que actúan en diferentes qubits de desactivación. Ahora veamos un ejemplo en el que se usa esta operación:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Ahora `op1` y `op2` se obtienen mediante la aplicación parcial y comparten un qubit. Cuando el usuario llama a `ApplyBoth` en el ejemplo anterior, el resultado de la operación dependerá del orden de `op1` y dentro de `op2` `ApplyBoth` . Esto no es lo que el usuario esperaría que ocurriera. `Distinct Inputs Checker`Detectará tales situaciones cuando se habilite y producirá una excepción `DistinctInputsCheckerException` . Consulte la documentación de la API en [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obtener más información.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Usar el comprobador de entradas DISTINCT en el programa de C#

A continuación se proporciona un ejemplo de código de controlador C# para usar el simulador de seguimiento de equipo Quantum con `Distinct Inputs Checker` habilitado:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

La clase `QCTraceSimulatorConfiguration` almacena la configuración del simulador de seguimiento de equipo Quantum y se puede proporcionar como argumento para el `QCTraceSimulator` constructor. Cuando `useDistinctInputsChecker` se establece en true, el `Distinct Inputs Checker` está habilitado. Consulte la documentación de la API en [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) y [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para obtener más información.

## <a name="see-also"></a>Vea también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.