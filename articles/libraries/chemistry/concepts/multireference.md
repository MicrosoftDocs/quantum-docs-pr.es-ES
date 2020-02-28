---
title: Funciones de onda correlacionadas
description: Obtenga información sobre las correlaciones dinámicas y no dinámicas en wavefunctions con la biblioteca de química de Quantum de Microsoft.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904441"
---
# <a name="correlated-wavefunctions"></a>Funciones de onda correlacionadas

En muchos sistemas, especialmente en los que están cerca de la geometría de equilibrio, la teoría [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) proporciona una descripción cualitativa de las propiedades moleculares a través de un estado de referencia determinante único. Sin embargo, para lograr una precisión cuantitativa, también se deben tener en cuenta los efectos de correlación. 

En este contexto, es importante dinstinguish entre correlaciones dinámicas y no dinámicas.
Las correlaciones dinámicas provienen de la tendencia de los electrones a quedarse separadas, por ejemplo, debido a la repulsión interelectrónica. Este efecto se puede modelar teniendo en cuenta las expediciones de los electrones fuera del estado de referencia. Las correlaciones no dinámicas se producen cuando el WaveFunction está dominado por dos o más configuraciones en orden inicial, incluso para lograr solo una descripción cualitativa del sistema.
Esto requiere una superposición de los factores determinantes y es un ejemplo de un WaveFunction de multireferencia.

La biblioteca de química proporciona una manera de especificar un WaveFunction de orden inicial para el problema de multireferencia como una superposición de los determinantes. Este enfoque, al que llamamos wavefunctions multireferencia dispersa, es eficaz cuando solo unos pocos componentes bastan para especificar la superposición. La biblioteca también proporciona un método para incluir las correlaciones dinámicas sobre una referencia de un solo determinante a través de la ansatz de la agrupación de unitarios con el clúster generalizado. Además, también construye circuitos Quantum que generan estos Estados en un equipo Quantum. Estos Estados se pueden especificar en el [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)y también se proporciona la funcionalidad para especificar manualmente estos Estados a través de la biblioteca de química.

## <a name="sparse-multi-reference-wavefunction"></a>WaveFunction de varias referencias dispersas
Un estado de referencia múltiple $ \ket{\ psi_ {\rm {MCSCF}}} $ puede especificarse explícitamente como una combinación lineal de $N $-electrones Slater determininants.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket{0}.
\end{align} por ejemplo, el estado $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket{0}$ puede especificarse en la biblioteca de química como se indica a continuación.
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
Esta representación explícita de los componentes de superposición es efectiva cuando se necesitan especificar solo algunos componentes. Uno debe evitar el uso de esta representación cuando se necesitan muchos componentes para capturar con precisión el estado deseado. La razón es que el costo de la barrera del circuito del Quantum prepara este estado en un equipo Quantum, que escala al menos linealmente con el número de componentes de superposición y, como máximo, de forma cuadrática con la única norma de las amplitudes de superposición.

## <a name="unitary-coupled-cluster-wavefunction"></a>Unitario acoplado: clúster WaveFunction
También es posible especificar un grupo de WaveFunction $ \ket{\ psi_ {\rm {UCC}} $ mediante la biblioteca Chemistery. En esta situación, tenemos un estado de referencia determinante único, por ejemplo, $ \ket{\ psi_ {\rm{SCF}}} $. Los componentes de la WaveFunction de la unitario acoplada-cluster se especifican implícitamente a través de un operador unitario que actúa en un estado de referencia.
Este operador unitario se escribe normalmente como $e ^ {T-T ^ \dagger} $, donde $T-T ^ \dagger $ es el operador de clúster Hermitian. Por lo tanto, \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

También es común dividir el operador de clúster $T = T_1 + T_2 + \cdots $ en partes, donde cada parte $T _j $ contiene $j términos $-Body. En teoría del clúster de acoplamiento generalizado, el operador de clúster de un cuerpo (único) tiene el formato \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

y el operador de clúster de dos cuerpos (dobles) tiene el formato \begin{align} T_2 = \ sum_ {PQRS} T ^ {pq} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.
\end{align}

Los términos de orden superior (triples, cuadruplican, etc.) son posibles, pero no se admiten actualmente en la biblioteca de química.

Por ejemplo, supongamos que $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}$ y que $T = 0,123 a ^ \ dagger_0 a_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $. A continuación, se crea una instancia de este estado en la biblioteca de química como se indica a continuación.
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

Spin convervation se puede hacer explícitamente mediante la especificación de `SpinOrbital` índices en lugar de índices de enteros. Por ejemplo, supongamos que $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket{0}$ y Let $T = 0,123 a ^ \ dagger_ {0. \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ is spin convserving. A continuación, se crea una instancia de este estado en la biblioteca de química como se indica a continuación.
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

También se proporciona una función de conveniencia que enumera todos los operadores de clústeres de la conversación de paso que solo annihilaten las órbitas ocupadas y se adquieren solo giros de giro no ocupados.
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
