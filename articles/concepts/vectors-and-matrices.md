---
title: Vectores y matrices de Quantum Computing
description: Conozca los conceptos básicos sobre cómo trabajar con vectores y matrices.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 076ab6242b7ae31d4936ae8505034f1f13fa4727
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904917"
---
# <a name="vectors-and-matrices"></a>Vectores y matrices

Algunos conocimientos sobre vectores y matrices son esenciales para comprender la informática Quantum. Se proporciona una breve introducción y se recomienda a los lectores interesados leer una referencia estándar sobre álgebra lineal, como *Strang, G (1993). Introducción a álgebra lineal (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o una referencia en línea como [álgebra lineal](http://joshua.smcvt.edu/linearalgebra/).

Un vector de columna (o simplemente [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de Dimension (o size) $n $ es una colección de $n $ Complex Numbers $ (v_1, v_2, \ldots, v_n) $ organizados como columna:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

La norma de un vector $v $ se define como $ \sqrt{\sum\_i | v\_i | ^ 2} $. Se dice que un vector es de norma unitaria (o, como alternativa, se denomina [*Vector de unidad*](https://en.wikipedia.org/wiki/Unit_vector)) si su norma es $1 $. El [*colindante de un vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ se denota $v ^ \dagger $ y se define como el siguiente vector de fila, donde $\*$ denota el conjugado complejo.

$ $ \begin{bmatrix} v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

La manera más común de multiplicar dos vectores juntos es a través del [*producto interno*](https://en.wikipedia.org/wiki/Inner_product_space), también conocido como producto punto.  El producto interno proporciona la proyección de un vector en otro y es muy útil para describir cómo expresar un vector como una suma de otros vectores más sencillos.  El producto interno entre $u $ y $v $, indicado $ \left\langle u, v\right\rangle $ se define como

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Esta notación también permite que la norma de un vector $v $ se escriba como $ \sqrt{\langle v, v\rangle} $.

Podemos multiplicar un vector con un número $c $ para formar un nuevo vector cuyas entradas se multiplican por $c $. También podemos agregar dos vectores $u $ y $v $ para formar un nuevo vector cuyas entradas son la suma de las entradas de $u $ y $v $. Estas operaciones se describen a continuación:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

Una [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamaño $m \times n $ es una colección de números $MN $ Complex organizados en $m $ rows y $n $ Columns, como se muestra a continuación:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ m_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2N}\\\\ \ddots\\\\ m_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN}\\\\ \end{bmatrix}. $ $

Tenga en cuenta que un vector de Dimension $n $ es simplemente una matriz de tamaño $n \times $1. Al igual que con los vectores, se puede multiplicar una matriz con un número $c $ para obtener una nueva matriz en la que cada entrada se multiplica por $c $ y se pueden agregar dos matrices del mismo tamaño para generar una nueva matriz cuyas entradas son la suma de las entradas correspondientes de las dos matrices. 

## <a name="matrix-multiplication-and-tensor-products"></a>Productos de multiplicación y tensores de matrices

También podemos multiplicar dos matrices $M $ de Dimension $m \times n $ y $N $ de Dimension $n \times p $ para obtener una nueva matriz $P $ de Dimension $m \times p $ como se indica a continuación:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ m_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2N}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \begin{bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1P}\\\\ n_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2P}\\\\ \ddots\\\\ n_ {N1} ~ ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1P}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2P}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{bmatrix} \end{align}

donde las entradas de $P $ están $P _ {IK} = \ sum_j M_ {ij} N_ {JK} $. Por ejemplo, la entrada $P _{11}$ es el producto interno de la primera fila de $M $ con la primera columna de $N $. Tenga en cuenta que, puesto que un vector es simplemente un caso especial de una matriz, esta definición se extiende a la multiplicación de vectores de matriz. 

Todas las matrices que consideramos serán matrices cuadradas, donde el número de filas y columnas es igual, o vectores, que corresponde solo a $1 $ Column. Una matriz cuadrada especial es la [*matriz de identidad*](https://en.wikipedia.org/wiki/Identity_matrix), indicada como $ \boldone $, que tiene todos sus elementos diagonales iguales a $1 $ y los elementos restantes son iguales a $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

En el caso de una matriz cuadrada $A $, dijimos una matriz $B $ es su [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) si $AB = BA = \boldone $. No es necesario que el inverso de una matriz exista, pero cuando existe es único y se denota $A ^{-1}$. 

En el caso de las matrices $M $, la transposición del tipo de $M $ es una matriz $N $ de modo que $N _ {ij} = M_ {ji} ^\*$. El contiguo de $M $ normalmente se indica $M ^ \dagger $. Dijimos una matriz $U $ es [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) si $UU ^ \Dagger = u ^ \dagger U = \boldone $ o equivalente, $U ^{-1} = u ^ \dagger $.  Quizás la propiedad más importante de las matrices de unitarios sea que conserven la norma de un vector.  Esto sucede porque 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

Se dice que una matriz $M $ es [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $M = M ^ \dagger $.

Por último, el [*producto tensores*](https://en.wikipedia.org/wiki/Tensor_product) (o producto Kronecker) de dos matrices $M $ de size $m \times n $ y $N $ de size $p \times q $ es una matriz mayor $P = M\otimes n $ de size $MP \times NQ $ y se obtiene de $M $ y $N $ como se indica a continuación:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ m_ {M1} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1T}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1P}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1T}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {M1} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1T}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {MN} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1P}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{ bmatrix} \end{bmatrix}.
\end{align}

Esto se demuestra mejor con algunos ejemplos:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ a d \\\\ a e \\b c \\\\ b d \\\\ be\end {bmatrix} $ $\\

y

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ \\t_15_ AG \ ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ CH \ DG \ DH \end{bmatrix}.\\
$$

Una Convención de notación útil final que rodea a los productos de tensores es que, en el caso de cualquier vector $v $ o Matrix $M $, $v ^ {\otimes n} $ o $M ^ {\otimes n} $ es una mano corta para un producto de tensores repetido de $n $ doblado.  Por ejemplo:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{ bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ end { bmatrix}.
\end{align}
