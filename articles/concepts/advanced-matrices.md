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
- $
- $
- $
- $
- $$
- $$
- $$
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
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269463"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="7ac2e-103">Conceptos de matriz avanzada</span><span class="sxs-lookup"><span data-stu-id="7ac2e-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="7ac2e-104">Ahora ampliamos nuestra manipulación de matrices a [*vectores propios, vectores propios*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) y [*exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) , que forman un conjunto fundamental de herramientas que necesitamos describir e implementar algoritmos Quantum.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="7ac2e-105">Vectores propios y vectores propios</span><span class="sxs-lookup"><span data-stu-id="7ac2e-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="7ac2e-106">Permita que $M $ sea una matriz cuadrada y $v $ ser un vector que no sea el vector todo ceros (es decir, el vector con todas las entradas iguales a $0 $ ).</span><span class="sxs-lookup"><span data-stu-id="7ac2e-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="7ac2e-107">Decimos $v $ es un [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M $ si $MV = cv $ durante cierto número $c $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="7ac2e-108">Decimos $c $ es el [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondiente al $v Eigenvector $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="7ac2e-109">En general, una matriz $M $ puede transformar un vector en cualquier otro Vector, pero un Eigenvector es especial porque se deja sin modificar, salvo que se multiplica por un número.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="7ac2e-110">Tenga en cuenta que si $v $ es un Eigenvector con eigenvalue $c $ , $AV $ también es Eigenvector (para cualquier $a distinto de cero $ ) con la misma eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="7ac2e-111">Por ejemplo, para la matriz de identidad, cada vector $v $ es un Eigenvector con eigenvalue $1 $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="7ac2e-112">Como otro ejemplo, considere una [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ que solo tiene entradas distintos de cero en la diagonal:</span><span class="sxs-lookup"><span data-stu-id="7ac2e-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="7ac2e-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7ac2e-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="7ac2e-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="7ac2e-115">Vectores</span><span class="sxs-lookup"><span data-stu-id="7ac2e-115">The vectors</span></span>

<span data-ttu-id="7ac2e-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ \end{bmatrix} y \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="7ac2e-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="7ac2e-117">son vectores propios de esta matriz con vectores propios $d _ 1, $ $d _2 $ y $d _3 $ , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="7ac2e-118">Si $d _ 1 $ , $d _2 $ y $d _3 $ son números distintos, estos vectores (y sus múltiplos) son los únicos vectores propios de la matriz $D $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="7ac2e-119">En general, para una matriz diagonal es fácil leer las vectores propios y vectores propios.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="7ac2e-120">Los vectores propios son todos los números que aparecen en la diagonal, y sus respectivas vectores propios son los vectores de unidad con una entrada igual a $1 $ y las entradas restantes son iguales a $0 $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="7ac2e-121">Observe en el ejemplo anterior que el vectores propios de $D $ forma una base para los $ vectores de dimensión $3.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="7ac2e-122">Una base es un conjunto de vectores, de modo que cualquier vector se puede escribir como una combinación lineal de ellos.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="7ac2e-123">Más explícitamente, $v _ 1, $ $v _2 $ y $v _3 $ forman una base si $ se puede escribir cualquier vector $v como $v = a_1 V_1 + a_2 v_2 + a_3 v_3 $ para algunos números $a _ 1 $ , $a _2 $ y $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="7ac2e-124">Recuerde que una matriz de Hermitian (también llamada Self-adjoin) es una matriz cuadrada compleja igual a su propia conjugada compleja, mientras que una matriz de la unitario es una matriz cuadrada compleja cuyo inverso es igual a su conjugado complejo.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="7ac2e-125">En el caso de las matrices Hermitian y unitarios, que son esencialmente las únicas matrices que se encuentran en la informática Quantum, hay un resultado general conocido como [*teorema espectral*](https://en.wikipedia.org/wiki/Spectral_theorem), que afirma lo siguiente: para cualquier $M de matriz de Hermitian o unitario $ , existe una unidad $U de forma $ que $M = U ^ \dagger D U $ para algunas $D de matriz diagonal $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="7ac2e-126">Además, las entradas diagonales de $D serán $ el vectores propios de $M $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="7ac2e-127">Ya sabemos cómo calcular el vectores propios y el vectores propios de una matriz diagonal $D $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="7ac2e-128">Con esta teorema sabemos que si $v $ es un Eigenvector de $D $ con eigenvalue $c $ , es decir, $DV = CV $ , $U ^ \dagger v será $ un eigenvector de $M $ con eigenvalue $c $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="7ac2e-129">Esto se debe a que</span><span class="sxs-lookup"><span data-stu-id="7ac2e-129">This is because</span></span>

<span data-ttu-id="7ac2e-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="7ac2e-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="7ac2e-131">Exponencial de matriz</span><span class="sxs-lookup"><span data-stu-id="7ac2e-131">Matrix Exponentials</span></span>
<span data-ttu-id="7ac2e-132">Una [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) también se puede definir en la analogía exacta con la función exponencial.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="7ac2e-133">La matriz exponencial de una matriz $A $ puede expresarse como</span><span class="sxs-lookup"><span data-stu-id="7ac2e-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="7ac2e-134">$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="7ac2e-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="7ac2e-135">Esto es importante porque la evolución del tiempo mecánico de Quantum se describe mediante una matriz de la forma $e ^ {iB } $ for Hermitian matrix $B $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="7ac2e-136">Por esta razón, la realización de la exponenciación de matriz es una parte fundamental de la informática Quantum y como tal # ofrece rutinas intrínsecas para describir estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="7ac2e-137">Hay muchas maneras de calcular una matriz exponencial en un equipo clásico y, en general, la aproximación numérica de este tipo exponencial es llena con peligros.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="7ac2e-138">Vea el [*topo de Cleve y el préstamo de Charles van. "Diecinueve maneras dudosas de calcular el valor exponencial de una matriz". SIAM revisión 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para obtener más información sobre los desafíos implicados.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="7ac2e-139">La forma más fácil de entender cómo calcular el valor exponencial de una matriz es a través de vectores propios y vectores propios de esa matriz.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="7ac2e-140">En concreto, el teorema espectral descrito anteriormente indica que para cada matriz Hermitian o unitario $A $ existe un $U de matriz unitario $ y una matriz diagonal $D $ tal que $A = u ^ \dagger D u $ .  Debido a las propiedades de Unitarity, tenemos $A ^ 2 = U ^ \dagger D ^ 2 U $ y similares para cualquier $p de energía $ $A ^ p = u ^ \dagger D ^ p U $ .  Si se sustituye por la definición de operador del operador exponencial se obtiene:</span><span class="sxs-lookup"><span data-stu-id="7ac2e-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="7ac2e-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="7ac2e-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="7ac2e-142">En otras palabras, si se transforma en el eigenbasis de la matriz $A $ , al calcular la matriz exponencial es equivalente a calcular el valor exponencial ordinario del vectores propios de la matriz.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="7ac2e-143">Tantas operaciones en la informática Quantum impliquen la realización de la exponenciación de matrices, este truco de transformación en el eigenbasis de una matriz para simplificar la realización del operador exponencial aparece con frecuencia y es la base de muchos algoritmos Quantum, como los métodos de simulación de Quantum de estilo Suzuki y Trotter, que se describen más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="7ac2e-144">Otra propiedad útil es si $B $ es unitario y Hermitian, es decir, $B = b ^ {-1 } = b ^ \dagger $ después $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="7ac2e-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="7ac2e-145">Aplicando esta regla a la expansión anterior de la matriz exponencial y agrupando los términos $ \boldone $ y $B $ juntos, puede ver que para cualquier valor real $x $ la identidad</span><span class="sxs-lookup"><span data-stu-id="7ac2e-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="7ac2e-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="7ac2e-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="7ac2e-147">Porta.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-147">holds.</span></span> <span data-ttu-id="7ac2e-148">Este truco es especialmente útil porque permite tener en cuenta que las exponenciaciones de la matriz de acciones tienen, aunque la dimensión de $B $ sea exponencialmente grande, en el caso especial en que $B $ sea unitario y Hermitian.</span><span class="sxs-lookup"><span data-stu-id="7ac2e-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
