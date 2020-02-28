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
# <a name="hartreefock-theory"></a>Hartree – Fock (teoría)

Quizás la cantidad más importante en la simulación de química de Quantum es el estado de la base, que es el Eigenvector energético mínimo de la matriz de Hamiltonian.
Esto se debe a que, para la mayoría de las moléculas en las cantidades de temperatura del salón, como las tasas de reacción, están dominadas por diferencias de energía gratuitas entre los Estados de Quantum que describen el principio y el final de un paso en una ruta de reacción y a la temperatura del salón como intermedio el estado son normalmente Estados de la base.
Aunque el estado de la base suele ser demasiado difícil de aprender (incluso con un equipo Quantum) porque se trata de una distribución a través de un gran número exponencial de configuraciones.
Se pueden aprender cantidades como la energía del estado de la base.
Por ejemplo, si $ \ket{\psi} $ es cualquier estado de Quantum puro, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} proporciona la energía media que el sistema tiene en ese estado.
Después, el estado de la base es el estado que proporciona el valor más pequeño. Como resultado, la elección de un estado lo más cercano posible al estado de la base de valor real es fundamental para calcular la energía directamente (como se hace en eigensolverss de variación) o a través de la estimación de la fase.

Hartree – Fock teoría ofrece una manera sencilla de construir el estado inicial de los sistemas Quantum. Produce una única aproximación determinante de Slater al estado de la base de un sistema Quantum. Para ello, encuentra un giro en el espacio de Fock que minimiza la energía del estado de la conexión. En concreto, para un sistema de $N $ electrones, el método realiza la rotación \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}\end{Equation} con un anti-Hermitian (es decir, $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $. Se debe observar que la matriz $u $ representa las rotaciones orbitales y $ \widetilde{a} ^ \ dagger_j $ y $ \widetilde{a} _j $ representan los operadores de creación y Annihilation para los electrones que ocupan Hartree – Fock molecular.


La matriz $u $ está optimizada para minimizar la energía esperada $ \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$. Aunque estos problemas de optimización pueden ser genéricos, en la práctica, el algoritmo Hartree – Fock tiende a converger rápidamente en una solución casi óptima al problema de optimización, especialmente en el caso de moléculas de Shell cerrado en las geometrías de equilibrio. Podemos especificar estos Estados como una instancia del objeto `FermionWavefunction`. Por ejemplo, el estado $a ^ \ dagger_{1}a ^ \ dagger_{2}se crea una instancia de ^ \ dagger_{6}\ket{0}$ en la biblioteca de química como se indica a continuación.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
También es posible indexar las funciones de onda con índices de `SpinOrbital` y, a continuación, convertir estos índices en enteros como se indica a continuación.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

La característica más impactante sobre Hartree – Fock teoría es que produce un estado de Quantum que no tiene ningún inenredo entre los electrones.
Esto significa que, a menudo, proporciona una descripción cualitativa adecuada de las propiedades de los sistemas moleculares. 

El estado Hartree-Fock también puede reconstruirse a partir de un `FermionHamiltonian` como se indica a continuación.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Sin embargo, la obtención de resultados precisos, especialmente para sistemas fuertemente correlacionados, requiere Estados Quantum que vayan más allá de Hartree – Fock teoría.
