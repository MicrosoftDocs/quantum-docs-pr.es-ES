---
title: Obtención de recuentos de recursos
description: Obtenga información sobre cómo obtener estimaciones de recursos mediante un simulador de seguimiento de Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907841"
---
# <a name="obtaining-resource-counts"></a>Obtención de recuentos de recursos

El costo de simular $n $ qubits en equipos clásico escala exponencialmente con $n $. Esto limita en gran medida el tamaño de una simulación de química de Quantum que se puede llevar a cabo con el simulador de estado completo. En el caso de instancias grandes de química, podemos obtener información útil. En este caso, veremos cómo los costos de recursos, como el número de puertas de T o de CNOT, para simular la química se pueden obtener de manera automatizada mediante el [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Esta información nos informa de cuándo los equipos Quantum pueden ser lo suficientemente grandes como para ejecutar estos algoritmos de química de Quantum. Como referencia, vea el ejemplo de `GetGateCount` proporcionado.

Supongamos que ya tenemos una instancia de `FermionHamiltonian`, por ejemplo, que se carga desde el esquema Broombridge, como se describe en el ejemplo de [carga de archivos](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

La sintaxis para obtener estimaciones de recursos es casi idéntica a la ejecución del algoritmo en el simulador de estado completo. Simplemente elegiremos un equipo de destino diferente. Para los fines de las estimaciones de recursos, basta con evaluar el costo de un solo paso de Trotter o un recorrido de Quantum creado por la técnica de Qubitization. La forma reutilizable para invocar estos algoritmos es la siguiente.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Ahora se configura el simulador de seguimiento para realizar un seguimiento de los recursos que le interesan. En este caso, se cuentan las operaciones de Quantum primitivas estableciendo la marca de `usePrimitiveOperationsCounter` en `true`. Un `throwOnUnconstraintMeasurement` de detalles técnicos se establece en `false` para evitar excepciones en los casos en los que el código de Q # no valida correctamente la probabilidad de los resultados de la medición, si se realizan.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Ahora ejecutamos el algoritmo Quantum desde el programa de controlador como se indica a continuación.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```