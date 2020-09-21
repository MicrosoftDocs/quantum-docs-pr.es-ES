---
title: Segunda cuantificación
description: Obtenga información sobre el segundo enfoque de cuantificación para modelar estructuras electrónicas en la programación de Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835815"
---
# <a name="second-quantization"></a>Segunda cuantificación

La segunda cuantificación examina el problema de la estructura electrónica a través de una lente diferente.
En lugar de asignar a cada uno de los $N _e $ electrones a un estado específico (o orbital), la segunda cuantificación realiza un seguimiento de cada orbital y almacena si hay un electrones presente en cada uno de ellos y, al mismo tiempo, garantiza automáticamente las propiedades de simetría de la función de onda correspondiente.
Esto es importante porque permite que se especifiquen modelos de química Quantum sin tener que preocuparse por symmetrizing el estado de entrada (como se requiere para fermions) y también porque la segunda cuantificación permite simular tales modelos con pequeños equipos Quantum.

Como ejemplo de segunda cuantificación en acción, supongamos que $ \ psi_0 \cdots \ psi_ {N-1} $ son un conjunto orthonormal de órbitas espaciales.
Estas órbitas se eligen para representar el sistema de la forma más precisa posible en el conjunto de bases finitas.
Un ejemplo común de estas órbitas son las órbitas atómicas que forman un eigenbasis para el átomo de hidrógeno.
Dado que los electrones tienen dos Estados de giro, se pueden Crammed dos electrones en cada uno de ellos.
Es decir, los Estados de base válidos son de la forma $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $, donde $ \uparrow $ y $ \downarrow $ son etiquetas que especifican los dos eigenstates del grado de giro de libertad.
Este índice combinado de $ (j, \sigma) $ para $ \sigma \en \{ \uparrow, \downarrow \} $ se denomina giro-orbital porque almacena tanto el espacial como el grado de giro de libertad.
En la biblioteca de química, las órbitas giradas se almacenan en una `SpinOrbital` estructura de datos y se crean como se indica a continuación.

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

Esto significa que se puede pensar formalmente en la base de la función de giro y espacial de la función de onda como $ \ psi_ {0} \cdots \ psi_ {2N-1} $, donde cada uno de los índices es ahora una enumeración de $ (j, \sigma) $.
Una posible enumeración es $g (j, \sigma) = j + N\sigma ' $.
Otra posible enumeración es $h (j, \sigma) = 2 * j + \sigma $.
La biblioteca de química de Quantum puede usar estas convenciones, y se pueden crear instancias de las órbitas en una codificación de este tipo, como se indica a continuación.

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

En el caso de los sistemas fermionic, el principio de exclusión Pauli impide que más de un electrones esté presente en cualquier giro orbital al mismo tiempo.
Esto significa que se pueden escribir los dos Estados válidos para $ \ psi_1 $ como \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket _ {0} 1 & \text{if $ \ psi_1 $ no está ocupado,} \\\
\ket _ {1} 1 & \text{if $ \ psi_1 $ está ocupado.} \end{Cases} \end{Equation} esta codificación es excelente para los equipos Quantum porque significa que podemos almacenar la profesión electrónica como un solo bit de Quantum.

Los Estados de ocupación para las órbitas $2N $ Spin se pueden almacenar de manera similar en $2N $ qubits.
Por ejemplo, si $N = $2, el estado $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $

se correspondería con los giros de giro $1 $ y $2 $ ocupados con el resto vacío.
Del mismo modo, el estado $ $ \ket {0} \equiv \ket {0} _ {0} {0} \cdots \ket_{N-1}, $ $

no tiene electrones y se conoce como "estado de vacuuming".

Un bonito efecto secundario de la segunda cuantificación es que ya no es necesario realizar un seguimiento explícito de la antisimetría del estado de Quantum.
Esto se debe a que, como veremos, la antisimetría del estado se representa en su lugar a través de las reglas antimutación de los operadores que crean y destruyen profesiones electrónicas de un giro orbital.

## <a name="fermionic-operators"></a>Operadores Fermionic

Los dos operadores fundamentales que actúan en los vectores de base de segundo cuantificado se conocen como operadores de creación y Annihilation.
Estos operadores insertan o destruyen electrones en una ubicación determinada.
Se indican $a ^ \ dagger_j $ y $a _j $ respectivamente.

Por ejemplo, \begin{Align} a ^ \ dagger_1 \ket _ {0} 1 = \ket _ {1} 1, \quad a ^ \ dagger_1 \ket _ {1} 1 = 0, \quad a_1 \ket _ {0} 1 = 0, \quad a_1 \ket _ {1} 1 = \ket _ {0} 1.
\end{align} tenga en cuenta que en este caso $a ^ \ dagger_1 \ket _ 1 = 0 $ y $a _ 1 _ 1 _ 1 _ 1 _ 1 {1} {0} $ yield el vector cero no $ \ket _ {0} 1.
Por lo tanto, estos operadores no son Hermitian ni unitarios.
Se representan los operadores de creación y Annihilation generales con el <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> tipo.
Por ejemplo, un único operador de creación se representa como sigue.

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

También puede usar estos operadores para expresar $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.
$ $ Esta secuencia de operadores se construirá dentro de la biblioteca de simulación de Hamiltonian con código C# que es similar al caso orbital de un solo giro que se ha considerado anteriormente:
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

En el caso de un sistema de $k $ fermions, en la segunda cuantificación, la acción del operador de creación $a ^ \ dagger_i $ viene determinada por $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ y $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ where $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mide el número total de fermions que se encuentran en el estado de una única partícula y que tienen un índice $j < i $.

Un tercer operador también se usa a menudo en la segunda representación cuantificada.
Este operador se conoce como operador de número y se define mediante \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} este operador cuenta la ocupación de un giro orbital determinado, que es decir \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _I.
\end{align} similar a los `FermionTerm` ejemplos anteriores, este operador Number se construye como se indica a continuación.
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

No obstante, surge un detalle al usar operadores de creación o Annihilation en sistemas fermionic.
Es necesario que cualquier estado de Quantum válido sea antisimétrico en el intercambio de etiquetas.
Esto significa que $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .
$ $ Estos operadores se consideran "anti-dismute" y, en general, para cualquier $i, j $ tenemos que \begin{Align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{align}, por lo tanto, las dos <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instancias siguientes se consideran inequivalentes
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

El requisito de que cada uno de los operadores de creación anti-dimute significa que el uso de una segunda representación cuantificada evita los desafíos a los que se enfrenta la antisimetría de fermions.
En su lugar, el desafío vuelve a emerger en nuestra definición de los operadores de creación. 

Con las reglas antimutación, algunas `LadderSequence` instancias corresponden realmente a la misma secuencia de operadores fermionic, a veces hasta un signo menos.
Por ejemplo, considere Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
Esto nos motiva a definir una ordenación canónica para cada `FermionTerm` .
Any `FermionTerm` se coloca automáticamente en orden canónico como se indica a continuación.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Second-cuantificado Fermionic Hamiltonian

Es posible que sea insorprendente que los Hamiltonian de los [modelos de Quantum para sistemas electrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) se puedan escribir en términos de creación y de operadores de Annihilation.
En concreto, si $ \psi \_ j $ son las órbitas de giro que forman la base

\begin{Equation} \hat{H} = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {PQRS} h \_ {PQRS} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + H \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation} donde $h \_ {\textrm NUC} $ es la energía nuclear (que es una constante en la aproximación de Oppenheimer).

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}

donde $V (x) $ es el potencial del campo medio y

\begin{align} h \_ {PQRS} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ etiqueta {EQ: Integrals} \end{align}

Los términos $h \_ {pq} $ se conocen como enteros de un solo electrones porque todos estos términos solo afectan a los electrones únicos y, de forma similar $h \_ {PQRS} $, son los enteros de dos electrones.
Se denominan enteros porque el cálculo de los valores de estos coeficientes requiere un entero.
Los términos de un electrones describen la energía cinética de los electrones individuales y sus interacciones con los campos eléctricos de los núcleos.
Los enteros de dos electrones por otro lado describen las interacciones entre los electrones.

Una Intuition para lo que significan estos términos se puede obtener de los operadores de creación y de Annihilation que componen cada uno de ellos.
Por ejemplo, $h _ {pq} a ^ \ dagger_p a_q $ describe el salto de electrones desde el giro orbital $q $ hasta el giro orbital $p $.
Del mismo modo, el término $h _ {PQRS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (para DISTINCT $p, q, r, s $) describe dos electrones en giros de giro $r $ y $s $ de dispersión y terminan en giros de giro $p $ y $q $.
Si $r = q $ y $p = s $ $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ proporciona la penalización energética asociada a los dos electrones cercanos entre sí, pero no describe un proceso dinámico.

Podríamos representar este Hamiltonians mediante la `FermionHamiltonian` clase, que es esencialmente una lista que contiene todas las instancias deseadas `FermionTerm` .
Como Hamiltonians se Hermitian por definición, los términos se indexan con el tipo más especializado `HermitianFermionTerm` que también usa la simetría Hermitian al comprobar si los términos son equivalentes.

Vamos a crear algunos ejemplos ilustrativos.
Considere Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
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
Podemos simplificar esta construcción con el hecho de que los operadores Hamiltonian son operadores Hermitian.
Cuando se agregan términos a Hamiltonian con `Add` , se supone que cualquier término que no sea de Hermitian como `fermionTerm0` se empareja con su Hermitian conjugado.
Por lo tanto, el siguiente fragmento de código también representa el mismo Hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Mediante el uso de las reglas antimutación, algunas `FermionTerm` instancias de Hamiltonian corresponden realmente a la misma secuencia de operadores fermionic, a veces hasta un signo menos.
Por ejemplo, considere el Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, que es una suma de los términos que se han creado anteriormente.
Es posible que no siempre sea evidente para el usuario que se trata de términos equivalentes, por lo que se pueden agregar al Hamiltonian por separado.
Como alternativa, puede que le interese modificar los términos ya existentes en el Hamiltonian.
En estos casos, es posible que combinemos términos equivalentes como se indica a continuación.
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
Mediante la combinación de coeficientes de términos equivalentes, se reduce el número total de términos en el Hamiltonian.
Más adelante, esto reduce el número de puertas de Quantum necesarias para simular el Hamiltonian.

### <a name="internal-representation"></a>Representación interna

Un Hamiltonian de fermionic con interacciones de uno y dos cuerpos se representa en la segunda notación cuantificada como

$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.
\end{align} $ $

En esta notación, hay como máximo $N ^ 2 + N ^ 4 $ coeficientes.
Sin embargo, muchos de estos coeficientes se pueden recopilar, ya que se corresponden con el mismo operador.
Por ejemplo, en el caso de $p, q, r, s $ son índices distintos, podemos usar las reglas antimutación para mostrar que: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {s} a \_ \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} \_ \_ a {s} a {r}.
$$

Además, como $H $ is Hermitian, cada operador fermionic que no sea Hermitian, por ejemplo, $h \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, tiene un conjugado Hermitian que también se encuentra en $H $. Para indexar de forma única los grupos de términos que se caracterizan por estos Symmetries, definimos un orden canónico en los índices $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ de cualquier secuencia de operadores $n + m $ fermionic $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as siguiente:
-   Todos los operadores de creación $a ^ \dagger \_ {i \_ \cdot} $ se colocan antes de todos los operadores de Annihilation $a \_ {j \_ \cdot} $.
-   Todos los índices de operadores de creación se ordenan en orden ascendente, es decir, $i \_ 1< i \_ 2< \cdots < i \_ n $.
-   Todos los índices de operador de Annihilation se ordenan en orden descendente, es decir, $j \_ 1> j \_ 2 \cdots > j \_ m $.
-   El índice situado más a la izquierda es menor o igual que el índice situado más a la derecha, es decir, $i \_ 1 \ le j \_ m $.

Vamos a identificar este conjunto de índices ordenados de forma canónica como $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \en S \_ {n, m}.
\end{align} $ $

Con esta ordenación canónica, fermionic Hamiltonian se puede expresar como $ $ \begin{align} H = \sum \_ {(p, q) \En S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \en s \_ {2,2} } H ' \_ {PQRS} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ con integrales de una y dos electrones adaptada adecuadamente $h ' \_ {pq} $ y $h ' \_ {PQRS} $, respectivamente.

