---
title: 'Comprobador de uso de qubits invalidado: kit de desarrollo de Quantum'
description: Obtenga información sobre el comprobador de uso invalidado de qubits de Microsoft QDK, que usa el simulador de seguimiento de Quantum para comprobar el Q# código en busca de qubits no válidos.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836002"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulador de seguimiento de Quantum: Comprobador de uso de qubits invalidado

El comprobador de uso de qubits invalidado forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de Quantum Development Kit. Puede usarlo para detectar posibles errores en el código causado por qubits no válidos. 

## <a name="invalid-qubits"></a>Qubits no válido

Considere el siguiente fragmento de Q# código para ilustrar los problemas detectados por el comprobador de uso de qubits invalidado:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Cuando se aplica la `H` operación a `q[0]` , apunta a un qubit ya liberado, lo que puede provocar un comportamiento indefinido. Cuando el comprobador de uso de qubits invalidado está habilitado, produce la excepción `InvalidatedQubitsUseCheckerException` si el programa aplica una operación a un qubit ya liberado. Para obtener más información, vea <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Invocar el comprobador de uso de qubits invalidado

Para ejecutar el simulador de seguimiento de Quantum con el comprobador de uso de qubits invalidado, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseInvalidatedQubitsUseChecker` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Usar el comprobador de uso de qubits invalidado en un programa host de C#

A continuación se proporciona un ejemplo de programas host de C# que usan el simulador de seguimiento de Quantum con el comprobador de uso de qubits invalidado habilitado: 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Vea también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API.