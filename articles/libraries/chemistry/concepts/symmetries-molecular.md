---
title: Symmetries de integrales moleculares
description: 'Obtenga información sobre cómo usar el tipo Q # OrbitalIntegral para enumerar el Symmetries molecular.'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904475"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries de integrales moleculares

La simetría inherente del Hamiltonian de Coulomb (, que es el Hamiltonian proporcionado en los [modelos de Quantum para sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels), que describe los electrones que interactúan de forma eléctrica entre sí y con los núcleos, conduce a una serie de Symmetries que se pueden aprovechar para comprimir los términos de la Hamiltonian.
En general, si no se realizan más suposiciones sobre las funciones de base $ \ psi_j $, solo tenemos \begin{Equation} H_ {PQRS} = H_ {qpsr}. \tag{★} \label{EQ: hpqrs} \end{Equation} que se puede obtener inmediatamente a partir de los enteros de los [modelos de Quantum para los sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) cuando se indica que sus valores siguen siendo idénticos si $p, q $ y $r, s $ se intercambian desde la commutación.

Si damos por hecho que las órbitas giradas son de valor real (como son para las bases orbitales gaussiano), entonces tenemos más que \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{ Equation} dadas estas suposiciones, podemos usar el Symmetries anterior para reducir los datos necesarios para almacenar los elementos de la matriz de Hamiltonian en un factor de $8 $; Aunque esto hace que la importación de datos de una manera coherente sea ligeramente más complicada.
Afortunadamente, la biblioteca de simulación de Hamiltonian tiene subrutinas que se pueden usar para importar archivos enteros desde [Liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) o directamente desde [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Enteros orbitales moleculares (es decir, el $h\_{pq} $ y $h\_{PQRS} $ Terms) como estos se representan mediante el tipo de `OrbitalIntegral`, que proporciona una serie de funciones útiles para expresar esta simetría.
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

Además de enumerar todas las integrales orbitales que son numéricamente idénticas, se puede generar una lista de todos los índices de giro orbital contenidos en el Hamiltonian representado por un `OrbitalIntegral`.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Construir Fermionic Hamiltonians a partir de integrales moleculares

En lugar de construir un Fermionic Hamiltonian mediante la adición de `FermionTerm`s, se pueden agregar automáticamente todos los términos correspondientes a cada entero orbital.
Por ejemplo, el código siguiente enumera automáticamente todos los Symmetries permutables y ordena los términos en orden canónico: 
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
