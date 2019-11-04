---
title: Simulación de Hamiltonian Dynamics | Microsoft Docs
description: Simulación de documentos conceptuales de Hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184073"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulación de Hamiltonian Dynamics

Una vez que Hamiltonian se expresa como una suma de los operadores elementales, la dinámica se puede compilar en operaciones fundamentales de la puerta mediante un host de técnicas conocidas.
Entre los tres enfoques eficaces se incluyen las fórmulas Trotter – Suzuki, las combinaciones lineales de unitaries y qubitization.
A continuación se explican estos tres enfoques y se proporcionan ejemplos concretos de preguntas y respuestas sobre cómo implementar estos métodos con la biblioteca de simulación de Hamiltonian.


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki fórmulas)
La idea detrás de las fórmulas de Trotter – Suzuki es sencilla: expresar Hamiltonian como una suma de fácil simulación de Hamiltonians y, después, aproximar la evolución total como una secuencia de estas evoluciones más sencillas.
En concreto, deje $H = \sum_{j = 1} ^ m H_j $ Hamiltonian.
Después, $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, que es decir que, si $t \ll $1, el error en esta aproximación se convierte en insignificante.
Tenga en cuenta que si $e ^ {-i H t} $ eran un valor exponencial normal, el error en esta aproximación no se $O (m ^ 2 t ^ 2) $: sería cero.
Este error se produce porque $e ^ {-iHt} $ es un operador exponencial y, como resultado, se produce un error al usar esta fórmula debido al hecho de que los $H _J $ Terms no se desactivan (*es decir*, $H _J H_k \Ne H_k H_j $ en general).

Si $t $ es grande, se pueden seguir usando las fórmulas Trotter – Suzuki para simular la dinámica con precisión dividiendo en una secuencia de pasos breves.
Deje que $r $ sea el número de pasos realizados en la evolución de la hora.
Después, tenemos $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left (\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r). $ $, lo que implica que si $r $ se escala como $m ^ 2 t ^ 2/\ épsilon $, el error se puede realizar como máximo $ \epsilon $ para cualquier $ \epsilon > 0 $.

Se pueden crear aproximaciones más precisas mediante la construcción de una secuencia de exponenciales de operador de modo que se cancelen los términos de error.
La fórmula más sencilla, la fórmula Trotter simétrica o la división Strang, tiene el formato $ $ U_1 (t) = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $ que se puede convertir en menos de $ \epsilon $ para cualquier $ \epsilon > 0 $ eligiendo $ r $ para escalar como $m ^ {3/2} t ^ {3/2}/\sqrt {\ épsilon} $.

Incluso las fórmulas de Trotter de orden superior se pueden construir en función de $U 1 _ 1 $.
La más simple es la siguiente fórmula de cuarto orden: introducido originalmente por Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $ donde $s _ 1 = (4-4 ^ {1/3}) ^{-1}$.
En general, las fórmulas de orden superior arbitrariamente se pueden construir de forma similar. sin embargo, los costos derivados del uso de integradores más complejos a menudo compensan las ventajas más allá del cuarto orden en lo que se refiere a los problemas prácticos.

Para hacer que las estrategias anteriores funcionen, es necesario tener un método para simular una clase ancha de $e ^ {-iH_j t} $.
La familia más sencilla de Hamiltonians y, posiblemente, lo más útil, que podríamos usar aquí son los operadores de Pauli.
Los operadores de Pauli se pueden simular fácilmente porque se pueden convertir en diagonal mediante operaciones de Clifford (que son puertas estándar en la informática Quantum).
Además, una vez que se han diagonal, su vectores propios se puede encontrar calculando la paridad del qubits en el que actúan.

Por ejemplo, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ where $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Aquí, $e ^ {-iHt} \ket{00} = e ^ {IT} \ket{00}$ y $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, que se puede ver directamente como consecuencia del hecho de que la paridad de $0 $ es $0 $ mientras que la paridad de la cadena de bits $1 $ es $1 $.

Los exponenciales de los operadores Pauli se pueden implementar directamente en Q # mediante la operación <xref:microsoft.quantum.primitive.exp>:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

En el caso de Fermionic Hamiltonians, la [descomposición de Jordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) asigna la Hamiltonian a una suma de operadores de Pauli.
Esto significa que el enfoque anterior se puede adaptar fácilmente a la simulación de química.
En lugar de recorrer manualmente los términos de Pauli en la representación Jordania-Wigner, a continuación se muestra un ejemplo sencillo de cómo sería la ejecución de este tipo de simulación dentro de la química.
Nuestro punto de partida es una [codificación de Jordania – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) de la Hamiltonian de Fermionic, expresada en el código como una instancia de la clase `JordanWignerEncoding`.

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

Este formato de Jordania – Wigner reprsentation que son consumibles por los algoritmos de simulación de Q # es un tipo definido por el usuario `JordanWignerEncodingData`.
En Q #, este formato se pasa a una función de comodidad `TrotterStepOracle` que devuelve un operador que aproxima la evolución del tiempo mediante el Trotter, Suzuki integrador, además de otros parámetros necesarios para su ejecución.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Lo importante es que esta implementación Aplique algunas optimizaciones que se describen en [simulación de la estructura electrónica Hamiltonians con equipos Quantum](https://arxiv.org/abs/1001.3855) y la mejora de los [algoritmos Quantum para la química Quantum](https://arxiv.org/abs/1403.1539) para minimizar el número de se requieren rotaciones de un solo qubit, así como reducir los errores de simulación.

## <a name="qubitization"></a>Qubitization

Qubitization es un enfoque alternativo a la simulación que usa ideas de los recorridos de Quantum para simular la dinámica de Quantum.
Aunque qubitization requiere más qubits que las fórmulas de Trotter, el método promete una escala óptima con el tiempo de evolución y la tolerancia de errores.
Por estos motivos, se ha convertido en un método favorable para simular Hamiltonian Dynamics en general y para resolver el problema de la estructura electrónica en particular.

En un nivel alto, qubitization lo consigue a través de los pasos siguientes.
En primer lugar, deje $H = \sum_j h_j H_j $ for unitario y Hermitian $H _J $ y $h _J \ GE $0.
Mediante la realización de un par de reflejos, qubitization implementa un operador que es equivalente a $ $W = e ^ {\pm i \cos ^{-1}(H/| H | _ 1)}, $ $ where $ | H | _ 1 = \sum_j | h_j | $.
El paso siguiente implica transformar el vectores propios del operador de recorrido de $e ^ {i\pm \cos ^{-1}(E_k/| h | _ 1)} $, donde $E _k $ son los vectores propios de $H $ para $e ^ {-iE_k t} $.
Esto puede lograrse mediante una variedad de métodos de transformación de valor singular de Quantum, incluido el [procesamiento de señales Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Como alternativa, si solo se quieren cantidades estáticas (por ejemplo, la energía de estado de la base de Hamiltonian), basta con aplicar la [estimación de fase](xref:microsoft.quantum.libraries.characterization) directamente a $W $ para calcular la energía de estado de la toma de la toma de la toma de la derivación del resultado.
Esto es importante porque permite que la transformación espectral se realice de forma individual en lugar de usar un método de transformación de valor singular singular.

En un nivel más detallado, la implementación de qubitization requiere dos subrutinas que proporcionan las interfaces para el Hamiltonian.
A diferencia de los métodos Trotter – Suzuki, estas subrutinas son Quantum not clásico y su implementación necesitará usar logarítmicamente más qubits de lo que sería necesario para una simulación basada en Trotter.

La primera subrutina Quantum que qubitization usa se denomina $ \operatorname{Select} $ y se promete producir \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} donde se supone que cada $H _J $ es Hermitian y unitario.
Aunque esto puede parecer restrictivo, recuerde que los operadores de Pauli son Hermitian y unitario, por lo que las aplicaciones como la simulación de la química de Quantum se encuentran en este marco de trabajo de forma natural.
La operación $ \operatorname{Select} $, quizás sorprendentemente, es realmente una operación de reflexión.
Esto se puede considerar desde el hecho de que $ \operatorname{Select} ^ 2 \ les {j} \ket{\psi} = \ket{j} \ket{\psi} $, ya que cada $H _J $ es unitario y Hermitian y, por tanto, tiene vectores propios $ \pm $1.

La segunda subrutina se denomina $ \operatorname{Prepare} $.
Mientras que la operación Select proporciona un medio para acceder de forma coherente a cada uno de los términos de Hamiltonian $H _J $ la subrutina Prepare proporciona un método para tener acceso a los coeficientes $h _J $, \begin{Equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{ | h | _ 1}} \ket{j}.
\end{Equation} a continuación, mediante el uso de una puerta de fase de control de multiplicación, vemos que $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{if} x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

La operación $ \operatorname{Prepare} $ no se usa directamente en qubitization, sino que se usa para implementar una reflexión sobre el estado que $ \operatorname{Prepare} $ crea $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket{0}\bra @no_ _t_2_ \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.
\end{align} $ $

El operador Walk, $W $, se puede expresar en términos de las operaciones $ \operatorname{Select} $ y $R $ como $ $ W = \operatorname{Select} R, $ $ que se puede observar de nuevo para implementar un operador equivalente (hasta un isometría) para $e ^ {\pm i \cos ^{-1}(H/| h | _ 1)} $.

Estas subrutinas son fáciles de configurar en Q #.
Como ejemplo, considere la simple qubit transversal-Ising Hamiltonian donde $H = x_1 + X_2 + Z_1 Z_2 $.
En este caso, el código de preguntas y respuestas que implementaría la operación $ \operatorname{Select} $ se invoca mediante <xref:microsoft.quantum.canon.multiplexoperations>, mientras que la operación $ \operatorname{Prepare} $ se puede implementar mediante <xref:microsoft.quantum.preparation.preparearbitrarystate>.
Un ejemplo que implica la simulación del modelo de Hubbard puede encontrarse como un [ejemplo de preguntas y respuestas](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).

La especificación manual de estos pasos para problemas de química arbitrarios requeriría mucho esfuerzo, lo que se evita mediante la biblioteca de química.
De forma similar al algoritmo de simulación Trotter – Suzuki anterior, el `JordanWignerEncodingData` se pasa a la función de comodidad `QubitizationOracle` que devuelve el operador Walk, además de otros parámetros necesarios para su ejecución.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Lo importante es que la implementación <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> es aplicable a Hamiltonians arbitrarios que se especifican como una combinación lineal de cadenas Pauli.
Una versión optimizada para las simulaciones de química se invoca mediante <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.
Esta versión está optimizada para minimizar el número de puertas T mediante técnicas descritas en [codificación de espectros electrónicos en circuitos Quantum con complejidad T lineal](https://arxiv.org/abs/1805.03662).
