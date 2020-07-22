---
title: Obtención de estimaciones de nivel de energía
description: Recorra un programa de ejemplo de preguntas y respuestas que calcula los valores de nivel de energía de hidrógeno molecular.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: b26538980366cf4cbe01fc2ef59580ae182f1e8a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871575"
---
# <a name="obtaining-energy-level-estimates"></a>Obtención de estimaciones de nivel de energía
La estimación de los valores de los niveles de energía es una de las aplicaciones principales de la química de Quantum. En este artículo se describe cómo puede realizar este procedimiento para el ejemplo canónico de hidrógeno molecular. El ejemplo al que se hace referencia en esta sección se encuentra [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) en el repositorio de ejemplos de química. Un ejemplo más visual que representa la salida es la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) demostración.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Estimación de los valores energéticos de hidrógeno molecular

El primer paso consiste en construir el Hamiltonian que representa el hidrógeno molecular. Aunque puede construir esto mediante la herramienta NWChem, para mayor brevedad, este ejemplo agrega los términos Hamiltonian manualmente.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

La simulación de Hamiltonian requiere la conversión de los operadores Fermion en operadores qubit. Esta conversión se realiza a través de la codificación Jordania-Wigner como se indica a continuación:

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

A continuación, pase `qSharpData` , que representa el Hamiltonian, a la `TrotterStepOracle` función. `TrotterStepOracle`Devuelve una operación Quantum que se aproxima a la evolución en tiempo real de Hamiltonian. Para obtener más información, consulte [simulación de Hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

En este momento, puede usar los [algoritmos de estimación de fase](xref:microsoft.quantum.libraries.characterization) de la biblioteca estándar para obtener información sobre la energía de estado de la base de la simulación anterior. Esto requiere preparar una buena aproximación al estado de la base de Quantum. En el esquema se proporcionan sugerencias para estas aproximaciones [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) . Sin embargo, si no se ofrecen estas sugerencias, el enfoque predeterminado agrega una serie de `hamiltonian.NElectrons` electrones para minimizar de forma expansiva el término esfuerzos diagonal de un solo electrones. Las funciones y operaciones de estimación de fase se proporcionan en notación DocFX en el espacio de nombres [Microsoft. Quantum. Caracterización](xref:microsoft.quantum.characterization) .

En el fragmento de código siguiente se muestra cómo se integra la salida de evolución en tiempo real de la biblioteca de simulación de química con la estimación de fase de Quantum.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

Ahora puede invocar el código de preguntas y respuestas desde el programa host. El siguiente código de C# crea un simulador de estado completo y se ejecuta `GetEnergyByTrotterization` para obtener la energía de estado de la alimentación.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

La operación devuelve dos parámetros: 

- `energyEst`es la estimación de la energía del estado de la base y debe estar cerca de la `-1.137` media. 
- `phaseEst`es la fase sin procesar devuelta por el algoritmo de estimación de fase. Esto resulta útil para diagnosticar el alias cuando se produce debido a un `trotterStep` valor demasiado grande.
