---
title: Symmetries de integrales moleculares
description: 'Obtenga información sobre cómo usar el tipo Q # OrbitalIntegral para enumerar el Symmetries molecular.'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275250"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="d07bc-103">Symmetries de integrales moleculares</span><span class="sxs-lookup"><span data-stu-id="d07bc-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="d07bc-104">La simetría inherente del Hamiltonian de Coulomb (, que es el Hamiltonian proporcionado en los [modelos de Quantum para sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels), que describe los electrones que interactúan de forma eléctrica entre sí y con los núcleos, conduce a una serie de Symmetries que se pueden aprovechar para comprimir los términos de la Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d07bc-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="d07bc-105">En general, si no se realizan más suposiciones sobre las funciones de base $ \ psi_j $, solo tenemos \begin{Equation} H_ {PQRS} = H_ {qpsr}. \tag{★} \label{EQ: hpqrs} \end{Equation} que se puede obtener inmediatamente a partir de los enteros de los [modelos de Quantum para los sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) cuando se indica que sus valores siguen siendo idénticos si $p, q $ y $r, s $ se intercambian desde la commutación.</span><span class="sxs-lookup"><span data-stu-id="d07bc-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="d07bc-106">Si damos por hecho que las órbitas giradas son de valor real (como son para las bases orbitales gaussiano), entonces tenemos que \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation} dadas estas suposiciones, podemos usar la Symmetries anterior para reducir los datos necesarios para almacenar los elementos de matriz de la Hamiltonian en un factor de $8 $; Aunque esto hace que la importación de datos de una manera coherente sea ligeramente más complicada.</span><span class="sxs-lookup"><span data-stu-id="d07bc-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="d07bc-107">Afortunadamente, la biblioteca de simulación de Hamiltonian tiene subrutinas que se pueden usar para importar archivos enteros desde [Liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) o directamente desde [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="d07bc-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="d07bc-108">Enteros orbitales moleculares (es decir, los \_ términos $h {pq} $ y $h \_ {PQRS} $) como estos se representan mediante el `OrbitalIntegral` tipo, que proporciona una serie de funciones útiles para expresar esta simetría.</span><span class="sxs-lookup"><span data-stu-id="d07bc-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="d07bc-109">Además de enumerar todas las integrales orbitales que son numéricamente idénticas, se puede generar una lista de todos los índices de giro orbital contenidos en el Hamiltonian representado por un `OrbitalIntegral` .</span><span class="sxs-lookup"><span data-stu-id="d07bc-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="d07bc-110">Construir Fermionic Hamiltonians a partir de integrales moleculares</span><span class="sxs-lookup"><span data-stu-id="d07bc-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="d07bc-111">En lugar de construir un Fermionic Hamiltonian mediante la adición de `FermionTerm` s, se pueden agregar automáticamente todos los términos correspondientes a cada entero orbital.</span><span class="sxs-lookup"><span data-stu-id="d07bc-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="d07bc-112">Por ejemplo, el código siguiente enumera automáticamente todos los Symmetries permutables y ordena los términos en orden canónico:</span><span class="sxs-lookup"><span data-stu-id="d07bc-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```