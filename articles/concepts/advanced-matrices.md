---
title: conceptos de matriz avanzada Descripción: Obtenga información sobre vectores propios, vectores propios y exponencial de la matriz, las herramientas fundamentales que se usan para describir y simular algoritmos Quantum.
Autor: QuantumWriter UID: Microsoft. Quantum. Concepts. Matrix: avanzado ms. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 ms. topic: article no-LOC:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="advanced-matrix-concepts"></a>Conceptos de matriz avanzada #

Ahora ampliamos nuestra manipulación de matrices a [*vectores propios, vectores propios*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) y [*exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) , que forman un conjunto fundamental de herramientas que necesitamos describir e implementar algoritmos Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Vectores propios y vectores propios ##

Permita que $ M $ sea una matriz cuadrada y $ v $ sea un vector que no sea el vector todo ceros (es decir, el vector con todas las entradas igual a $ 0 $ ).

Decimos que $ v $ es una [*Eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $ M $ si $ MV = CV $ para algún número $ c $ . Decimos $ $ que c es el [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondiente a Eigenvector $ v $ . En general, una matriz $ M $ puede transformar un vector en cualquier otro Vector, pero un Eigenvector es especial porque se deja sin modificar, salvo que se multiplica por un número. Tenga en cuenta que si $ v $ es un Eigenvector con eigenvalue $ c $ , $ AV $ también es Eigenvector (para cualquier valor distinto de cero $ $ ) con la misma eigenvalue.

Por ejemplo, para la matriz de identidad, cada vector $ v $ es un Eigenvector con eigenvalue $ 1 $ .

Como otro ejemplo, considere una [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ que solo tiene entradas distintos de cero en la diagonal:

$$
\begin{bmatrix}
d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix} .
$$

Vectores

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} y \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

son vectores propios de esta matriz con vectores propios $ d_1 $ , $ d_2 $ y $ d_3 $ , respectivamente. Si $ d_1 $ , $ d_2 $ y $ d_3 $ son números distintos, estos vectores (y sus múltiplos) son los únicos vectores propios de la matriz $ d $ . En general, para una matriz diagonal es fácil leer las vectores propios y vectores propios. Los vectores propios son todos los números que aparecen en la diagonal, y sus respectivas vectores propios son los vectores de unidad con una entrada igual a $ 1 $ y las entradas restantes son iguales a $ 0 $ .

Observe en el ejemplo anterior que el vectores propios de $ D $ forma una base para $ los $ vectores de tres dimensiones. Una base es un conjunto de vectores, de modo que cualquier vector se puede escribir como una combinación lineal de ellos. Más explícitamente, $ V_1 $ , $ v_2 $ y $ v_3 $ forman una base si cualquier vector $ v $ se puede escribir como $ v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ para algunos números $ a_1 $ , $ a_2 $ y $ a_3 $ .

Recuerde que una matriz de Hermitian (también llamada Self-adjoin) es una matriz cuadrada compleja igual a su propia TRANSPOSE de conjugada compleja, mientras que una matriz de unitarios es una matriz de cuadrados compleja cuyo inverso es igual a la TRANSPOSE de conjugación contigua o compleja.
En el caso de matrices Hermitian y unitarios, que son esencialmente las únicas matrices que se encuentran en la informática Quantum, hay un resultado general conocido como [*teorema espectral*](https://en.wikipedia.org/wiki/Spectral_theorem), que valida lo siguiente: para cualquier Hermitian o matriz de $ unidad M $ , existe un unitario $ u $ $ de tipo m = u ^ \dagger D u $ para alguna matriz diagonal $ D $ . Además, las entradas diagonales de $ D serán $ el vectores propios de $ M $ .

Ya sabemos cómo calcular el vectores propios y el vectores propios de una matriz diagonal $ D $ . Con esta teorema sabemos que si $ v $ es un Eigenvector de $ D $ con eigenvalue $ c $ , es decir, $ DV = CV $ , entonces $ U ^ v será \dagger $ un Eigenvector de $ M $ con eigenvalue $ c $ . Esto se debe a que

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger D v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Exponencial de matriz
Una [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) también se puede definir en la analogía exacta con la función exponencial.  La matriz exponencial de una matriz $ a $ se puede expresar como

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac { A ^ 3 } { 3!}+\cdots
$$

Esto es importante porque la evolución del tiempo mecánico de Quantum se describe mediante una matriz de la forma $ e ^ { IB } $ para la matriz de Hermitian $ B $ .  Por esta razón, la realización de la exponenciación de matriz es una parte fundamental de la informática Quantum y, como tal, Q# ofrece rutinas intrínsecas para describir estas operaciones.
Hay muchas maneras de calcular una matriz exponencial en un equipo clásico y, en general, la aproximación numérica de este tipo exponencial es llena con peligros.  Vea el [*topo de Cleve y el préstamo de Charles van. "Diecinueve maneras dudosas de calcular el valor exponencial de una matriz". SIAM revisión 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para obtener más información sobre los desafíos implicados.

La forma más fácil de entender cómo calcular el valor exponencial de una matriz es a través de vectores propios y vectores propios de esa matriz.  En concreto, los teorema espectrales descritos anteriormente indican que, para cada matriz de Hermitian o unitario $ $ , existe una matriz de unidad de la $ unidad $ $ $ $ = \dagger $ de  Debido a las propiedades de Unitarity, tenemos $ un ^ 2 = u ^ \dagger d ^ 2 u $ y similar para cualquier potencia $ p $ $ A ^ p = u ^ \dagger d ^ p u $ .  Si se sustituye por la definición de operador del operador exponencial se obtiene:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { nn } ) \end{bmatrix} U.$$

En otras palabras, si se transforma en el eigenbasis de la matriz $ a $ , el cálculo de la matriz exponencial es equivalente a calcular el valor exponencial ordinario del vectores propios de la matriz.  Tantas operaciones en la informática Quantum impliquen la realización de la exponenciación de matrices, este truco de transformación en el eigenbasis de una matriz para simplificar la realización del operador exponencial aparece con frecuencia y es la base de muchos algoritmos Quantum, como los métodos de simulación de Quantum de estilo Suzuki y Trotter, que se describen más adelante en esta guía.

Otra propiedad útil es si $ b $ es unitario y Hermitian, es decir, $ b = b ^ { -1 } = B ^ y \dagger $ $ b ^ 2 = \boldone $ . Aplicando esta regla a la expansión anterior de la matriz exponencial y agrupando los $ \boldone $ $ términos y B $ juntos, puede ver que para cualquier valor real $ x $ la identidad

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


Porta. Este truco es especialmente útil porque permite tener en cuenta que las exponenciaciones de la matriz de acciones tienen, aunque la dimensión de $ b $ sea exponencialmente grande, en el caso especial en que $ B $ sea unitario y Hermitian.
