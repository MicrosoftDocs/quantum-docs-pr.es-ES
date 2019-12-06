---
title: Simulación de Hamiltonian Dynamics | Microsoft Docs
description: Simulación de documentos conceptuales de Hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864464"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="2e7b8-103">Simulación de Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="2e7b8-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="2e7b8-104">Una vez que Hamiltonian se expresa como una suma de los operadores elementales, la dinámica se puede compilar en operaciones fundamentales de la puerta mediante un host de técnicas conocidas.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="2e7b8-105">Entre los tres enfoques eficaces se incluyen las fórmulas Trotter – Suzuki, las combinaciones lineales de unitaries y qubitization.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="2e7b8-106">A continuación se explican estos tres enfoques y se proporcionan ejemplos concretos de preguntas y respuestas sobre cómo implementar estos métodos con la biblioteca de simulación de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="2e7b8-107">Trotter – Suzuki fórmulas)</span><span class="sxs-lookup"><span data-stu-id="2e7b8-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="2e7b8-108">La idea detrás de las fórmulas de Trotter – Suzuki es sencilla: expresar Hamiltonian como una suma de fácil simulación de Hamiltonians y, después, aproximar la evolución total como una secuencia de estas evoluciones más sencillas.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="2e7b8-109">En concreto, deje $H = \ sum_ {j = 1} ^ m H_j $ sea el Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="2e7b8-110">Después, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $ que es decir que, si $t \ll $1, el error en esta aproximación se vuelve insignificante.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="2e7b8-111">Tenga en cuenta que si $e ^ {-i H t} $ eran un valor exponencial normal, el error en esta aproximación no se $O (m ^ 2 t ^ 2) $: sería cero.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="2e7b8-112">Este error se produce porque $e ^ {-iHt} $ es un operador exponencial y, como resultado, se produce un error al usar esta fórmula debido al hecho de que el $H _j $ Terms no se desactivan (*es decir*, $H _J H_k \ne H_k H_j $ en general).</span><span class="sxs-lookup"><span data-stu-id="2e7b8-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="2e7b8-113">Si $t $ es grande, se pueden seguir usando las fórmulas Trotter – Suzuki para simular la dinámica con precisión dividiendo en una secuencia de pasos breves.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="2e7b8-114">Deje que $r $ sea el número de pasos realizados en la evolución de la hora.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="2e7b8-115">Después, tenemos $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r). $ $, que implica que si $r $ se escala como $m ^ 2 t ^ 2/\ épsilon $, el error se puede hacer como máximo $ \epsilon $ para cualquier $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="2e7b8-116">Se pueden crear aproximaciones más precisas mediante la construcción de una secuencia de exponenciales de operador de modo que se cancelen los términos de error.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="2e7b8-117">La fórmula más sencilla, la fórmula Trotter simétrica o la división Strang, tiene el formato $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3). $ $ que se puede convertir en menos de $ \epsilon $ para cualquier $ \epsilon > 0 $ eligiendo $r $ para escalar como $m ^ {3/2} t ^ {3/2}/\sqrt {\ épsilon} $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="2e7b8-118">Incluso las fórmulas de Trotter de orden superior se pueden construir en función de $U 1 _ 1 $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="2e7b8-119">La más simple es la siguiente fórmula de cuarto orden: introducido originalmente por Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $ donde $s _ 1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="2e7b8-120">En general, las fórmulas de orden superior arbitrariamente se pueden construir de forma similar. sin embargo, los costos derivados del uso de integradores más complejos a menudo compensan las ventajas más allá del cuarto orden en lo que se refiere a los problemas prácticos.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="2e7b8-121">Para hacer que las estrategias anteriores funcionen, es necesario tener un método para simular una clase ancha de $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="2e7b8-122">La familia más sencilla de Hamiltonians y, posiblemente, lo más útil, que podríamos usar aquí son los operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="2e7b8-123">Los operadores de Pauli se pueden simular fácilmente porque se pueden convertir en diagonal mediante operaciones de Clifford (que son puertas estándar en la informática Quantum).</span><span class="sxs-lookup"><span data-stu-id="2e7b8-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="2e7b8-124">Además, una vez que se han diagonal, su vectores propios se puede encontrar calculando la paridad del qubits en el que actúan.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="2e7b8-125">Por ejemplo, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ where $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="2e7b8-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="2e7b8-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="2e7b8-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="2e7b8-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="2e7b8-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="2e7b8-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="2e7b8-129">$ $ Aquí, $e ^ {-iHt} \ket{00} = e ^ {IT} \ket{00}$ y $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, que se puede ver directamente como consecuencia del hecho de que la paridad de $0 $ es $0 $ mientras que la paridad de la cadena de bits $1 $ es $1 $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="2e7b8-130">Los exponenciales de los operadores Pauli se pueden implementar directamente en Q # mediante la operación <xref:microsoft.quantum.primitive.exp>:</span><span class="sxs-lookup"><span data-stu-id="2e7b8-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="2e7b8-131">En el caso de Fermionic Hamiltonians, la [descomposición de Jordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) asigna la Hamiltonian a una suma de operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="2e7b8-132">Esto significa que el enfoque anterior se puede adaptar fácilmente a la simulación de química.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="2e7b8-133">En lugar de recorrer manualmente los términos de Pauli en la representación Jordania-Wigner, a continuación se muestra un ejemplo sencillo de cómo sería la ejecución de este tipo de simulación dentro de la química.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="2e7b8-134">Nuestro punto de partida es una [codificación de Jordania – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) de la Hamiltonian de Fermionic, expresada en el código como una instancia de la clase `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="2e7b8-135">Este formato de la representación Jordania – Wigner que son consumibles por los algoritmos de simulación de Q # es un tipo definido por el usuario `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="2e7b8-136">En Q #, este formato se pasa a una función de comodidad `TrotterStepOracle` que devuelve un operador que aproxima la evolución del tiempo mediante el Trotter, Suzuki integrador, además de otros parámetros necesarios para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

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

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="2e7b8-137">Lo importante es que esta implementación Aplique algunas optimizaciones que se describen en [simulación de la estructura electrónica Hamiltonians con equipos Quantum](https://arxiv.org/abs/1001.3855) y la mejora de los [algoritmos Quantum para la química Quantum](https://arxiv.org/abs/1403.1539) para minimizar el número de giros de un solo qubit necesarios, así como reducir los errores de simulación.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="2e7b8-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="2e7b8-138">Qubitization</span></span>

<span data-ttu-id="2e7b8-139">Qubitization es un enfoque alternativo a la simulación que usa ideas de los recorridos de Quantum para simular la dinámica de Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="2e7b8-140">Aunque qubitization requiere más qubits que las fórmulas de Trotter, el método promete una escala óptima con el tiempo de evolución y la tolerancia de errores.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="2e7b8-141">Por estos motivos, se ha convertido en un método favorable para simular Hamiltonian Dynamics en general y para resolver el problema de la estructura electrónica en particular.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="2e7b8-142">En un nivel alto, qubitization lo consigue a través de los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="2e7b8-143">En primer lugar, deje $H = \ sum_j h_j H_j $ para Hermitian $H _j $ y $h _j \ge $0.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="2e7b8-144">Mediante la realización de un par de reflejos, qubitization implementa un operador que es equivalente a $ $W = e ^ {\pm i \cos ^{-1}(H/| H | _ 1)}, $ $ where $ | H | _ 1 = \ sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="2e7b8-145">El paso siguiente implica transformar el vectores propios del operador de recorrido de $e ^ {i\pm \cos ^{-1}(E_k/| h | _ 1)} $, donde $E _k $ son los vectores propios de $H $ a $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="2e7b8-146">Esto puede lograrse mediante una variedad de métodos de transformación de valor singular de Quantum, incluido el [procesamiento de señales Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="2e7b8-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="2e7b8-147">Como alternativa, si solo se quieren cantidades estáticas (por ejemplo, la energía de estado de la base de Hamiltonian), basta con aplicar la [estimación de fase](xref:microsoft.quantum.libraries.characterization) directamente a $W $ para calcular la energía de estado de la toma de la toma de la toma de la derivación del resultado.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="2e7b8-148">Esto es importante porque permite que la transformación espectral se realice de forma individual en lugar de usar un método de transformación de valor singular singular.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="2e7b8-149">En un nivel más detallado, la implementación de qubitization requiere dos subrutinas que proporcionan las interfaces para el Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="2e7b8-150">A diferencia de los métodos Trotter – Suzuki, estas subrutinas son Quantum not clásico y su implementación necesitará usar logarítmicamente más qubits de lo que sería necesario para una simulación basada en Trotter.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="2e7b8-151">La primera subrutina Quantum que qubitization usa se denomina $ \operatorname{Select} $ y se promete producir \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} donde se supone que cada $H _j $ es Hermitian y unitario.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="2e7b8-152">Aunque esto puede parecer restrictivo, recuerde que los operadores de Pauli son Hermitian y unitario, por lo que las aplicaciones como la simulación de la química de Quantum se encuentran en este marco de trabajo de forma natural.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="2e7b8-153">La operación $ \operatorname{Select} $, quizás sorprendentemente, es realmente una operación de reflexión.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="2e7b8-154">Esto se puede considerar desde el hecho de que $ \operatorname{Select} ^ 2 \ les {j} \ket{\psi} = \ket{j} \ket{\psi} $, ya que cada $H _j $ es unitario y Hermitian y, por tanto, vectores propios $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="2e7b8-155">La segunda subrutina se denomina $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="2e7b8-156">Mientras que la operación de selección proporciona un medio para tener acceso coherente a cada uno de los términos de Hamiltonian $H _j $ la subrutina de preparación proporciona un método para obtener acceso a los coeficientes $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _ 1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="2e7b8-157">\end{Equation} a continuación, mediante el uso de una puerta de fase de control de multiplicación, vemos que $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="2e7b8-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="2e7b8-158">\ket{x} & \text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="2e7b8-159">La operación $ \operatorname{Prepare} $ no se usa directamente en qubitization, sino que se usa para implementar una reflexión sobre el estado que $ \operatorname{Prepare} $ crea $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="2e7b8-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2e7b8-160">\end{align} $$</span></span>

<span data-ttu-id="2e7b8-161">El operador Walk, $W $, se puede expresar en términos de las operaciones $ \operatorname{Select} $ y $R $ como $ $ W = \operatorname{Select} R, $ $ que se puede observar de nuevo para implementar un operador equivalente (hasta un isometría) para $e ^ {\pm i \cos ^{-1}(H/| h | _ 1)} $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="2e7b8-162">Estas subrutinas son fáciles de configurar en Q #.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="2e7b8-163">Como ejemplo, considere la simple qubit transversal-Ising Hamiltonian donde $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="2e7b8-164">En este caso, el código de preguntas y respuestas que implementaría la operación $ \operatorname{Select} $ se invoca mediante <xref:microsoft.quantum.canon.multiplexoperations>, mientras que la operación $ \operatorname{Prepare} $ se puede implementar mediante <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="2e7b8-165">Un ejemplo que implica la simulación del modelo de Hubbard puede encontrarse como un [ejemplo de preguntas y respuestas](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span><span class="sxs-lookup"><span data-stu-id="2e7b8-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="2e7b8-166">La especificación manual de estos pasos para problemas de química arbitrarios requeriría mucho esfuerzo, lo que se evita mediante la biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="2e7b8-167">De forma similar al algoritmo de simulación Trotter – Suzuki anterior, el `JordanWignerEncodingData` se pasa a la función de comodidad `QubitizationOracle` que devuelve el operador Walk, además de otros parámetros necesarios para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="2e7b8-168">Lo importante es que la implementación <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> es aplicable a Hamiltonians arbitrarios que se especifican como una combinación lineal de cadenas Pauli.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="2e7b8-169">Una versión optimizada para las simulaciones de química se invoca mediante <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="2e7b8-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="2e7b8-170">Esta versión está optimizada para minimizar el número de puertas T mediante técnicas descritas en [codificación de espectros electrónicos en circuitos Quantum con complejidad T lineal](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="2e7b8-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
