---
title: 'Comprobador de uso de qubits invalidado: kit de desarrollo de Quantum'
description: Obtenga información sobre el comprobador de uso de qubits de Microsoft QDK invalidado, que usa el simulador de seguimiento de Quantum para comprobar el código de preguntas y respuestas de qubits no válidos.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871100"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulador de seguimiento de Quantum: Comprobador de uso de qubits invalidado

El comprobador de uso de qubits invalidado forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de Quantum Development Kit. Puede usarlo para detectar posibles errores en el código causado por qubits no válidos. 

## <a name="invalid-qubits"></a>Qubits no válido

Considere el siguiente fragmento de código de preguntas y respuestas para ilustrar los problemas detectados por el comprobador de uso de qubits invalidado:

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

## <a name="see-also"></a>Consulta también

- Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API.