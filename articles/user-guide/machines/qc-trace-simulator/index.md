---
title: 'Simulador de seguimiento cuántico: Kit de desarrollo de Microsoft Quantum'
description: Obtenga información sobre cómo usar el simulador de seguimiento cuántico de Microsoft para depurar código clásico y calcular los requisitos de recursos de un programa de Q#.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2e2d9f8494d8709fba34123793cecce4011b609a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690839"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Simulador de seguimiento cuántico del kit de desarrollo de Microsoft Quantum (QDK)

La clase <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> de QDK ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico. Por esta razón, el simulador de seguimiento cuántico puede ejecutar programas cuánticos que usan miles de cúbits.  Esto tiene dos propósitos principales: 

* Depurar código clásico que forma parte de un programa cuántico. 
* Calcular los recursos necesarios para ejecutar una determinada instancia de un programa cuántico en un equipo cuántico. De hecho, el [estimador de recursos](xref:microsoft.quantum.machines.resources-estimator), que proporciona un conjunto de métricas más limitado, se basa en el simulador de seguimiento.

## <a name="invoking-the-quantum-trace-simulator"></a>Invocación del simulador de seguimiento cuántico

Puede usar el simulador de seguimiento cuántico para ejecutar cualquier operación de Q#.

Al igual que con otras máquinas de destino, primero se crea una instancia de la clase `QCTraceSimulator` y, a continuación, se pasa como el primer parámetro del método `Run` de una operación.

Tenga en cuenta que, a diferencia de la clase `QuantumSimulator`, la clase `QCTraceSimulator` no implementa la interfaz <xref:System.IDisposable> y, por lo tanto, no es necesario encerrarla dentro de una instrucción `using`.

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Probabilidad de los resultados de una medición

Como el simulador de seguimiento cuántico no simula el estado cuántico real, no puede calcular la probabilidad de los resultados de una medición dentro de una operación. 

Por consiguiente, si una operación incluye mediciones, debe proporcionar explícitamente estas probabilidades con la operación <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> del espacio de nombres <xref:Microsoft.Quantum.Diagnostics>. Esto se ilustra en el ejemplo siguiente:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Si el simulador de seguimiento cuántico se encuentra con `AssertMeasurementProbability`, registrará que la medición de `PauliZ` en `source` y `q` dará un resultado de `Zero`, con una probabilidad de **0,5** . Más adelante, cuando ejecuta la operación `M`, busca los valores registrados de las probabilidades de resultado y `M` devuelve `Zero` o `One`, con una probabilidad de **0,5** . Si se ejecuta el mismo código en un simulador que realiza un seguimiento del estado cuántico, ese simulador comprueba que las probabilidades que se proporcionan en `AssertMeasurementProbability` sean correctas.

Tenga en cuenta que si hay al menos una operación de medición que no se haya anotado mediante `AssertMeasurementProbability`, el simulador activará [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Herramientas del simulador de seguimiento cuántico

El QDK incluye cinco herramientas que se pueden usar con el simulador de seguimiento cuántico para detectar errores en los programas y calcular los recursos de los programas cuánticos: 

|Herramienta | Descripción |
|-----| -----|
|[Comprobador de entradas únicas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Comprueba posibles conflictos con los cúbits compartidos |
|[Comprobador de uso de cúbits invalidado](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Comprueba si el programa aplica una operación a un cúbit que ya se ha liberado. |
|[Contador de operaciones primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Cuenta el número de primitivas utilizadas por cada operación invocada en un programa cuántico.  |
|[Contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Recopila recuentos que representan el límite inferior de la profundidad de cada operación invocada en un programa cuántico.   |
|[Contador de ancho](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Cuenta el número de cúbits asignados y prestados por cada operación en un programa cuántico. |

Para habilitar cada una de estas herramientas, hay que establecer las marcas correspondientes en `QCTraceSimulatorConfiguration` y, a continuación, pasar la configuración a la declaración de `QCTraceSimulator`. Para más información sobre el uso de cada una de estas herramientas, consulte los vínculos de la lista anterior. Para más información sobre la configuración de `QCTraceSimulator`, consulte [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Métodos de QCTraceSimulator

`QCTraceSimulator` tiene varios métodos integrados para recuperar los valores de las métricas de las que se realiza un seguimiento durante una operación cuántica. Se pueden encontrar ejemplos de los métodos [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) y [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) en los artículos [Contador de operaciones primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contador de profundidad](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) y [Contador de ancho](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Para más información sobre todos los métodos disponibles, consulte [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) en la referencia de la API de Q#.  

## <a name="see-also"></a>Consulte también

- [Estimador de recursos cuánticos](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador cuántico de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador cuántico de estado completo](xref:microsoft.quantum.machines.full-state-simulator) 