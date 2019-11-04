---
title: Simulador de seguimiento de equipos cuánticos | Microsoft Docs
description: Introducción a un simulador de seguimiento de equipos cuánticos
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035138"
---
# <a name="quantum-trace-simulator"></a>Simulador de seguimiento de equipos cuánticos

El simulador de seguimiento de equipos cuánticos de Microsoft ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico.  Por esta razón, el simulador de seguimiento puede ejecutar programas cuánticos que usan miles de qubits.  Esto tiene dos propósitos principales: 

* Depurar código clásico que forma parte de un programa cuántico. 
* Calcular los recursos necesarios para ejecutar una determinada instancia de un programa cuántico en un equipo cuántico.

El simulador de seguimiento se basa en la información adicional que proporciona el usuario cuando se deben realizar medidas. Consulte la sección [Proporcionar la probabilidad de los resultados de medidas](#providing-the-probability-of-measurement-outcomes) para obtener más detalles. 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Proporcionar la probabilidad de los resultados de medidas

Hay dos tipos de medidas que aparecen en los algoritmos cuánticos. El primer tipo juega un papel auxiliar en el que el usuario normalmente conoce la probabilidad de los resultados. En este caso, el usuario puede escribir <xref:microsoft.quantum.primitive.assertprob> en el espacio de nombres <xref:microsoft.quantum.primitive> para expresar este conocimiento. Esto se ilustra en el ejemplo siguiente:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

Si el simulador de seguimiento ejecuta `AssertProb`, este registrará que a la medida `PauliZ` en `source` y `ancilla` se le debe dar un resultado de `Zero` con una probabilidad de 0,5. Si el simulador ejecuta `M` posteriormente, encontrará los valores registrados de las probabilidades de resultados y `M` devolverá `Zero` o `One` con una probabilidad de 0,5. Si se ejecuta el mismo código en un simulador que realiza un seguimiento del estado cuántico, ese simulador comprobará que las probabilidades que se proporcionan en `AssertProb` son correctas.

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

## <a name="see-also"></a>Otras referencias
Referencia de C# sobre el [simulador de seguimiento](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) de equipos cuánticos 

