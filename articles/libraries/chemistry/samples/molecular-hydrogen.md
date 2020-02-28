---
title: Obtención de estimaciones de nivel de energía
description: Recorra un programa de ejemplo de preguntas y respuestas que calcula los valores de nivel de energía de hidrógeno molecular.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907314"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="4a883-103">Obtención de estimaciones de nivel de energía</span><span class="sxs-lookup"><span data-stu-id="4a883-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="4a883-104">La estimación de los valores de los niveles de energía es una de las aplicaciones principales de la química de Quantum.</span><span class="sxs-lookup"><span data-stu-id="4a883-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="4a883-105">Aquí se describe cómo se puede realizar esta operación para el ejemplo canónico de hidrógeno molecular.</span><span class="sxs-lookup"><span data-stu-id="4a883-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="4a883-106">El ejemplo al que se hace referencia en esta sección se `MolecularHydrogen` en el repositorio de ejemplos de química.</span><span class="sxs-lookup"><span data-stu-id="4a883-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="4a883-107">Un ejemplo más visual que representa la salida es la demostración de `MolecularHydrogenGUI`.</span><span class="sxs-lookup"><span data-stu-id="4a883-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="4a883-108">El primer paso es construir el Hamiltonian que representa el hidrógeno molecular.</span><span class="sxs-lookup"><span data-stu-id="4a883-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="4a883-109">Aunque esto se puede construir mediante la herramienta NWChem, se agregan manualmente los términos de Hamiltonian para mayor brevedad en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a883-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="4a883-110">La simulación de Hamiltonian requiere convertir los operadores Fermion en operadores qubit.</span><span class="sxs-lookup"><span data-stu-id="4a883-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="4a883-111">Esta conversión se realiza a través de la codificación Jordania-Wigner como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="4a883-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="4a883-112">Ahora pasamos el `qSharpData` que representa Hamiltonian a la función de `TrotterStepOracle` en la [simulación de Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span><span class="sxs-lookup"><span data-stu-id="4a883-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="4a883-113">`TrotterStepOracle` devuelve una operación Quantum que se aproxima a la evolución en tiempo real de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4a883-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="4a883-114">Ahora podemos usar los algoritmos de estimación de fase de la biblioteca estándar para aprender la energía de estado de la base de la simulación.</span><span class="sxs-lookup"><span data-stu-id="4a883-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="4a883-115">Esto requiere preparar una buena aproximación al estado de la base de Quantum.</span><span class="sxs-lookup"><span data-stu-id="4a883-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="4a883-116">En el esquema de `Broombridge` se proporcionan sugerencias para estas aproximaciones, pero no están presentes estas sugerencias, el enfoque predeterminado agrega una serie de electrones de `hamiltonian.NElectrons` a minimizar con suma el término de esfuerzos de un solo electrones.</span><span class="sxs-lookup"><span data-stu-id="4a883-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="4a883-117">Las funciones y operaciones de estimación de fase se encuentran en el [espacio de nombres Microsoft. Quantum. Caracterización](xref:microsoft.quantum.characterization in DocFX notation).</span><span class="sxs-lookup"><span data-stu-id="4a883-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="4a883-118">En el fragmento de código siguiente se muestra cómo la biblioteca de simulación de química puede integrar la salida en tiempo real de la evolución en tiempo real con la estimación de la fase de Quantum.</span><span class="sxs-lookup"><span data-stu-id="4a883-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="4a883-119">Este código de Q # puede llamarse ahora desde el programa de controladores.</span><span class="sxs-lookup"><span data-stu-id="4a883-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="4a883-120">En el siguiente procedimiento, se crea un simulador de estado completo y se ejecuta `GetEnergyByTrotterization` para obtener la energía de estado de la base.</span><span class="sxs-lookup"><span data-stu-id="4a883-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="4a883-121">Observe que se devuelven dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="4a883-121">Note that two parameters are returned.</span></span> <span data-ttu-id="4a883-122">`energyEst` es la estimación de la energía de estado de la alimentación y debe estar en torno a `-1.137` de promedio.</span><span class="sxs-lookup"><span data-stu-id="4a883-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="4a883-123">`phaseEst` es la fase sin procesar devuelta por el algoritmo de estimación de fase y es útil para diagnosticar cuando se produce el alias debido a un `trotterStep` demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="4a883-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
