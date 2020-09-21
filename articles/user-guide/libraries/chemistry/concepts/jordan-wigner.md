---
title: 'Jordania: representación Wigner'
description: Obtenga información sobre la representación Jordania-Wigner, que asigna operadores Hamiltonian a matrices unitarios que se pueden implementar más fácilmente en un equipo Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833878"
---
# <a name="jordan-wigner-representation"></a>Jordania: representación Wigner

Aunque el segundo Hamiltonians cuantificado se representa de manera adecuada en términos de $a ^ \dagger $ (creación) y $a $ (Annihilation), estas operaciones no son operaciones fundamentales en los equipos Quantum.
Como resultado, si se desea implementarlos en un equipo Quantum, es necesario asignar los operadores a las matrices unitarios que se pueden implementar en un equipo Quantum.
La representación Jordania – Wigner proporciona una de estas asignaciones.
Sin embargo, también existen otros, como la representación Bravyi – Kitaev y tienen sus propias ventajas y desventajas relativas.
La principal ventaja de la representación Jordania-Wigner es su simplicidad.

La representación Jordania-Wigner es sencilla para derivar.
Recuerde que un estado $ \ket {0} _J $ implica que el giro orbital $j $ está vacío y $ \ket {1} _J $ implica que está ocupado.
Esto significa que qubits puede almacenar de forma natural la profesión de un giro orbital determinado.
Después tenemos ese $a ^ \ dagger_j \ket {0} _J = \ket {1} _J $ y $a ^ \ dagger_j \ket {1} _J = $0.
Es fácil comprobar que \begin{Align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align} donde $X _J $ y $Y _J $ son los operadores Pauli-$X $ y-$Y $ que actúan en qubit $j $.

>[!NOTE]
> En Q# el estado $ \ket {0} $ representa el eigenstate + 1 del operador $Z $. En algunas áreas de física, $ \ket {0} $ representa el estado de la baja energía y, por tanto, el-1 eigenstate del operador $Z $. Por lo tanto, algunas fórmulas pueden diferir de la literatura popular.

En la biblioteca de química, usamos $ \ket {0} $ para representar un giro no ocupado.
Esto muestra que, en el caso de una sola rotación, es fácil representar los operadores de creación y Annihilation en términos de matrices unitarios que entienden los equipos Quantum.
Tenga en cuenta que mientras $X $ y $Y $ son unitarios $a ^ \dagger $ y $a $ no lo son.
Más adelante veremos que esto no supone un reto para la simulación.

Un problema que queda es que mientras que la construcción anterior funciona para un único giro orbital, se produce un error en los sistemas con dos o más giros de giro.
Como fermions son antisymmetic, sabemos que $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ para cualquier $j $ y $k $.
Sin embargo, $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).
$ $ En otras palabras, los dos operadores de creación no contrae el desactivador según sea necesario.
Esto puede solucionarse en un modo sencillo, si es elegante.
La solución consiste en tener en cuenta que los operadores de Pauli de forma natural se contraen.
En concreto, $XZ =-ZX $ y $YZ =-ZY $.
Por lo tanto, al entremezclar $Z operadores $ en la construcción del operador, podemos emular la commutación correcta.
La construcción completa es la siguiente: 

\begin{Align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_2 &= Z\otimes\left (\frac{X-iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iy} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iy} {2} \right). \label{EQ: JW} \end{align}

También es conveniente expresar los operadores de número, $n _j $, en términos de operadores de Pauli.
Afortunadamente, las cadenas de $Z $ Operators (conocidas como cadenas de Jordania-Wigner) cancelan después de una realiza esta sustitución.
Después de llevar esto (y de que se revoque $X _jY_j = iZ_j $), tenemos \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Construir Hamiltonians en Jordania: representación Wigner

Una vez que se ha invocado la representación Jordania-Wigner, la conversión de Hamiltonian a una suma de operadores de Pauli es sencilla.
Simplemente tiene que reemplazar cada uno de los operadores $a ^ \dagger $ y $a $ en el Hamiltonian Fermionic con las cadenas de operadores Pauli especificados anteriormente.
Cuando una realiza esta sustitución, solo hay cinco clases de términos dentro de Hamiltonian.
Estas cinco clases se corresponden con las distintas formas en que se puede elegir el $p, q $ y $p, q, r, s $ en los términos de un cuerpo y dos cuerpos en el Hamiltonian.
Estas cinco clases, para el caso en que $p>q>r>s $ y las órbitas con valores reales son

\begin{align} H_ {PP} A_P ^ \dagger A_P &= \ sum_p \frac{H_ {PP}} {2} (1-Z_p) \\ \\ H_ {PQ} (A_P ^ \dagger a_q + a ^ \ dagger_q A_P) &= \frac{H_ {pq}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ H_ {pqqp} n_P n_q &= \frac{H_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {PQRS} &= \frac{H_ {PQRS}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Aunque la generación de Hamiltonians a mano solo requiere la aplicación de estas reglas de reemplazo, hacerlo sería inviable para moléculas grandes que pueden constar de millones de términos de Hamiltonian.
Como alternativa, podemos construir automáticamente la `JordanWignerEncoding` determinada `FermionHamiltonian` representación de Hamiltonian.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Una vez que los Hamiltonians se construyen de esta forma, podemos usar un host de algoritmos de simulación de Quantum para compilar la dinámica generada por $e ^ {-iHt} $ en una secuencia de puertas elementales (dentro de alguna tolerancia de errores definible por el usuario).
Se describen los dos métodos más populares de las fórmulas de simulación de Quantum, qubitization y Trotter – Suzuki en la documentación algorítmica. Proporcionamos implementaciones para ambos métodos en la biblioteca de simulación de Hamiltonian.
