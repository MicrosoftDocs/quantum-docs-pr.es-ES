---
title: Segunda cuantificación
description: Obtenga información sobre el segundo enfoque de cuantificación para modelar estructuras electrónicas en la programación de Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: a08e20d5b53aa97cb12ead0dc3a36069d0ec5df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858831"
---
# <a name="second-quantization"></a><span data-ttu-id="9b3c1-103">Segunda cuantificación</span><span class="sxs-lookup"><span data-stu-id="9b3c1-103">Second Quantization</span></span>

<span data-ttu-id="9b3c1-104">La segunda cuantificación examina el problema de la estructura electrónica a través de una lente diferente.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="9b3c1-105">En lugar de asignar a cada uno de los $N _e $ electrones a un estado específico (o orbital), la segunda cuantificación realiza un seguimiento de cada orbital y almacena si hay un electrones presente en cada uno de ellos y, al mismo tiempo, garantiza automáticamente las propiedades de simetría de la función de onda correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="9b3c1-106">Esto es importante porque permite que se especifiquen modelos de química Quantum sin tener que preocuparse por symmetrizing el estado de entrada (como se requiere para fermions) y también porque la segunda cuantificación permite simular tales modelos con pequeños equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="9b3c1-107">Como ejemplo de segunda cuantificación en acción, supongamos que $ \ psi_0 \cdots \ psi_ {N-1} $ son un conjunto orthonormal de órbitas espaciales.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="9b3c1-108">Estas órbitas se eligen para representar el sistema de la forma más precisa posible en el conjunto de bases finitas.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="9b3c1-109">Un ejemplo común de estas órbitas son las órbitas atómicas que forman un eigenbasis para el átomo de hidrógeno.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="9b3c1-110">Dado que los electrones tienen dos Estados de giro, se pueden Crammed dos electrones en cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="9b3c1-111">Es decir, los Estados de base válidos son de la forma $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $, donde $ \uparrow $ y $ \downarrow $ son etiquetas que especifican los dos eigenstates del grado de giro de libertad.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="9b3c1-112">Este índice combinado de $ (j, \sigma) $ para $ \sigma \en \{ \uparrow, \downarrow \} $ se denomina giro-orbital porque almacena tanto el espacial como el grado de giro de libertad.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="9b3c1-113">En la biblioteca de química, las órbitas giradas se almacenan en una `SpinOrbital` estructura de datos y se crean como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="9b3c1-114">Esto significa que se puede pensar formalmente en la base de la función de giro y espacial de la función de onda como $ \ psi_ {0} \cdots \ psi_ {2N-1} $, donde cada uno de los índices es ahora una enumeración de $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="9b3c1-115">Una posible enumeración es $g (j, \sigma) = j + N\sigma ' $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="9b3c1-116">Otra posible enumeración es $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="9b3c1-117">La biblioteca de química de Quantum puede usar estas convenciones, y se pueden crear instancias de las órbitas en una codificación de este tipo, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="9b3c1-118">En el caso de los sistemas fermionic, el principio de exclusión Pauli impide que más de un electrones esté presente en cualquier giro orbital al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="9b3c1-119">Esto significa que se pueden escribir los dos Estados válidos para $ \ psi_1 $ como \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket _ {0} 1 & \text{if $ \ psi_1 $ no está ocupado,} </span><span class="sxs-lookup"><span data-stu-id="9b3c1-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="9b3c1-120">\ket _ {1} 1 & \text{if $ \ psi_1 $ está ocupado.}</span><span class="sxs-lookup"><span data-stu-id="9b3c1-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="9b3c1-121">\end{Cases} \end{Equation} esta codificación es excelente para los equipos Quantum porque significa que podemos almacenar la profesión electrónica como un solo bit de Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="9b3c1-122">Los Estados de ocupación para las órbitas $2N $ Spin se pueden almacenar de manera similar en $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="9b3c1-123">Por ejemplo, si $N = $2, el estado $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="9b3c1-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="9b3c1-124">se correspondería con los giros de giro $1 $ y $2 $ ocupados con el resto vacío.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="9b3c1-125">Del mismo modo, el estado $ $ \ket {0} \equiv \ket {0} _{0} {0} \cdots \ket_{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="9b3c1-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="9b3c1-126">no tiene electrones y se conoce como "estado de vacuuming".</span><span class="sxs-lookup"><span data-stu-id="9b3c1-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="9b3c1-127">Un bonito efecto secundario de la segunda cuantificación es que ya no es necesario realizar un seguimiento explícito de la antisimetría del estado de Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="9b3c1-128">Esto se debe a que, como veremos, la antisimetría del estado se representa en su lugar a través de las reglas antimutación de los operadores que crean y destruyen profesiones electrónicas de un giro orbital.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="9b3c1-129">Operadores Fermionic</span><span class="sxs-lookup"><span data-stu-id="9b3c1-129">Fermionic operators</span></span>

<span data-ttu-id="9b3c1-130">Los dos operadores fundamentales que actúan en los vectores de base de segundo cuantificado se conocen como operadores de creación y Annihilation.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="9b3c1-131">Estos operadores insertan o destruyen electrones en una ubicación determinada.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="9b3c1-132">Se indican $a ^ \ dagger_j $ y $a _j $ respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="9b3c1-133">Por ejemplo, \begin{Align} a ^ \ dagger_1 \ket _ {0} 1 = \ket _ {1} 1, \quad a ^ \ dagger_1 \ket _ {1} 1 = 0, \quad a_1 \ket _ {0} 1 = 0, \quad a_1 \ket _ {1} 1 = \ket _ {0} 1.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="9b3c1-134">\end{align} tenga en cuenta que en este caso $a ^ \ dagger_1 \ket _ 1 = 0 $ y $a _ 1 _ 1 _ 1 _ 1 _ 1 {1} {0} $ yield el vector cero no $ \ket _ {0} 1.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="9b3c1-135">Por lo tanto, estos operadores no son Hermitian ni unitarios.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="9b3c1-136">Se representan los operadores de creación y Annihilation generales con el <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> tipo.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="9b3c1-137">Por ejemplo, un único operador de creación se representa como sigue.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="9b3c1-138">También puede usar estos operadores para expresar $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="9b3c1-139">$ $ Esta secuencia de operadores se construirá dentro de la biblioteca de simulación de Hamiltonian con código C# que es similar al caso orbital de un solo giro que se ha considerado anteriormente:</span><span class="sxs-lookup"><span data-stu-id="9b3c1-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="9b3c1-140">En el caso de un sistema de $k $ fermions, en la segunda cuantificación, la acción del operador de creación $a ^ \ dagger_i $ viene determinada por $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ y $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ where $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mide el número total de fermions que se encuentran en el estado de una única partícula y que tienen un índice $j < i $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="9b3c1-141">Un tercer operador también se usa a menudo en la segunda representación cuantificada.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="9b3c1-142">Este operador se conoce como operador de número y se define mediante \begin{Equation} n_i = a ^ \ dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="9b3c1-143">\end{Equation} este operador cuenta la ocupación de un giro orbital determinado, que es decir \begin{align} n_i \ket {0} _i &= 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="9b3c1-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="9b3c1-144">n_i \ket {1} _i &= \ket {1} _I.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="9b3c1-145">\end{align} similar a los `FermionTerm` ejemplos anteriores, este operador Number se construye como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="9b3c1-146">No obstante, surge un detalle al usar operadores de creación o Annihilation en sistemas fermionic.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="9b3c1-147">Es necesario que cualquier estado de Quantum válido sea antisimétrico en el intercambio de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="9b3c1-148">Esto significa que $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="9b3c1-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="9b3c1-149">$ $ Estos operadores se consideran "anti-dismute" y, en general, para cualquier $i, j $ tenemos que \begin{Align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="9b3c1-150">\end{align}, por lo tanto, las dos <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instancias siguientes se consideran inequivalentes</span><span class="sxs-lookup"><span data-stu-id="9b3c1-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="9b3c1-151">El requisito de que cada uno de los operadores de creación anti-dimute significa que el uso de una segunda representación cuantificada evita los desafíos a los que se enfrenta la antisimetría de fermions.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="9b3c1-152">En su lugar, el desafío vuelve a emerger en nuestra definición de los operadores de creación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="9b3c1-153">Con las reglas antimutación, algunas `LadderSequence` instancias corresponden realmente a la misma secuencia de operadores fermionic, a veces hasta un signo menos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="9b3c1-154">Por ejemplo, considere Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="9b3c1-155">Esto nos motiva a definir una ordenación canónica para cada `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="9b3c1-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="9b3c1-156">Any `FermionTerm` se coloca automáticamente en orden canónico como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="9b3c1-157">Second-Quantized Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="9b3c1-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="9b3c1-158">Es posible que sea insorprendente que los Hamiltonian de los [modelos de Quantum para sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) se puedan escribir en términos de creación y de operadores de Annihilation.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="9b3c1-159">En concreto, si $ \psi \_ j $ son las órbitas de giro que forman la base</span><span class="sxs-lookup"><span data-stu-id="9b3c1-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="9b3c1-160">\begin{Equation} \hat{H} = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {PQRS} h \_ {PQRS} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + H \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation} donde $h \_ {\textrm NUC} $ es la energía nuclear (que es una constante en la aproximación Born-Oppenheimer) y</span><span class="sxs-lookup"><span data-stu-id="9b3c1-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="9b3c1-161">\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="9b3c1-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="9b3c1-162">donde $V (x) $ es el potencial del campo medio y</span><span class="sxs-lookup"><span data-stu-id="9b3c1-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="9b3c1-163">\begin{align} h \_ {PQRS} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ etiqueta {EQ: Integrals} \end{align}</span><span class="sxs-lookup"><span data-stu-id="9b3c1-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="9b3c1-164">Los términos $h \_ {pq} $ se conocen como enteros de un solo electrones porque todos estos términos solo afectan a los electrones únicos y, de forma similar $h \_ {PQRS} $, son los enteros de dos electrones.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="9b3c1-165">Se denominan enteros porque el cálculo de los valores de estos coeficientes requiere un entero.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="9b3c1-166">Los términos de un electrones describen la energía cinética de los electrones individuales y sus interacciones con los campos eléctricos de los núcleos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="9b3c1-167">Los enteros de dos electrones por otro lado describen las interacciones entre los electrones.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="9b3c1-168">Una Intuition para lo que significan estos términos se puede obtener de los operadores de creación y de Annihilation que componen cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="9b3c1-169">Por ejemplo, $h _ {pq} a ^ \ dagger_p a_q $ describe el salto de electrones desde el giro orbital $q $ hasta el giro orbital $p $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="9b3c1-170">Del mismo modo, el término $h _ {PQRS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (para DISTINCT $p, q, r, s $) describe dos electrones en giros de giro $r $ y $s $ de dispersión y terminan en giros de giro $p $ y $q $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="9b3c1-171">Si $r = q $ y $p = s $ $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ proporciona la penalización energética asociada a los dos electrones cercanos entre sí, pero no describe un proceso dinámico.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="9b3c1-172">Podríamos representar este Hamiltonians mediante la `FermionHamiltonian` clase, que es esencialmente una lista que contiene todas las instancias deseadas `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="9b3c1-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="9b3c1-173">Como Hamiltonians se Hermitian por definición, los términos se indexan con el tipo más especializado `HermitianFermionTerm` que también usa la simetría Hermitian al comprobar si los términos son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="9b3c1-174">Vamos a crear algunos ejemplos ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="9b3c1-175">Considere Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="9b3c1-176">Podemos simplificar esta construcción con el hecho de que los operadores Hamiltonian son operadores Hermitian.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="9b3c1-177">Cuando se agregan términos a Hamiltonian con `Add` , se supone que cualquier término que no sea de Hermitian como `fermionTerm0` se empareja con su Hermitian conjugado.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="9b3c1-178">Por lo tanto, el siguiente fragmento de código también representa el mismo Hamiltonian:</span><span class="sxs-lookup"><span data-stu-id="9b3c1-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="9b3c1-179">Mediante el uso de las reglas antimutación, algunas `FermionTerm` instancias de Hamiltonian corresponden realmente a la misma secuencia de operadores fermionic, a veces hasta un signo menos.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="9b3c1-180">Por ejemplo, considere el Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, que es una suma de los términos que se han creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="9b3c1-181">Es posible que no siempre sea evidente para el usuario que se trata de términos equivalentes, por lo que se pueden agregar al Hamiltonian por separado.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="9b3c1-182">Como alternativa, puede que le interese modificar los términos ya existentes en el Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="9b3c1-183">En estos casos, es posible que combinemos términos equivalentes como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="9b3c1-184">Mediante la combinación de coeficientes de términos equivalentes, se reduce el número total de términos en el Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="9b3c1-185">Más adelante, esto reduce el número de puertas de Quantum necesarias para simular el Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="9b3c1-186">Representación interna</span><span class="sxs-lookup"><span data-stu-id="9b3c1-186">Internal Representation</span></span>

<span data-ttu-id="9b3c1-187">Un Hamiltonian de fermionic con interacciones de uno y dos cuerpos se representa en la segunda notación cuantificada como</span><span class="sxs-lookup"><span data-stu-id="9b3c1-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="9b3c1-188">$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="9b3c1-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9b3c1-189">\end{align} $$</span></span>

<span data-ttu-id="9b3c1-190">En esta notación, hay como máximo $N ^ 2 + N ^ 4 $ coeficientes.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="9b3c1-191">Sin embargo, muchos de estos coeficientes se pueden recopilar, ya que se corresponden con el mismo operador.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="9b3c1-192">Por ejemplo, en el caso de $p, q, r, s $ son índices distintos, podemos usar las reglas antimutación para mostrar que: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {s} a \_ \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} \_ \_ a {s} a {r}.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="9b3c1-193">Además, como $H $ is Hermitian, cada operador fermionic que no sea Hermitian, por ejemplo, $h \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, tiene un conjugado Hermitian que también se encuentra en $H $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="9b3c1-194">Para indexar de forma única los grupos de términos que se caracterizan por estos Symmetries, definimos un orden canónico en los índices $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ de cualquier secuencia de operadores $n + m $ fermionic $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b3c1-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="9b3c1-195">Todos los operadores de creación $a ^ \dagger \_ {i \_ \cdot} $ se colocan antes de todos los operadores de Annihilation $a \_ {j \_ \cdot} $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="9b3c1-196">Todos los índices de operadores de creación se ordenan en orden ascendente, es decir, $i \_ 1< i \_ 2< \cdots < i \_ n $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="9b3c1-197">Todos los índices de operador de Annihilation se ordenan en orden descendente, es decir, $j \_ 1> j \_ 2 \cdots > j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="9b3c1-198">El índice situado más a la izquierda es menor o igual que el índice situado más a la derecha, es decir, $i \_ 1 \ le j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="9b3c1-199">Vamos a identificar este conjunto de índices ordenados de forma canónica como $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \en S \_ {n, m}.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="9b3c1-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9b3c1-200">\end{align} $$</span></span>

<span data-ttu-id="9b3c1-201">Con esta ordenación canónica, fermionic Hamiltonian se puede expresar como $ $ \begin{align} H = \sum \_ {(p, q) \En S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \en s \_ {2,2} } H ' \_ {PQRS} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ con integrales de una y dos electrones adaptada adecuadamente $h ' \_ {pq} $ y $h ' \_ {PQRS} $, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9b3c1-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

