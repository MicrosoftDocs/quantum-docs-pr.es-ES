---
title: Funciones de onda correlacionadas
description: Obtenga información sobre las correlaciones dinámicas y no dinámicas en wavefunctions con la biblioteca de química de Quantum de Microsoft.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275913"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="215b4-103">Funciones de onda correlacionadas</span><span class="sxs-lookup"><span data-stu-id="215b4-103">Correlated wavefunctions</span></span>

<span data-ttu-id="215b4-104">En muchos sistemas, especialmente en los que están cerca de la geometría de equilibrio, la teoría [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) proporciona una descripción cualitativa de las propiedades moleculares a través de un estado de referencia determinante único.</span><span class="sxs-lookup"><span data-stu-id="215b4-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="215b4-105">Sin embargo, para lograr una precisión cuantitativa, también se deben tener en cuenta los efectos de correlación.</span><span class="sxs-lookup"><span data-stu-id="215b4-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="215b4-106">En este contexto, es importante dinstinguish entre correlaciones dinámicas y no dinámicas.</span><span class="sxs-lookup"><span data-stu-id="215b4-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="215b4-107">Las correlaciones dinámicas provienen de la tendencia de los electrones a quedarse separadas, por ejemplo, debido a la repulsión interelectrónica.</span><span class="sxs-lookup"><span data-stu-id="215b4-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="215b4-108">Este efecto se puede modelar teniendo en cuenta las expediciones de los electrones fuera del estado de referencia.</span><span class="sxs-lookup"><span data-stu-id="215b4-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="215b4-109">Las correlaciones no dinámicas se producen cuando el WaveFunction está dominado por dos o más configuraciones en orden inicial, incluso para lograr solo una descripción cualitativa del sistema.</span><span class="sxs-lookup"><span data-stu-id="215b4-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="215b4-110">Esto requiere una superposición de los factores determinantes y es un ejemplo de un WaveFunction de multireferencia.</span><span class="sxs-lookup"><span data-stu-id="215b4-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="215b4-111">La biblioteca de química proporciona una manera de especificar un WaveFunction de orden inicial para el problema de multireferencia como una superposición de los determinantes.</span><span class="sxs-lookup"><span data-stu-id="215b4-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="215b4-112">Este enfoque, al que llamamos wavefunctions multireferencia dispersa, es eficaz cuando solo unos pocos componentes bastan para especificar la superposición.</span><span class="sxs-lookup"><span data-stu-id="215b4-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="215b4-113">La biblioteca también proporciona un método para incluir las correlaciones dinámicas sobre una referencia de un solo determinante a través de la ansatz de la agrupación de unitarios con el clúster generalizado.</span><span class="sxs-lookup"><span data-stu-id="215b4-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="215b4-114">Además, también construye circuitos Quantum que generan estos Estados en un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="215b4-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="215b4-115">Estos Estados se pueden especificar en el [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)y también se proporciona la funcionalidad para especificar manualmente estos Estados a través de la biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="215b4-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="215b4-116">WaveFunction de varias referencias dispersas</span><span class="sxs-lookup"><span data-stu-id="215b4-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="215b4-117">Un estado de referencia múltiple $ \ket{\ psi_ {\rm {MCSCF}}} $ puede especificarse explícitamente como una combinación lineal de $N $-electrones Slater determininants.</span><span class="sxs-lookup"><span data-stu-id="215b4-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="215b4-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="215b4-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="215b4-119">\end{align} por ejemplo, el estado $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ puede especificarse en la biblioteca de química como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="215b4-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="215b4-120">Esta representación explícita de los componentes de superposición es efectiva cuando se necesitan especificar solo algunos componentes.</span><span class="sxs-lookup"><span data-stu-id="215b4-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="215b4-121">Uno debe evitar el uso de esta representación cuando se necesitan muchos componentes para capturar con precisión el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="215b4-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="215b4-122">La razón es que el costo de la barrera del circuito del Quantum prepara este estado en un equipo Quantum, que escala al menos linealmente con el número de componentes de superposición y, como máximo, de forma cuadrática con la única norma de las amplitudes de superposición.</span><span class="sxs-lookup"><span data-stu-id="215b4-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="215b4-123">Unitario acoplado: clúster WaveFunction</span><span class="sxs-lookup"><span data-stu-id="215b4-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="215b4-124">También es posible especificar un grupo de WaveFunction $ \ket{\ psi_ {\rm {UCC}} $ mediante la biblioteca Chemistery.</span><span class="sxs-lookup"><span data-stu-id="215b4-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="215b4-125">En esta situación, tenemos un estado de referencia determinante único, por ejemplo, $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="215b4-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="215b4-126">Los componentes de la WaveFunction de la unitario acoplada-cluster se especifican implícitamente a través de un operador unitario que actúa en un estado de referencia.</span><span class="sxs-lookup"><span data-stu-id="215b4-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="215b4-127">Este operador unitario se escribe normalmente como $e ^ {T-T ^ \dagger} $, donde $T-T ^ \dagger $ es el operador de clúster Hermitian.</span><span class="sxs-lookup"><span data-stu-id="215b4-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="215b4-128">Por lo tanto, \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="215b4-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="215b4-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="215b4-129">\end{align}</span></span>

<span data-ttu-id="215b4-130">También es común dividir el operador de clúster $T = T_1 + T_2 + \cdots $ en partes, donde cada parte $T _j $ contiene $j términos $-Body.</span><span class="sxs-lookup"><span data-stu-id="215b4-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="215b4-131">En teoría del clúster de acoplamiento generalizado, el operador de clúster de un cuerpo (único) tiene el formato \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="215b4-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="215b4-132">y el operador de clúster de dos cuerpos (dobles) tiene el formato \begin{align} T_2 = \ sum_ {PQRS} T ^ {pq} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="215b4-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="215b4-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="215b4-133">\end{align}</span></span>

<span data-ttu-id="215b4-134">Los términos de orden superior (triples, cuadruplican, etc.) son posibles, pero no se admiten actualmente en la biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="215b4-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="215b4-135">Por ejemplo, supongamos que $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ y deje $T = 0,123 a ^ \ dagger_0 a_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="215b4-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="215b4-136">A continuación, se crea una instancia de este estado en la biblioteca de química como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="215b4-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="215b4-137">Spin convervation se puede hacer explícitamente mediante la especificación `SpinOrbital` de índices en lugar de índices de enteros.</span><span class="sxs-lookup"><span data-stu-id="215b4-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="215b4-138">Por ejemplo, supongamos que $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ y let $T = 0,123 a ^ \ dagger_ {0. \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ is spin convserving.</span><span class="sxs-lookup"><span data-stu-id="215b4-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="215b4-139">A continuación, se crea una instancia de este estado en la biblioteca de química como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="215b4-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="215b4-140">También se proporciona una función de conveniencia que enumera todos los operadores de clústeres de la conversación de paso que solo annihilaten las órbitas ocupadas y se adquieren solo giros de giro no ocupados.</span><span class="sxs-lookup"><span data-stu-id="215b4-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
