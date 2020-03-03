---
title: Simulador de seguimiento de equipos cuánticos
description: Obtenga información sobre cómo usar el simulador de seguimiento de equipos de Microsoft Quantum para depurar código clásico y calcular los requisitos de recursos de un programa cuántico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906090"
---
# <a name="quantum-trace-simulator"></a>Simulador de seguimiento de equipos cuánticos

El simulador de seguimiento de equipos cuánticos de Microsoft ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico.  Por esta razón, el simulador de seguimiento puede ejecutar programas cuánticos que usan miles de qubits.  Esto tiene dos propósitos principales: 

* Depurar código clásico que forma parte de un programa cuántico. 
* Calcular los recursos necesarios para ejecutar una determinada instancia de un programa cuántico en un equipo cuántico.

El simulador de seguimiento se basa en la información adicional que proporciona el usuario cuando se deben realizar medidas. Consulte la sección [Proporcionar la probabilidad de los resultados de medidas](#providing-the-probability-of-measurement-outcomes) para obtener más detalles. 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Proporcionar la probabilidad de los resultados de medidas

Hay dos tipos de medidas que aparecen en los algoritmos cuánticos. El primer tipo juega un papel auxiliar en el que el usuario normalmente conoce la probabilidad de los resultados. En este caso, el usuario puede escribir <xref:microsoft.quantum.intrinsic.assertprob> en el espacio de nombres <xref:microsoft.quantum.intrinsic> para expresar este conocimiento. Esto se ilustra en el ejemplo siguiente:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Si el simulador de seguimiento ejecuta `AssertProb`, este registrará que a la medida `PauliZ` en `source` y `q` se le debe dar un resultado de `Zero` con una probabilidad de 0,5. Si el simulador ejecuta `M` posteriormente, encontrará los valores registrados de las probabilidades de resultados y `M` devolverá `Zero` o `One` con una probabilidad de 0,5. Si se ejecuta el mismo código en un simulador que realiza un seguimiento del estado cuántico, ese simulador comprobará que las probabilidades que se proporcionan en `AssertProb` son correctas.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Ejecución del programa con el simulador de seguimiento de equipos cuánticos 

El simulador de seguimiento de equipos cuánticos se puede considerar simplemente como otra máquina de destino. El programa del controlador de C# para usarlo es muy similar al de cualquier otro simulador cuántico: 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Tenga en cuenta que si hay alguna medida que no se haya anotado mediante `AssertProb`, el simulador devolverá `UnconstrainedMeasurementException` desde el espacio de nombres `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Consulte la documentación de la API sobre [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) para más información.

Además de ejecutar programas cuánticos, el simulador de seguimiento incluye cinco componentes para detectar errores en los programas y realizar cálculos sobre los recursos que necesitan los programas cuánticos. 

* [Comprobador de entradas únicas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Comprobador de uso de qubits invalidado](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Contador de operaciones primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Contador de profundidad del circuito](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Contador de anchura del circuito](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Cada uno de estos componentes se puede habilitar mediante el establecimiento de las marcas adecuadas en `QCTraceSimulatorConfiguration`. Se puede encontrar más información sobre cada uno de estos componentes en los archivos de referencia correspondientes. Consulte la documentación de la API sobre [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obtener detalles más específicos.

## <a name="see-also"></a>Consulte también
Referencia de C# sobre el [simulador de seguimiento](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) de equipos cuánticos 

