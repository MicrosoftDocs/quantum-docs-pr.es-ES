---
title: Comprobador de uso de qubits invalidado | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820885"
---
# <a name="invalidated-qubits-use-checker"></a>Comprobador de uso de qubits invalidado

El `Invalidated Qubits Use Checker` es una parte del equipo Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) diseñado para detectar posibles errores en el código. Tenga en cuenta la siguiente parte del código de preguntas y respuestas para ilustrar los problemas detectados por el `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit() : Unit {
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
