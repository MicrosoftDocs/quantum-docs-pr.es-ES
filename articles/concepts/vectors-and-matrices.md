---
title: Vectores y matrices en la computación cuántica
description: Conozca los conceptos básicos sobre cómo trabajar con vectores y matrices.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269548"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="20080-103">Vectores y matrices</span><span class="sxs-lookup"><span data-stu-id="20080-103">Vectors and Matrices</span></span>

<span data-ttu-id="20080-104">Algunos conocimientos sobre vectores y matrices son esenciales para comprender la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="20080-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="20080-105">Se proporciona una breve introducción y se recomienda a los lectores interesados leer una referencia estándar sobre álgebra lineal, como *Strang, G (1993). Introducción a álgebra lineal (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o una referencia en línea como [álgebra lineal](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="20080-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="20080-106">Un vector de columna (o simplemente [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de dimensión (o tamaño) $n $ es una colección de $n $ números complejos $ (V_1, v_2, \ldots, v_n) $ organizados como columna:</span><span class="sxs-lookup"><span data-stu-id="20080-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="20080-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="20080-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-108">v_1\\\\</span></span>
<span data-ttu-id="20080-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-109">v_2\\\\</span></span>
<span data-ttu-id="20080-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-110">\vdots\\\\</span></span>
<span data-ttu-id="20080-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="20080-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="20080-112">La norma de un vector $v $ se define como $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $.</span><span class="sxs-lookup"><span data-stu-id="20080-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="20080-113">Se dice que un vector es de norma unitaria (o, como alternativa, se denomina [*Vector de unidad*](https://en.wikipedia.org/wiki/Unit_vector)) si su norma es $1 $ .</span><span class="sxs-lookup"><span data-stu-id="20080-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="20080-114">El [*adjoin de una $v de vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ se denota $v ^ \dagger $ y se define como el siguiente vector de fila, donde $ \* $ denota el conjugado complejo.</span><span class="sxs-lookup"><span data-stu-id="20080-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="20080-115">$ $ \begin{ bmatrix } V_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } V_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="20080-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="20080-116">La manera más común de multiplicar dos vectores juntos es a través del [*producto interno*](https://en.wikipedia.org/wiki/Inner_product_space), también conocido como producto punto.</span><span class="sxs-lookup"><span data-stu-id="20080-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="20080-117">El producto interno proporciona la proyección de un vector en otro y es muy útil para describir cómo expresar un vector como una suma de otros vectores más sencillos.</span><span class="sxs-lookup"><span data-stu-id="20080-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="20080-118">El producto interno entre $u $ y $v $ , indicado $ \left \langle u, v \right \rangle $ se define como</span><span class="sxs-lookup"><span data-stu-id="20080-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="20080-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="20080-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="20080-120">Esta notación también permite escribir la norma de un vector $v $ como $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="20080-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="20080-121">Podemos multiplicar un vector con un número $c $ para formar un nuevo vector cuyas entradas se multiplican por $c $ .</span><span class="sxs-lookup"><span data-stu-id="20080-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="20080-122">También podemos agregar dos vectores $u $ y $v $ para formar un nuevo vector cuyas entradas son la suma de las entradas de $u $ y $v $ .</span><span class="sxs-lookup"><span data-stu-id="20080-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="20080-123">Estas operaciones se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="20080-123">These operations are depicted below:</span></span>

<span data-ttu-id="20080-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="20080-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-125">u_1\\\\</span></span>
<span data-ttu-id="20080-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-126">u_2\\\\</span></span>
<span data-ttu-id="20080-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-127">\vdots\\\\</span></span>
<span data-ttu-id="20080-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-129">v_1\\\\</span></span>
    <span data-ttu-id="20080-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-130">v_2\\\\</span></span>
    <span data-ttu-id="20080-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-131">\vdots\\\\</span></span>
    <span data-ttu-id="20080-132">v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="20080-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="20080-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="20080-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-135">\vdots\\\\</span></span>
<span data-ttu-id="20080-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="20080-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="20080-137">Una [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamaño $m \times n $ es una colección de $MN $ números complejos organizados en $m $ filas y $n $ columnas, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="20080-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="20080-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="20080-139">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="20080-140">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="20080-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="20080-141">Tenga en cuenta que un vector de Dimension $n $ es simplemente una matriz de tamaño $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="20080-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="20080-142">Al igual que con los vectores, se puede multiplicar una matriz con un número $c $ para obtener una nueva matriz en la que cada entrada se multiplica con $c $ y se pueden agregar dos matrices del mismo tamaño para generar una nueva matriz cuyas entradas son la suma de las entradas correspondientes de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="20080-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="20080-143">Productos de multiplicación y tensores de matrices</span><span class="sxs-lookup"><span data-stu-id="20080-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="20080-144">También podemos multiplicar dos matrices $M $ de dimension $m \times n $ y $N $ de Dimension $n \times p $ para obtener una nueva $P $ de matriz de Dimension $m \times p $ como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="20080-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="20080-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="20080-145">\begin{align}</span></span>
<span data-ttu-id="20080-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-147">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="20080-148">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="20080-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="20080-149">extremobmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-149">\end{bmatrix}</span></span>
<span data-ttu-id="20080-150">iniciabmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-150">\begin{bmatrix}</span></span>
<span data-ttu-id="20080-151">N_ {11 } ~ ~ n_ {12 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ n_ {21 } ~ ~ n_ {22 } ~ ~ \cdots ~ ~ n_ {2P } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="20080-152">N_ {N1 } ~ ~ n_ {N2 } ~ ~ \cdots ~ ~ n_ {NP}</span><span class="sxs-lookup"><span data-stu-id="20080-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="20080-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="20080-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1P } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2P } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="20080-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="20080-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="20080-156">extremobmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-156">\end{bmatrix}</span></span>
<span data-ttu-id="20080-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="20080-157">\end{align}</span></span>

<span data-ttu-id="20080-158">donde las entradas de $P $ se $P _ {IK } = \ sum_j m_ {ij} n_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="20080-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="20080-159">Por ejemplo, la entrada $P _ {11 } $ es el producto interno de la primera fila de $M $ con la primera columna de $N $ .</span><span class="sxs-lookup"><span data-stu-id="20080-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="20080-160">Tenga en cuenta que, puesto que un vector es simplemente un caso especial de una matriz, esta definición se extiende a la multiplicación de vectores de matriz.</span><span class="sxs-lookup"><span data-stu-id="20080-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="20080-161">Todas las matrices que consideramos serán matrices cuadradas, donde el número de filas y columnas es igual, o vectores, que corresponde a la $ columna $1.</span><span class="sxs-lookup"><span data-stu-id="20080-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="20080-162">Una matriz cuadrada especial es la [*matriz de identidad*](https://en.wikipedia.org/wiki/Identity_matrix), indicada como $ \boldone $ , que tiene todos sus elementos diagonales iguales a $1 $ y los elementos restantes iguales a $0 $ :</span><span class="sxs-lookup"><span data-stu-id="20080-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="20080-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="20080-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="20080-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="20080-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="20080-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="20080-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="20080-168">En el caso de una matriz cuadrada $A $ , decimos que una matriz $B $ es su [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) si $AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="20080-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="20080-169">No es necesario que el inverso de una matriz exista, pero cuando existe es único y se denota $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="20080-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="20080-170">En el caso de cualquier matriz $M, la transposición del $ $M o del tipo de conjugada $ es una matriz $N $ tal que $N _ {ij } = m_ {ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="20080-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="20080-171">El contiguo de $M $ suele estar indicado $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20080-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="20080-172">Decimos que una matriz $U $ es [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) si $UU ^ \dagger = U ^ \dagger U = \boldone $ o equivalente, $U ^ {-1 } = u ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20080-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="20080-173">Quizás la propiedad más importante de las matrices de unitarios sea que conserven la norma de un vector.</span><span class="sxs-lookup"><span data-stu-id="20080-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="20080-174">Esto sucede porque</span><span class="sxs-lookup"><span data-stu-id="20080-174">This happens because</span></span> 

<span data-ttu-id="20080-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger U ^ \Dagger u v = \Langle u v, U v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="20080-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="20080-176">$Se dice que una matriz $M es [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20080-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="20080-177">Por último, el [*producto tensores*](https://en.wikipedia.org/wiki/Tensor_product) (o producto Kronecker) de dos matrices $M $ de tamaño $m \times n $ y $N $ de tamaño $p \times q $ es una matriz mayor $P = M \otimes n $ de tamaño $mp \times NQ $ y se obtiene de $M $ y $N $ como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="20080-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="20080-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="20080-178">\begin{align}</span></span>
    <span data-ttu-id="20080-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-180">M_ {11 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="20080-181">M_ {M1 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="20080-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="20080-182">extremobmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-182">\end{bmatrix}</span></span>
    <span data-ttu-id="20080-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-184">N_ {11 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="20080-185">N_ {P1 } ~ ~ \cdots ~ ~ n_ {pq}</span><span class="sxs-lookup"><span data-stu-id="20080-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="20080-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-187">M_ {11 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1T } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20080-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="20080-188">M_ {M1 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {MN } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1T } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {pq } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="20080-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="20080-189">\end{bmatrix}.</span></span>
<span data-ttu-id="20080-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="20080-190">\end{align}</span></span>

<span data-ttu-id="20080-191">Esto se demuestra mejor con algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="20080-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="20080-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="20080-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="20080-196">extremobmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-196">\end{bmatrix}</span></span>
    <span data-ttu-id="20080-197">= \begin{ bmatrix } a \\ \\ d a \\ \\ e \\ \\ b c \\ \\ b d \\ \\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="20080-198">y</span><span class="sxs-lookup"><span data-stu-id="20080-198">and</span></span>

<span data-ttu-id="20080-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="20080-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="20080-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="20080-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="20080-204">un\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20080-206">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20080-208">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20080-210">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="20080-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20080-212">extremobmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-212">\end{bmatrix}</span></span>
    <span data-ttu-id="20080-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20080-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="20080-214">AE \ AF \ es \ BF \\ \\ AG \ ah \ BG \ BH \\ \\ CE \ CF \ de \ DF \\ \\ CG \ CH \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="20080-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="20080-215">Una Convención de notación útil final que rodea a los productos de tensores es que, para cualquier vector $v $ o matriz $M $ , $v ^ {\otimes n } $ o $M ^ {\otimes n } $ es una mano corta para un $ producto tensores repetido de $n doblado.</span><span class="sxs-lookup"><span data-stu-id="20080-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="20080-216">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20080-216">For example:</span></span>

<span data-ttu-id="20080-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="20080-217">\begin{align}</span></span>
<span data-ttu-id="20080-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{1-1 bmatrix } \\ \\ \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 \end{bmatrix} &0&0&0.</span><span class="sxs-lookup"><span data-stu-id="20080-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="20080-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="20080-219">\end{align}</span></span>
