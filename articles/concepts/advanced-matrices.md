---
title: Conceptos avanzados de matrices
description: Obtenga información sobre vectores propios, vectores propios y la matriz exponencial, las herramientas fundamentales que se usan para describir y simular algoritmos Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630149"
---
# <a name="advanced-matrix-concepts"></a>Conceptos de matriz avanzada #

Ahora ampliamos nuestra manipulación de matrices a [*vectores propios, vectores propios*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) y [*exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) , que forman un conjunto fundamental de herramientas que necesitamos describir e implementar algoritmos Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Vectores propios y vectores propios ##

Permita que $M $ sea una matriz cuadrada y $v $ ser un vector que no sea el vector todo ceros (es decir, el vector con todas las entradas iguales a $0 $ ).

Decimos $v $ es un [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M $ si $MV = cv $ durante cierto número $c $ . Decimos $c $ es el [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondiente al $v Eigenvector $ . En general, una matriz $M $ puede transformar un vector en cualquier otro Vector, pero un Eigenvector es especial porque se deja sin modificar, salvo que se multiplica por un número. Tenga en cuenta que si $v $ es un Eigenvector con eigenvalue $c $ , $AV $ también es Eigenvector (para cualquier $a distinto de cero $ ) con la misma eigenvalue.

Por ejemplo, para la matriz de identidad, cada vector $v $ es un Eigenvector con eigenvalue $1 $ .

Como otro ejemplo, considere una [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ que solo tiene entradas distintos de cero en la diagonal:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \end{ bmatrix } .
$$

Vectores

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } y \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$

son vectores propios de esta matriz con vectores propios $d _ 1, $ $d _2 $ y $d _3 $ , respectivamente. Si $d _ 1 $ , $d _2 $ y $d _3 $ son números distintos, estos vectores (y sus múltiplos) son los únicos vectores propios de la matriz $D $ . En general, para una matriz diagonal es fácil leer las vectores propios y vectores propios. Los vectores propios son todos los números que aparecen en la diagonal, y sus respectivas vectores propios son los vectores de unidad con una entrada igual a $1 $ y las entradas restantes son iguales a $0 $ .

Observe en el ejemplo anterior que el vectores propios de $D $ forma una base para los $ vectores de dimensión $3. Una base es un conjunto de vectores, de modo que cualquier vector se puede escribir como una combinación lineal de ellos. Más explícitamente, $v _ 1, $ $v _2 $ y $v _3 $ forman una base si $ se puede escribir cualquier vector $v como $v = a_1 V_1 + a_2 v_2 + a_3 v_3 $ para algunos números $a _ 1 $ , $a _2 $ y $a _3 $ .

Recuerde que una matriz de Hermitian (también llamada Self-adjoin) es una matriz cuadrada compleja igual a su propia conjugada compleja, mientras que una matriz de la unitario es una matriz cuadrada compleja cuyo inverso es igual a su conjugado complejo.
En el caso de las matrices Hermitian y unitarios, que son esencialmente las únicas matrices que se encuentran en la informática Quantum, hay un resultado general conocido como [*teorema espectral*](https://en.wikipedia.org/wiki/Spectral_theorem), que afirma lo siguiente: para cualquier $M de matriz de Hermitian o unitario $ , existe una unidad $U de forma $ que $M = U ^ \dagger D U $ para algunas $D de matriz diagonal $ . Además, las entradas diagonales de $D serán $ el vectores propios de $M $ .

Ya sabemos cómo calcular el vectores propios y el vectores propios de una matriz diagonal $D $ . Con esta teorema sabemos que si $v $ es un Eigenvector de $D $ con eigenvalue $c $ , es decir, $DV = CV $ , $U ^ \dagger v será $ un eigenvector de $M $ con eigenvalue $c $ . Esto se debe a que

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Exponencial de matriz
Una [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) también se puede definir en la analogía exacta con la función exponencial.  La matriz exponencial de una matriz $A $ puede expresarse como

$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $

Esto es importante porque la evolución del tiempo mecánico de Quantum se describe mediante una matriz de la forma $e ^ {iB } $ for Hermitian matrix $B $ .  Por esta razón, la realización de la exponenciación de matriz es una parte fundamental de la informática Quantum y como tal # ofrece rutinas intrínsecas para describir estas operaciones.
Hay muchas maneras de calcular una matriz exponencial en un equipo clásico y, en general, la aproximación numérica de este tipo exponencial es llena con peligros.  Vea el [*topo de Cleve y el préstamo de Charles van. "Diecinueve maneras dudosas de calcular el valor exponencial de una matriz". SIAM revisión 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para obtener más información sobre los desafíos implicados.

La forma más fácil de entender cómo calcular el valor exponencial de una matriz es a través de vectores propios y vectores propios de esa matriz.  En concreto, el teorema espectral descrito anteriormente indica que para cada matriz Hermitian o unitario $A $ existe un $U de matriz unitario $ y una matriz diagonal $D $ tal que $A = u ^ \dagger D u $ .  Debido a las propiedades de Unitarity, tenemos $A ^ 2 = U ^ \dagger D ^ 2 U $ y similares para cualquier $p de energía $ $A ^ p = u ^ \dagger D ^ p U $ .  Si se sustituye por la definición de operador del operador exponencial se obtiene:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $

En otras palabras, si se transforma en el eigenbasis de la matriz $A $ , al calcular la matriz exponencial es equivalente a calcular el valor exponencial ordinario del vectores propios de la matriz.  Tantas operaciones en la informática Quantum impliquen la realización de la exponenciación de matrices, este truco de transformación en el eigenbasis de una matriz para simplificar la realización del operador exponencial aparece con frecuencia y es la base de muchos algoritmos Quantum, como los métodos de simulación de Quantum de estilo Suzuki y Trotter, que se describen más adelante en esta guía.

Otra propiedad útil es si $B $ es unitario y Hermitian, es decir, $B = b ^ {-1 } = b ^ \dagger $ después $B ^ 2 = \boldone $ . Aplicando esta regla a la expansión anterior de la matriz exponencial y agrupando los términos $ \boldone $ y $B $ juntos, puede ver que para cualquier valor real $x $ la identidad

$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $


Porta. Este truco es especialmente útil porque permite tener en cuenta que las exponenciaciones de la matriz de acciones tienen, aunque la dimensión de $B $ sea exponencialmente grande, en el caso especial en que $B $ sea unitario y Hermitian.
