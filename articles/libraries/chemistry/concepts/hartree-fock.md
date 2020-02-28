---
title: Teoría de Hartree-Fock
description: Obtenga información sobre la teoría Hartree – Fock, una manera sencilla de construir el estado inicial de los sistemas Quantum.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904458"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="6559f-103">Hartree – Fock (teoría)</span><span class="sxs-lookup"><span data-stu-id="6559f-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="6559f-104">Quizás la cantidad más importante en la simulación de química de Quantum es el estado de la base, que es el Eigenvector energético mínimo de la matriz de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="6559f-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="6559f-105">Esto se debe a que, para la mayoría de las moléculas en las cantidades de temperatura del salón, como las tasas de reacción, están dominadas por diferencias de energía gratuitas entre los Estados de Quantum que describen el principio y el final de un paso en una ruta de reacción y a la temperatura del salón como intermedio el estado son normalmente Estados de la base.</span><span class="sxs-lookup"><span data-stu-id="6559f-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="6559f-106">Aunque el estado de la base suele ser demasiado difícil de aprender (incluso con un equipo Quantum) porque se trata de una distribución a través de un gran número exponencial de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="6559f-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="6559f-107">Se pueden aprender cantidades como la energía del estado de la base.</span><span class="sxs-lookup"><span data-stu-id="6559f-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="6559f-108">Por ejemplo, si $ \ket{\psi} $ es cualquier estado de Quantum puro, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} proporciona la energía media que el sistema tiene en ese estado.</span><span class="sxs-lookup"><span data-stu-id="6559f-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="6559f-109">Después, el estado de la base es el estado que proporciona el valor más pequeño.</span><span class="sxs-lookup"><span data-stu-id="6559f-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="6559f-110">Como resultado, la elección de un estado lo más cercano posible al estado de la base de valor real es fundamental para calcular la energía directamente (como se hace en eigensolverss de variación) o a través de la estimación de la fase.</span><span class="sxs-lookup"><span data-stu-id="6559f-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="6559f-111">Hartree – Fock teoría ofrece una manera sencilla de construir el estado inicial de los sistemas Quantum.</span><span class="sxs-lookup"><span data-stu-id="6559f-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="6559f-112">Produce una única aproximación determinante de Slater al estado de la base de un sistema Quantum.</span><span class="sxs-lookup"><span data-stu-id="6559f-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="6559f-113">Para ello, encuentra un giro en el espacio de Fock que minimiza la energía del estado de la conexión.</span><span class="sxs-lookup"><span data-stu-id="6559f-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="6559f-114">En concreto, para un sistema de $N $ electrones, el método realiza la rotación \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}\end{Equation} con un anti-Hermitian (es decir, $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="6559f-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="6559f-115">Se debe observar que la matriz $u $ representa las rotaciones orbitales y $ \widetilde{a} ^ \ dagger_j $ y $ \widetilde{a} _j $ representan los operadores de creación y Annihilation para los electrones que ocupan Hartree – Fock molecular.</span><span class="sxs-lookup"><span data-stu-id="6559f-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="6559f-116">La matriz $u $ está optimizada para minimizar la energía esperada $ \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="6559f-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="6559f-117">Aunque estos problemas de optimización pueden ser genéricos, en la práctica, el algoritmo Hartree – Fock tiende a converger rápidamente en una solución casi óptima al problema de optimización, especialmente en el caso de moléculas de Shell cerrado en las geometrías de equilibrio.</span><span class="sxs-lookup"><span data-stu-id="6559f-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="6559f-118">Podemos especificar estos Estados como una instancia del objeto `FermionWavefunction`.</span><span class="sxs-lookup"><span data-stu-id="6559f-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="6559f-119">Por ejemplo, el estado $a ^ \ dagger_{1}a ^ \ dagger_{2}se crea una instancia de ^ \ dagger_{6}\ket{0}$ en la biblioteca de química como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="6559f-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="6559f-120">También es posible indexar las funciones de onda con índices de `SpinOrbital` y, a continuación, convertir estos índices en enteros como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="6559f-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="6559f-121">La característica más impactante sobre Hartree – Fock teoría es que produce un estado de Quantum que no tiene ningún inenredo entre los electrones.</span><span class="sxs-lookup"><span data-stu-id="6559f-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="6559f-122">Esto significa que, a menudo, proporciona una descripción cualitativa adecuada de las propiedades de los sistemas moleculares.</span><span class="sxs-lookup"><span data-stu-id="6559f-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="6559f-123">El estado Hartree-Fock también puede reconstruirse a partir de un `FermionHamiltonian` como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="6559f-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="6559f-124">Sin embargo, la obtención de resultados precisos, especialmente para sistemas fuertemente correlacionados, requiere Estados Quantum que vayan más allá de Hartree – Fock teoría.</span><span class="sxs-lookup"><span data-stu-id="6559f-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
