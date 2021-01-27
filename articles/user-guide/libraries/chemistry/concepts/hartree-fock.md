---
title: Hartree-Fock teoría
description: Obtenga información sobre la teoría Hartree – Fock, una manera sencilla de construir el estado inicial de los sistemas Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 48d6bc4face90046271dd8705188a92daafad98a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854089"
---
# <a name="hartreefock-theory"></a>Hartree – Fock (teoría)

Quizás la cantidad más importante en la simulación de química de Quantum es el estado de la base, que es el Eigenvector energético mínimo de la matriz de Hamiltonian.
Esto se debe a que, para la mayoría de las moléculas en las cantidades de temperatura de la habitación, como las tasas de reacción están preparadas por diferencias de energía gratuitas entre los Estados de Quantum que describen el principio y el final de un paso en una ruta de reacción y a la temperatura del salón, este estado intermedio es normalmente un estado
Aunque el estado de la base suele ser demasiado difícil de aprender (incluso con un equipo Quantum) porque se trata de una distribución a través de un gran número exponencial de configuraciones.
Se pueden aprender cantidades como la energía del estado de la base.
Por ejemplo, si $ \ket{\psi} $ es cualquier estado de Quantum puro, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} proporciona la energía media que el sistema tiene en ese estado.
Después, el estado de la base es el estado que proporciona el valor más pequeño. Como resultado, la elección de un estado lo más cercano posible al estado de la base de valor real es fundamental para calcular la energía directamente (como se hace en eigensolverss de variación) o a través de la estimación de la fase.

Hartree – Fock teoría ofrece una manera sencilla de construir el estado inicial de los sistemas Quantum. Produce una única aproximación determinante de Slater al estado de la base de un sistema Quantum. Para ello, encuentra un giro en el espacio de Fock que minimiza la energía del estado de la conexión. En concreto, para un sistema de $N $ electrones, el método realiza la rotación \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} con un anti-Hermitian (es decir, $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $. Se debe observar que la matriz $u $ representa las rotaciones orbitales y $ \widetilde{a} ^ \ dagger_j $ y $ \widetilde{a} _j $ representan los operadores de creación y Annihilation para los electrones que ocupan Hartree – Fock molecular.


La matriz $u $ está optimizada para minimizar la energía esperada $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket {0} $. Aunque estos problemas de optimización pueden ser genéricos, en la práctica, el algoritmo Hartree – Fock tiende a converger rápidamente en una solución casi óptima al problema de optimización, especialmente en el caso de moléculas de Shell cerrado en las geometrías de equilibrio. Podemos especificar estos Estados como una instancia del `FermionWavefunction` objeto. Por ejemplo, se crea una instancia del estado $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ en la biblioteca de química como se indica a continuación.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
También es posible indexar funciones de onda con `SpinOrbital` índices y, a continuación, convertir estos índices en enteros de la manera siguiente.
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

El estado de Hartree-Fock también puede reconstruirse a partir de un `FermionHamiltonian`  como se indica a continuación.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Sin embargo, la obtención de resultados precisos, especialmente para sistemas fuertemente correlacionados, requiere Estados Quantum que vayan más allá de Hartree – Fock teoría.
