---
title: Comprobador de uso de qubits invalidado | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184974"
---
# <a name="invalidated-qubits-use-checker"></a>Comprobador de uso de qubits invalidado

El `Invalidated Qubits Use Checker` es una parte del equipo Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) diseñado para detectar posibles errores en el código. Tenga en cuenta la siguiente parte del código de preguntas y respuestas para ilustrar los problemas detectados por el `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Cuando se aplica `H` a `q[0]` apunta a un qubit ya liberado. Esto puede producir un comportamiento indefinido. Cuando la `Invalidated Qubits Use Checker` está habilitada, se producirá la `InvalidatedQubitsUseCheckerException` de excepción si se aplica una operación a un qubit ya liberado. Consulte la documentación de la API en [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para obtener más información.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Usar el comprobador de uso de qubits invalidado en el C# programa

El siguiente es un ejemplo de C# código de controlador para usar el equipo Quantum `Trace
Simulator` con el `Invalidated Qubits Use Checker` habilitado: 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

La clase `QCTraceSimulatorConfiguration` almacena la configuración del simulador de seguimiento de equipo Quantum y se puede proporcionar como argumento para el constructor `QCTraceSimulator`. Cuando `useInvalidatedQubitsUseChecker` está establecido en true, el `Invalidated Qubits Use Checker` está habilitado. Consulte la documentación de la API en [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) y [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obtener más información.

## <a name="see-also"></a>Vea también ##

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.
