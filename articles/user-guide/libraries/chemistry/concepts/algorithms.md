---
title: Simulación de Hamiltonian Dynamics
description: Aprenda a usar las fórmulas de Trotter-Suzuki y qubitization para trabajar con simulaciones de Hamiltonian.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275931"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulación de Hamiltonian Dynamics

Una vez que Hamiltonian se expresa como una suma de los operadores elementales, la dinámica se puede compilar en operaciones fundamentales de la puerta mediante un host de técnicas conocidas.
Entre los tres enfoques eficaces se incluyen las fórmulas Trotter – Suzuki, las combinaciones lineales de unitaries y qubitization.
A continuación se explican estos tres enfoques y se proporcionan ejemplos concretos de preguntas y respuestas sobre cómo implementar estos métodos con la biblioteca de simulación de Hamiltonian.


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki fórmulas)
La idea detrás de las fórmulas de Trotter – Suzuki es sencilla: expresar Hamiltonian como una suma de fácil simulación de Hamiltonians y, después, aproximar la evolución total como una secuencia de estas evoluciones más sencillas.
En concreto, deje $H = \ sum_ {j = 1} ^ m H_j $ sea el Hamiltonian.
Después, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $ que es decir que, si $t \ll $1, el error en esta aproximación se vuelve insignificante.
Tenga en cuenta que si $e ^ {-i H t} $ eran un valor exponencial normal, el error en esta aproximación no se $O (m ^ 2 t ^ 2) $: sería cero.
Este error se produce porque $e ^ {-iHt} $ es un operador exponencial y, como resultado, se produce un error al usar esta fórmula debido al hecho de que el $H _j $ Terms no se desactivan (*es decir*, $H _J H_k \ne H_k H_j $ en general).

Si $t $ es grande, se pueden seguir usando las fórmulas Trotter – Suzuki para simular la dinámica con precisión dividiendo en una secuencia de pasos breves.
Deje que $r $ sea el número de pasos que se llevan a cabo en la evolución de tiempo, por lo que cada paso de tiempo se ejecuta para el tiempo $t/r $. Después, tenemos $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r). $ $, lo que implica que si $r $ se escala como $m ^ 2 t ^ 2/\ épsilon $, el error se puede realizar como máximo $ \epsilon $ para cualquier $ \epsilon>$0.

Se pueden crear aproximaciones más precisas mediante la construcción de una secuencia de exponenciales de operador de modo que se cancelen los términos de error.
La fórmula más sencilla, la fórmula Trotter-Suzuki, tiene el formato $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2) $ $ el error se puede realizar menos de $ \epsilon $ para cualquier $ \epsilon>$0. para ello, elija $r $ para escalar como $m ^ {3/2} t ^ {3/2}/\sqrt {\ épsilon} $.

Incluso las fórmulas de orden superior, específicamente ($ 2K $) TH-Order para $k>$0, se pueden crear de forma recursiva: $ $ U_ {2K} (t) = [U_ {2K-2} (s_k \~ t)] ^ 2 U_ {2K-2} ([1-4s_k] t) [U_ {2K-2} (s_k \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2K + 1}/r ^ {2K}), $ $ where $s _k = (4-4 ^ {1/(2K-1)}) ^ {-1} $.

La más simple es la siguiente fórmula de cuarto orden ($k = $2), introducida originalmente por Suzuki: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5T ^ 5/r ^ 4), $ $ Where $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
En general, las fórmulas de orden superior arbitrariamente se pueden construir de forma similar. sin embargo, los costos derivados del uso de integradores más complejos a menudo compensan las ventajas más allá del cuarto orden en lo que se refiere a los problemas prácticos.

Para hacer que las estrategias anteriores funcionen, es necesario tener un método para simular una clase ancha de $e ^ {-iH_j t} $.
La familia más sencilla de Hamiltonians y, posiblemente, lo más útil, que podríamos usar aquí son los operadores de Pauli.
Los operadores de Pauli se pueden simular fácilmente porque se pueden convertir en diagonal mediante operaciones de Clifford (que son puertas estándar en la informática Quantum).
Además, una vez que se han diagonal, su vectores propios se puede encontrar calculando la paridad del qubits en el que actúan.

Por ejemplo, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ where $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0\\\
        0 & e ^ {i t} & 0 & 0\\\
        0 & 0 & e ^ {IT} & 0\\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Aquí, $e ^ {-iHt} \ket {00} = e ^ {IT} \ket {00} $ y $e ^ {-iHt} \ket {01} = e ^ {-IT} \ket {01} $, que se puede ver directamente como consecuencia del hecho de que la paridad de $0 $ es $0 $ mientras que la paridad de la cadena de bits $1 $ es $1 $.

Los exponenciales de los operadores Pauli se pueden implementar directamente en Q # mediante la <xref:microsoft.quantum.intrinsic.exp> operación:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

En el caso de Fermionic Hamiltonians, la [descomposición de Jordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) asigna la Hamiltonian a una suma de operadores de Pauli.
Esto significa que el enfoque anterior se puede adaptar fácilmente a la simulación de química.
En lugar de recorrer manualmente los términos de Pauli en la representación Jordania-Wigner, a continuación se muestra un ejemplo sencillo de cómo sería la ejecución de este tipo de simulación dentro de la química.
Nuestro punto de partida es una [codificación de Jordania – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) de la Hamiltonian de Fermionic, expresada en el código como una instancia de la `JordanWignerEncoding` clase.

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

Este formato de la representación Jordania – Wigner que son consumibles por los algoritmos de simulación de Q # es un tipo definido por el usuario `JordanWignerEncodingData` .
Dentro de Q #, este formato se pasa a una función de conveniencia `TrotterStepOracle` que devuelve un operador que aproxima la evolución del tiempo mediante el Trotter, Suzuki integrador, además de otros parámetros necesarios para su ejecución.

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

Lo importante es que esta implementación Aplique algunas optimizaciones que se describen en [simulación de la estructura electrónica Hamiltonians con equipos Quantum](https://arxiv.org/abs/1001.3855) y la mejora de los [algoritmos Quantum para la química Quantum](https://arxiv.org/abs/1403.1539) para minimizar el número de giros de un solo qubit necesarios, así como reducir los errores de simulación.

## <a name="qubitization"></a>Qubitization

Qubitization es un enfoque alternativo a la simulación que usa ideas de los recorridos de Quantum para simular la dinámica de Quantum.
Aunque qubitization requiere más qubits que las fórmulas de Trotter, el método promete una escala óptima con el tiempo de evolución y la tolerancia de errores.
Por estos motivos, se ha convertido en un método favorable para simular Hamiltonian Dynamics en general y para resolver el problema de la estructura electrónica en particular.

En un nivel alto, qubitization lo consigue a través de los pasos siguientes.
En primer lugar, deje $H = \ sum_j h_j H_j $ para Hermitian $H _j $ y $h _j \ge $0.
Mediante la realización de un par de reflejos, qubitization implementa un operador que es equivalente a $ $W = e ^ {\pm i \cos ^ {-1} (H/| H | _ 1)}, $ $ where $ | H | _ 1 = \ sum_j | h_j | $.
El siguiente paso consiste en transformar el vectores propios del operador de recorrido de $e ^ {i\pm \cos ^ {-1} (E_k/| h | _ 1)} $, donde $E _k $ son los vectores propios de $H $ a $e ^ {-iE_k t} $.
Esto puede lograrse mediante una variedad de métodos de transformación de valor singular de Quantum, incluido el [procesamiento de señales Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Como alternativa, si solo se quieren cantidades estáticas (por ejemplo, la energía de estado de la base de Hamiltonian), basta con aplicar la [estimación de fase](xref:microsoft.quantum.libraries.characterization) directamente a $W $ para calcular la energía de estado de la toma de la toma de la toma de la derivación del resultado.
Esto es importante porque permite que la transformación espectral se realice de forma individual en lugar de usar un método de transformación de valor singular singular.

En un nivel más detallado, la implementación de qubitization requiere dos subrutinas que proporcionan las interfaces para el Hamiltonian.
A diferencia de los métodos Trotter – Suzuki, estas subrutinas son Quantum not clásico y su implementación necesitará usar logarítmicamente más qubits de lo que sería necesario para una simulación basada en Trotter.

La primera subrutina Quantum que qubitization usa se denomina $ \operatorname{Select} $ y se promete producir \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} donde se supone que cada $H _j $ es Hermitian y unitario.
Aunque esto puede parecer restrictivo, recuerde que los operadores de Pauli son Hermitian y unitario, por lo que las aplicaciones como la simulación de la química de Quantum se encuentran en este marco de trabajo de forma natural.
La operación $ \operatorname{Select} $, quizás sorprendentemente, es realmente una operación de reflexión.
Esto se puede considerar desde el hecho de que $ \operatorname{Select} ^ 2 \ les {j} \ket{\psi} = \ket{j} \ket{\psi} $, ya que cada $H _j $ es unitario y Hermitian y, por tanto, vectores propios $ \pm $1.

La segunda subrutina se denomina $ \operatorname{Prepare} $.
Mientras que la operación de selección proporciona un medio para tener acceso coherente a cada uno de los términos de Hamiltonian $H _j $ la subrutina de preparación proporciona un método para acceder a los coeficientes $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _ 1}} \ket{j}.
\end{Equation} a continuación, mediante el uso de una puerta de fase de control de multiplicación, vemos que $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \text{if} x = 0\\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

La operación $ \operatorname{Prepare} $ no se usa directamente en qubitization, sino que se usa para implementar una reflexión sobre el estado que $ \operatorname{Prepare} $ crea $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} .
\end{align} $ $

El operador de recorrido, $W $, se puede expresar en términos de las operaciones $ \operatorname{Select} $ y $R $ como $ $ W = \operatorname{Select} R, $ $ que se puede observar de nuevo para implementar un operador equivalente (hasta un isometría) a $e ^ {\pm i \cos ^ {-1} (H/| h | _ 1)} $.

Estas subrutinas son fáciles de configurar en Q #.
Como ejemplo, considere la simple qubit transversal-Ising Hamiltonian donde $H = X_1 + X_2 + Z_1 Z_2 $.
En este caso, se invoca a Q # Code que implementaría la operación $ \operatorname{Select} $ <xref:microsoft.quantum.canon.multiplexoperations> , mientras que la operación $ \operatorname{Prepare} $ se puede implementar mediante <xref:microsoft.quantum.preparation.preparearbitrarystate> .
Un ejemplo que implica la simulación del modelo de Hubbard puede encontrarse como un [ejemplo de preguntas y respuestas](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).

La especificación manual de estos pasos para problemas de química arbitrarios requeriría mucho esfuerzo, lo que se evita mediante la biblioteca de química.
De forma similar al algoritmo de simulación Trotter – Suzuki anterior, `JordanWignerEncodingData` se pasa a la función de conveniencia `QubitizationOracle` que devuelve el operador Walk, además de otros parámetros necesarios para su ejecución.

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

Lo importante <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> es que la implementación se aplica a Hamiltonians arbitrarios especificados como una combinación lineal de cadenas Pauli.
Una versión optimizada para las simulaciones de química se invoca mediante <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> .
Esta versión está optimizada para minimizar el número de puertas T mediante técnicas descritas en [codificación de espectros electrónicos en circuitos Quantum con complejidad T lineal](https://arxiv.org/abs/1805.03662).
