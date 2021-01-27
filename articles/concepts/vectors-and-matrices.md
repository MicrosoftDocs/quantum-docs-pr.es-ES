---
title: vectores y matrices en Quantum Computing Description: Conozca los conceptos básicos sobre cómo trabajar con vectores y matrices.
Autor: QuantumWriter UID: Microsoft. Quantum. Concepts. vectores ms. Author: v-benbra ms. Date: 12/11/2017 ms. topic: conceptual no-LOC:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
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

# <a name="vectors-and-matrices"></a>Vectores y matrices

Algunos conocimientos sobre vectores y matrices son esenciales para comprender la informática Quantum. Se proporciona una breve introducción y se recomienda a los lectores interesados leer una referencia estándar sobre álgebra lineal, como *Strang, G (1993). Introducción a álgebra lineal (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o una referencia en línea como [álgebra lineal](http://joshua.smcvt.edu/linearalgebra/).

Un vector de columna (o simplemente [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ de dimensión (o tamaño) $ n $ es una colección de $ n $ números complejos $ (V_1, v_2, \ldots, v_n) $ organizados como una columna:

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

La norma de un vector $ v $ se define como $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ . Se dice que un vector es de norma unitaria (o, como alternativa, se denomina [*Vector de unidad*](https://en.wikipedia.org/wiki/Unit_vector)) si su norma es $ 1 $ . El [*contiguo de un vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ se indica $ como v ^ \dagger $ y se define como el siguiente vector de fila donde $ \* $ denota el conjugado complejo.

$$\begin{bmatrix}V_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

La manera más común de multiplicar dos vectores juntos es a través del [*producto interno*](https://en.wikipedia.org/wiki/Inner_product_space), también conocido como producto punto.  El producto interno proporciona la proyección de un vector en otro y es muy útil para describir cómo expresar un vector como una suma de otros vectores más sencillos.  El producto interno entre $ u $ y $ v $ , indicado $ \left \langle u, v \right \rangle $ se define como

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Esta notación también permite escribir la norma de un vector $ v $ como $ \sqrt { \langle v, v \rangle } $ .

Podemos multiplicar un vector con un número $ c $ para formar un nuevo vector cuyas entradas se multiplican por $ c $ . También podemos agregar dos vectores $ u $ y $ v $ para formar un nuevo vector cuyas entradas son la suma de las entradas de $ u $ y $ v $ . Estas operaciones se describen a continuación:

$$\mathrm{Si } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { y}~
v =\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} , ~ \mathrm {}~
au + BV =\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} .
$$

Una [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamaño $ m \times n $ es una colección de $ MN $ Complex Numbers organizada en $ m $ Rows y $ n $ columnas, como se muestra a continuación:

$$F = 
\begin{bmatrix}
M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2N}\\\\
\ddots\\\\
M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\
\end{bmatrix}.$$

Tenga en cuenta que un vector de dimensión $ n $ es simplemente una matriz de tamaño $ n \times 1 $ . Al igual que con los vectores, se puede multiplicar una matriz con un número $ c $ para obtener una nueva matriz en la que cada entrada se multiplica por $ c $ y se pueden agregar dos matrices del mismo tamaño para generar una nueva matriz cuyas entradas son la suma de las entradas correspondientes de las dos matrices. 

## <a name="matrix-multiplication-and-tensor-products"></a>Productos de multiplicación y tensores de matrices

También podemos multiplicar dos matrices $ m $ de Dimension $ m \times n $ y $ n $ de Dimension $ n \times p $ para obtener una nueva matriz $ p $ de Dimension $ m \times p $ como se indica a continuación:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
    M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2N}\\\\
    \ddots\\\\
    M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ n_ { 12 } ~~ \cdots ~~ n_ { 1P}\\\\
N_ { 21 } ~~ n_ { 22 } ~~ \cdots ~~ n_ { 2P}\\\\
\ddots\\\\
N_ { N1 } ~~ n_ { N2 } ~~ \cdots ~~ n_ { NP}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2P}\\\\
\ddots\\\\
P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}
\end{bmatrix}
\end{align}

donde las entradas de $ P $ se $ P_n a la { inversa } = \sum _j M_ { ij } n_ { JK } $ . Por ejemplo, la entrada $ P_ { 11 } $ es el producto interno de la primera fila de $ M $ con la primera columna de $ N $ . Tenga en cuenta que, puesto que un vector es simplemente un caso especial de una matriz, esta definición se extiende a la multiplicación de vectores de matriz. 

Todas las matrices que consideramos serán matrices cuadradas, donde el número de filas y columnas es igual, o vectores, que corresponde a una $ sola $ columna. Una matriz cuadrada especial es la [*matriz de identidad*](https://en.wikipedia.org/wiki/Identity_matrix), indicada $ \boldone $ , que tiene todos sus elementos diagonales iguales a $ 1 $ y los elementos restantes son iguales a $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

En el caso de una matriz cuadrada $ a $ , se $ indica que la matriz B $ es [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) si $ AB = BA = \boldone $ . No es necesario que el inverso de una matriz exista, pero cuando existe, es único y se le indica que es $ ^ { -1 } $ . 

En el caso de cualquier matriz $ m $ , la transposición de m o $ del $ tipo de variable es una matriz $ N $ tal que $ n_ { ij } = m_ { ji } ^ \* $ . El colindante de $ M $ se indica normalmente como $ m ^ \dagger $ . Decimos que una matriz $ u $ es [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) si $ UU ^ \dagger = u ^ \dagger u = \boldone $ o equivalente, $ u ^ { -1 } = U ^ \dagger $ .  Quizás la propiedad más importante de las matrices de unitarios sea que conserven la norma de un vector.  Esto sucede porque 

$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, u v \rangle .$$  

$ $ Se dice que una matriz M es [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $ m = m ^ \dagger $ .

Por último, el [*producto tensores*](https://en.wikipedia.org/wiki/Tensor_product) (o producto Kronecker) de dos $ matrices $ de tamaño $ m \times n $ y $ n $ de tamaño $ p \times q $ es una matriz mayor $ = de tamaño p M \otimes n $ de $ MP \times NQ $ , y se obtiene de $ M y n de la $ $ $ manera siguiente:

\begin{align}
    M \otimes N &=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ m_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ n_ { 1P  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ n_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Esto se demuestra mejor con algunos ejemplos:

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a \\\\ d a e b a b \\\\ \\\\ c \\\\ d \\\\\end{bmatrix}
$$

y

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d \end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h \end{bmatrix}
     =
    \begin{bmatrix}
    un\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    d\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE \ AF \ \ BF \\\\
    AG \ ah \ BG \ BH \\\\
    CE \ CF \ de \ DF \\\\
    CG \ CH \ DG \ DH \end{bmatrix} .
$$

Una Convención de notación útil final que rodea a los productos de tensores es que, para cualquier vector $ v $ o Matrix $ M $ , $ v ^ { \otimes n } $ o $ m ^ { \otimes n } $ es una mano corta para un $ $ producto tensores repetido de n veces.  Por ejemplo:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .
\end{align}
