---
title: Obtención de estimaciones de nivel de energía
description: 'Recorra un programa de ejemplo Q# que calcula los valores de nivel de energía de hidrógeno molecular.'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691534"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="15435-103">Obtención de estimaciones de nivel de energía</span><span class="sxs-lookup"><span data-stu-id="15435-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="15435-104">La estimación de los valores de los niveles de energía es una de las aplicaciones principales de la química de Quantum.</span><span class="sxs-lookup"><span data-stu-id="15435-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="15435-105">En este artículo se describe cómo puede realizar este procedimiento para el ejemplo canónico de hidrógeno molecular.</span><span class="sxs-lookup"><span data-stu-id="15435-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="15435-106">El ejemplo al que se hace referencia en esta sección se encuentra [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) en el repositorio de ejemplos de química.</span><span class="sxs-lookup"><span data-stu-id="15435-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="15435-107">Un ejemplo más visual que representa la salida es la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demostración.</span><span class="sxs-lookup"><span data-stu-id="15435-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="15435-108">Estimación de los valores energéticos de hidrógeno molecular</span><span class="sxs-lookup"><span data-stu-id="15435-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="15435-109">El primer paso consiste en construir el Hamiltonian que representa el hidrógeno molecular.</span><span class="sxs-lookup"><span data-stu-id="15435-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="15435-110">Aunque puede construir esto mediante la herramienta NWChem, para mayor brevedad, este ejemplo agrega los términos Hamiltonian manualmente.</span><span class="sxs-lookup"><span data-stu-id="15435-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="15435-111">La simulación de Hamiltonian requiere la conversión de los operadores Fermion en operadores qubit.</span><span class="sxs-lookup"><span data-stu-id="15435-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="15435-112">Esta conversión se realiza a través de la codificación de Jordan-Wigner como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="15435-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="15435-113">A continuación, pase `qSharpData` , que representa el Hamiltonian, a la `TrotterStepOracle` función.</span><span class="sxs-lookup"><span data-stu-id="15435-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="15435-114">`TrotterStepOracle` Devuelve una operación Quantum que se aproxima a la evolución en tiempo real de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="15435-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="15435-115">Para obtener más información, consulte [simulación de Hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="15435-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="15435-116">En este momento, puede usar los [algoritmos de estimación de fase](xref:microsoft.quantum.libraries.characterization) de la biblioteca estándar para obtener información sobre la energía de estado de la base de la simulación anterior.</span><span class="sxs-lookup"><span data-stu-id="15435-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="15435-117">Esto requiere preparar una buena aproximación al estado de la base de Quantum.</span><span class="sxs-lookup"><span data-stu-id="15435-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="15435-118">En el esquema se proporcionan sugerencias para estas aproximaciones [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) .</span><span class="sxs-lookup"><span data-stu-id="15435-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="15435-119">Sin embargo, si no se ofrecen estas sugerencias, el enfoque predeterminado agrega una serie de `hamiltonian.NElectrons` electrones para minimizar de forma expansiva el término esfuerzos diagonal de un solo electrones.</span><span class="sxs-lookup"><span data-stu-id="15435-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="15435-120">Las funciones y operaciones de estimación de fase se proporcionan en notación DocFX en el espacio de nombres [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization) .</span><span class="sxs-lookup"><span data-stu-id="15435-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="15435-121">En el fragmento de código siguiente se muestra cómo se integra la salida de evolución en tiempo real de la biblioteca de simulación de química con la estimación de fase de Quantum.</span><span class="sxs-lookup"><span data-stu-id="15435-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="15435-122">Ahora puede invocar el Q# código desde el programa host.</span><span class="sxs-lookup"><span data-stu-id="15435-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="15435-123">El siguiente código de C# crea un simulador de estado completo y se ejecuta `GetEnergyByTrotterization` para obtener la energía de estado de la alimentación.</span><span class="sxs-lookup"><span data-stu-id="15435-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="15435-124">La operación devuelve dos parámetros:</span><span class="sxs-lookup"><span data-stu-id="15435-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="15435-125">`energyEst` es la estimación de la energía del estado de la base y debe estar cerca de la `-1.137` media.</span><span class="sxs-lookup"><span data-stu-id="15435-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="15435-126">`phaseEst` es la fase sin procesar devuelta por el algoritmo de estimación de fase.</span><span class="sxs-lookup"><span data-stu-id="15435-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="15435-127">Esto resulta útil para diagnosticar el alias cuando se produce debido a un `trotterStep` valor demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="15435-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
