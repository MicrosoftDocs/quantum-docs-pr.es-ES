---
title: 'Comprobador de entradas DISTINCT: kit de desarrollo de Quantum'
description: Obtenga información sobre el comprobador de entradas distintas de Microsoft QDK, que usa el simulador de seguimiento de Quantum para comprobar el Q# código en busca de posibles conflictos con qubits compartidas.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868277"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Simulador de seguimiento de Quantum: Comprobador de entradas distintas

El comprobador de entradas DISTINCT es una parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de Quantum Development Kit. Puede usarlo para detectar posibles errores en el código causados por conflictos con qubits compartidos. 

## <a name="conflicts-with-shared-qubits"></a>Conflictos con qubits compartidos

Considere el siguiente fragmento de Q# código para ilustrar los problemas detectados por el comprobador de entradas distintivo:

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

Al examinar este programa, puede suponer que el orden en el que llama a `op1` y no `op2` importa, ya que `q1` y `q2` son diferentes qubits y operaciones que actúan en diferentes desactivaciones de qubits. 

Ahora, considere este ejemplo:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Tenga en cuenta que `op1` y `op2` se obtienen mediante la aplicación parcial y comparten un qubit. Cuando se llama a `ApplyBoth` en este ejemplo, el resultado de la operación depende del orden de `op1` y `op2` dentro `ApplyBoth` de lo que se espera que suceda. Al habilitar el comprobador de entradas DISTINCT, detecta esas situaciones y produce una excepción `DistinctInputsCheckerException` . Para obtener más información, vea <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> en la Q# biblioteca de API.

## <a name="invoking-the-distinct-inputs-checker"></a>Invocar el comprobador de entradas DISTINCT

Para ejecutar el simulador de seguimiento de Quantum con el comprobador de entradas DISTINCT, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseDistinctInputsChecker` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Usar el comprobador de entradas DISTINCT en un programa host de C#

A continuación se proporciona un ejemplo de un programa host de C# que usa el simulador de seguimiento de Quantum con el comprobador de entradas distintivos habilitado:

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
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
- Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API.
