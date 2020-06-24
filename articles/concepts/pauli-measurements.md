---
title: Medidas Pauli
description: Obtenga información sobre cómo trabajar con operaciones de medición de Pauli de un solo y varios qubit.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269480"
---
# <a name="pauli-measurements"></a><span data-ttu-id="fd840-103">Medidas Pauli</span><span class="sxs-lookup"><span data-stu-id="fd840-103">Pauli Measurements</span></span>

<span data-ttu-id="fd840-104">En las conversaciones anteriores, nos hemos centrado en las mediciones de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="fd840-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="fd840-105">De hecho, hay otras medidas comunes que se producen en la informática Quantum que, desde una perspectiva de notación, son convenientes para expresar en términos de mediciones de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="fd840-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="fd840-106">A medida que trabaje con Q #, el tipo más común de medidas en las que se ejecutará probablemente serán *mediciones de Pauli*, que generalizan las mediciones de base de cálculo para incluir medidas en otras bases y de paridad entre diferentes qubits.</span><span class="sxs-lookup"><span data-stu-id="fd840-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="fd840-107">En tales casos, es habitual analizar un operador Pauli, en general un operador como $X, Y, Z $ o $Z \otimes z, x \otimes x, x y \otimes , etc $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="fd840-108">En Q #, los operadores de Pauli de varios qubit se suelen representar mediante matrices de tipo `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="fd840-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="fd840-109">Por ejemplo, para representar $X \otimes Z \otimes Y $ , puede usar la matriz `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="fd840-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="fd840-110">La explicación de la medida en términos de operadores Pauli es especialmente común en el subcampo de la corrección de errores Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="fd840-111">En Q #, seguimos una Convención similar; ahora se explica esta vista alternativa de las medidas.</span><span class="sxs-lookup"><span data-stu-id="fd840-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="fd840-112">Antes de profundizar en los detalles de cómo pensar en una medición Pauli, es útil pensar en qué medida un qubit único dentro de un equipo Quantum se realiza en el estado de Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="fd840-113">Imagine que tenemos un $ Estado de quantum $n-qubit y, a continuación, la medición de una qubit de inmediato pone en espera la mitad de las posibilidades de $2 ^ n $ que podrían estar en el estado.</span><span class="sxs-lookup"><span data-stu-id="fd840-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="fd840-114">En otras palabras, la medida proyecta el estado de cuanto en uno de los dos espacios a medio.</span><span class="sxs-lookup"><span data-stu-id="fd840-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="fd840-115">Podemos generalizar el modo en que pensamos en medida para reflejar este Intuition.</span><span class="sxs-lookup"><span data-stu-id="fd840-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="fd840-116">Para identificar de manera concisa estos subespacios, necesitamos un lenguaje para describirlos.</span><span class="sxs-lookup"><span data-stu-id="fd840-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="fd840-117">Una manera de describir los dos subespacios es mediante la especificación de una matriz que solo tiene dos vectores propios únicos, tomadas por Convención para que sea $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="fd840-118">Para obtener un ejemplo sencillo de la descripción de los subespacios de esta manera, considere la posibilidad de $Z $ :</span><span class="sxs-lookup"><span data-stu-id="fd840-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="fd840-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-119">$$ \begin{align}</span></span>
  <span data-ttu-id="fd840-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd840-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="fd840-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-121">\end{align}</span></span>
$$

<span data-ttu-id="fd840-122">Al leer los elementos diagonales de la matriz Pauli-$Z $ , podemos ver que $Z $ tiene dos vectores propios, $ \ket{0 } $ y $ \ket{1 } $, con el vectores propios $ \pm 1 correspondiente $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="fd840-123">Por lo tanto, si se mide el qubit y `Zero` se obtiene (que corresponde al estado $ \ket{0 } $), sabemos que el estado de nuestro qubit es un $ + 1 $ eigenstate del $ operador $Z.</span><span class="sxs-lookup"><span data-stu-id="fd840-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="fd840-124">Del mismo modo, si obtenemos `One` , sabemos que el estado de nuestro qubit es un $ eigenstate de $Z $-1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="fd840-125">Este proceso se conoce en el idioma de las medidas de Pauli como "medición de Pauli $Z $ " y es totalmente equivalente a realizar una medición de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="fd840-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="fd840-126">Cualquier \times $ matriz de $2 2 que sea una transformación de $Z $ también cumple este criterio.</span><span class="sxs-lookup"><span data-stu-id="fd840-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="fd840-127">Es decir, también podríamos usar una matriz $A = U ^ \dagger Z U $ , donde $U $ es cualquier otra matriz de unidades de unidad, para proporcionar una matriz que defina los dos resultados de una medida en su vectores propios $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="fd840-128">La notación de las medidas Pauli hace referencia a esta equivalencia de unitarios mediante la identificación de las medidas $X, Y, Z $ como medidas equivalentes que puede hacer para obtener información de un qubit.</span><span class="sxs-lookup"><span data-stu-id="fd840-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="fd840-129">Estas medidas se proporcionan a continuación para mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="fd840-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="fd840-130">Medida Pauli</span><span class="sxs-lookup"><span data-stu-id="fd840-130">Pauli Measurement</span></span>  |<span data-ttu-id="fd840-131">Transformación unitario</span><span class="sxs-lookup"><span data-stu-id="fd840-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="fd840-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="fd840-132">$Z$</span></span>               | <span data-ttu-id="fd840-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-133">$\boldone$</span></span>             |
| <span data-ttu-id="fd840-134">$X$</span><span class="sxs-lookup"><span data-stu-id="fd840-134">$X$</span></span>               | <span data-ttu-id="fd840-135">$H$</span><span class="sxs-lookup"><span data-stu-id="fd840-135">$H$</span></span>                    |
| <span data-ttu-id="fd840-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="fd840-136">$Y$</span></span>               | <span data-ttu-id="fd840-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="fd840-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="fd840-138">Es decir, el uso de este lenguaje, "Measure $Y $ " es equivalente a aplicar $HS ^ \dagger $ y, a continuación, medir en función de la base de cálculo, donde [`S`](xref:microsoft.quantum.intrinsic.s) es una operación Quantum intrínseca que a veces se denomina "puerta de fase" y se puede simular mediante la matriz unitario</span><span class="sxs-lookup"><span data-stu-id="fd840-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="fd840-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-139">$$ \begin{align}</span></span>
    <span data-ttu-id="fd840-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd840-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="fd840-141">1 & 0 \\ \\ 0 & i \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd840-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="fd840-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-142">\end{align}</span></span>
$$

<span data-ttu-id="fd840-143">También es equivalente a aplicar $HS ^ \dagger $ al vector de estado de Quantum y, a continuación, medir $Z $ , de modo que la operación siguiente sea equivalente a `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="fd840-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="fd840-144">A continuación, se encontraría el estado correcto transformando de nuevo a la base de cálculo, que se aplica a la aplicación $ de $SH al vector de estado de Quantum; en el fragmento de código anterior, la transformación de nuevo a la base computacional se controla automáticamente mediante el uso del `within … apply` bloque.</span><span class="sxs-lookup"><span data-stu-id="fd840-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="fd840-145">En Q #, se indica el resultado---es decir, la información clásica extraída de la interacción con el estado---se proporciona mediante un `Result` valor $j \en \\ {\Texttt{Zero } , \texttt{One } \\ } $ que indica si el resultado está en la variable $ (-1) ^ j $ eigenspace del operador Pauli medido.</span><span class="sxs-lookup"><span data-stu-id="fd840-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="fd840-146">Mediciones de varios qubit</span><span class="sxs-lookup"><span data-stu-id="fd840-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="fd840-147">Las medidas de los operadores qubit de Pauli se definen de forma similar, como se aprecia en:</span><span class="sxs-lookup"><span data-stu-id="fd840-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="fd840-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="fd840-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="fd840-149">Por lo tanto, los productos tensores de dos operadores Pauli-$Z $ forman una matriz formada por dos espacios compuestos de $ + 1 $ y $-1 $ vectores propios.</span><span class="sxs-lookup"><span data-stu-id="fd840-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="fd840-150">Al igual que en el caso de un solo qubit, ambos constituyen un medio de espacio, lo que significa que la mitad del espacio de vector accesible pertenece a la eigenspace $ + 1 $ y la mitad restante al eigenspace $-1 $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="fd840-151">En general, es fácil ver a partir de la definición del producto tensores que cualquier producto tensores de operadores Pauli-$Z $ y la identidad también obedece esto.</span><span class="sxs-lookup"><span data-stu-id="fd840-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="fd840-152">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="fd840-152">For example,</span></span>

<span data-ttu-id="fd840-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-153">$$ \begin{align}</span></span>
    <span data-ttu-id="fd840-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="fd840-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="fd840-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="fd840-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="fd840-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-156">\end{align}</span></span>
$$

<span data-ttu-id="fd840-157">Como antes, cualquier transformación unitario de estas matrices también describe dos espacios a la mitad etiquetados por $ \pm 1 $ vectores propios.</span><span class="sxs-lookup"><span data-stu-id="fd840-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="fd840-158">Por ejemplo, $X \otimes X = h \otimes h (z \otimes z) h \otimes h $ de la identidad que $Z = HxH $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="fd840-159">De forma similar al caso One-qubit, todas las dos qubit Pauli-Measurements se pueden escribir como $U ^ \dagger (Z \otimes \id) U $ para las \times $ matrices unitarios de $4 4 $U $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="fd840-160">En la tabla siguiente se enumeran las transformaciones.</span><span class="sxs-lookup"><span data-stu-id="fd840-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="fd840-161">En la tabla siguiente, usamos $ \operatorname{SWAP } $ para indicar la matriz $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="fd840-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="fd840-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="fd840-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & 1 & 0 & 0 0 & 0 & \\ \\ \\ \\ 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="fd840-164">$ $ se usa para simular la operación intrínseca [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="fd840-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="fd840-165">Medida Pauli</span><span class="sxs-lookup"><span data-stu-id="fd840-165">Pauli Measurement</span></span>     |<span data-ttu-id="fd840-166">Transformación unitario</span><span class="sxs-lookup"><span data-stu-id="fd840-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="fd840-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="fd840-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="fd840-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="fd840-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="fd840-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="fd840-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="fd840-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="fd840-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="fd840-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="fd840-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="fd840-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="fd840-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="fd840-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="fd840-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="fd840-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="fd840-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="fd840-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="fd840-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="fd840-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="fd840-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="fd840-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="fd840-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="fd840-181">$Z\otimes Z$</span></span> | <span data-ttu-id="fd840-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="fd840-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="fd840-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="fd840-183">$X\otimes Z$</span></span> | <span data-ttu-id="fd840-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="fd840-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="fd840-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="fd840-185">$Y\otimes Z$</span></span> | <span data-ttu-id="fd840-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="fd840-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="fd840-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="fd840-187">$Z\otimes X$</span></span> | <span data-ttu-id="fd840-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="fd840-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="fd840-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="fd840-189">$X\otimes X$</span></span> | <span data-ttu-id="fd840-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="fd840-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="fd840-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="fd840-191">$Y\otimes X$</span></span> | <span data-ttu-id="fd840-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="fd840-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="fd840-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="fd840-193">$Z\otimes Y$</span></span> | <span data-ttu-id="fd840-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="fd840-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="fd840-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="fd840-195">$X\otimes Y$</span></span> | <span data-ttu-id="fd840-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="fd840-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="fd840-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="fd840-197">$Y\otimes Y$</span></span> | <span data-ttu-id="fd840-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="fd840-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="fd840-199">En este caso, la [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operación aparece por el siguiente motivo.</span><span class="sxs-lookup"><span data-stu-id="fd840-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="fd840-200">Cada medida de Pauli que no incluye la matriz $ \boldone equivale $ a una unitario a $Z \otimes Z $ por la razón anterior.</span><span class="sxs-lookup"><span data-stu-id="fd840-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="fd840-201">Los vectores propios de $Z \otimes Z $ solo dependen de la paridad del qubits que conforman cada vector de base de cálculo, y las operaciones controladas y no sirven para calcular esta paridad y almacenarla en el primer bit.</span><span class="sxs-lookup"><span data-stu-id="fd840-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="fd840-202">Después, una vez que se mide el primer bit, podemos recuperar la identidad del espacio medio resultante, que es equivalente a medir el operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="fd840-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="fd840-203">Una nota adicional: aunque puede ser tentador asumir que la medición de $Z \otimes z $ es la misma que la medición secuencial $Z \otimes \mathbb{1 } $ y, a continuación, $ \mathbb{1 } \otimes z $ , esta suposición sería falsa.</span><span class="sxs-lookup"><span data-stu-id="fd840-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="fd840-204">La razón es que medir $Z \otimes Z $ proyecta el estado de cuanto en el eigenstate $ + 1 $ o $-1 $ de estos operadores.</span><span class="sxs-lookup"><span data-stu-id="fd840-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="fd840-205">La medición de $Z \otimes \mathbb{1 } $ y, a continuación, $ \Mathbb{1 } \otimes Z $ proyecta el vector de estado Quantum primero en un espacio medio de $Z \otimes \mathbb{1 } $ y, a continuación, en un espacio medio de $ \mathbb{1 } \otimes Z $ . Como hay cuatro vectores de base de cálculo, al realizar ambas mediciones se reduce el estado a un cuarto de espacio y, por tanto, se reduce a un vector de base de cálculo único.</span><span class="sxs-lookup"><span data-stu-id="fd840-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="fd840-206">Correlaciones entre qubits</span><span class="sxs-lookup"><span data-stu-id="fd840-206">Correlations between qubits</span></span>
<span data-ttu-id="fd840-207">Otra forma de ver los productos de tensores de matrices de Pauli, como $X \otimes X $ o $Z \otimes Z, $ es que estas medidas permiten examinar la información almacenada en las correlaciones entre las dos qubits.</span><span class="sxs-lookup"><span data-stu-id="fd840-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="fd840-208">La medición \otimes de $X \id $ permite ver la información que se almacena localmente en el primer qubit.</span><span class="sxs-lookup"><span data-stu-id="fd840-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="fd840-209">Aunque ambos tipos de medidas son igualmente valiosos en la informática Quantum, el primero ilumina la potencia de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="fd840-210">Revela que, con frecuencia, la información que desea aprender no se almacena en ningún qubit único, sino que se almacena de forma no local en todas las qubits a la vez y, por lo tanto, solo al examinarla a través de una medida conjunta (por ejemplo $Z \otimes Z $ ) hace que esta información se convierta en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="fd840-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="fd840-211">Por ejemplo, en la corrección de errores, a menudo queremos obtener información sobre el error que se produjo al no aprender nada sobre el estado que estamos intentando proteger.</span><span class="sxs-lookup"><span data-stu-id="fd840-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="fd840-212">[En el ejemplo de código bit-Flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) se muestra un ejemplo de cómo puede hacerlo con medidas como $Z \otimes Z \otimes \id $ y $ \id \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="fd840-213">También se pueden medir los operadores arbitrarios de Pauli, como $X \otimes Y \Otimes Z \otimes \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="fd840-214">Todos estos productos tensores de los operadores Pauli tienen solo dos vectores propios $ \pm 1 $ y ambos eigenspaces constituyen los semiespacios del espacio vectorial completo.</span><span class="sxs-lookup"><span data-stu-id="fd840-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="fd840-215">Por lo tanto, coinciden con los requisitos indicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fd840-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="fd840-216">En Q #, estas medidas devuelven $j $ si la medida produce un resultado en el eigenspace del signo $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="fd840-217">El hecho de tener medidas Pauli como una característica integrada en Q # es útil porque la medición de estos operadores requiere largas cadenas de puertas y transformaciones controladas no que describan la creación de diagonal $U $ puerta necesaria para expresar la operación como un producto tensores de $Z $ y $ \id $ . Al poder especificar que desea realizar una de estas medidas predefinidas, no es necesario preocuparse por cómo transformar la base de forma que una medición de base de cálculo proporcione la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="fd840-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="fd840-218">Q # controla todas las transformaciones de base necesarias automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fd840-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="fd840-219">Para obtener más información, vea [`Measure`](xref:microsoft.quantum.intrinsic.measure) las [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operaciones y.</span><span class="sxs-lookup"><span data-stu-id="fd840-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="fd840-220">Teorema sin clonación</span><span class="sxs-lookup"><span data-stu-id="fd840-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="fd840-221">La información de Quantum es eficaz.</span><span class="sxs-lookup"><span data-stu-id="fd840-221">Quantum information is powerful.</span></span>
<span data-ttu-id="fd840-222">Nos permite hacer cosas sorprendentes, como números de factor exponencialmente más rápidos que los mejores algoritmos clásicos conocidos, o simular eficazmente sistemas de electrones correlacionados que requieran el costo exponencial para simular con precisión.</span><span class="sxs-lookup"><span data-stu-id="fd840-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="fd840-223">Sin embargo, existen limitaciones en cuanto a la eficacia de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="fd840-224">Una de estas limitaciones viene determinada por el *teorema sin clonación*.</span><span class="sxs-lookup"><span data-stu-id="fd840-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="fd840-225">La teorema sin clonación tiene un nombre acertado.</span><span class="sxs-lookup"><span data-stu-id="fd840-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="fd840-226">No permite la clonación de Estados de Quantum genéricos por un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="fd840-227">La prueba de Teorema es bastante sencilla.</span><span class="sxs-lookup"><span data-stu-id="fd840-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="fd840-228">Aunque una prueba completa del teorema sin clonación es un poco muy técnico para nuestro debate aquí, la prueba, en el caso de que no haya ningún qubits auxiliar adicional, se encuentra dentro de nuestro ámbito (los qubits auxiliares son qubits que se usan para el espacio de desecho durante un cálculo y se usan y administran fácilmente en Q #, vea el [qubits prestado](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="fd840-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="fd840-229">Para este tipo de equipo Quantum, la operación de clonación debe describirse mediante una matriz de unitario.</span><span class="sxs-lookup"><span data-stu-id="fd840-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="fd840-230">No permitimos la medición, ya que dañaría el estado de Quantum que estamos intentando clonar.</span><span class="sxs-lookup"><span data-stu-id="fd840-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="fd840-231">Para simular la operación de clonación, queremos que la matriz de unitarios se use para tener la propiedad $ $ U \ket { \psi } \ket{0 } = \ket { \psi } { \ket \psi}</span><span class="sxs-lookup"><span data-stu-id="fd840-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="fd840-232">$ $ para cualquier estado $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="fd840-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="fd840-233">La propiedad linearity de la multiplicación de matrices implica que para cualquier segundo estado de Quantum $ \ket { \phi } $,</span><span class="sxs-lookup"><span data-stu-id="fd840-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="fd840-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-234">$$ \begin{align}</span></span>
    <span data-ttu-id="fd840-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="fd840-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="fd840-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="fd840-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="fd840-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="fd840-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="fd840-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="fd840-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="fd840-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd840-239">\end{align}</span></span>
$$

<span data-ttu-id="fd840-240">Esto proporciona el Intuition fundamental detrás del teorema sin clonación: cualquier dispositivo que copie un estado de Quantum desconocido debe inducir errores en al menos algunos de los Estados que copia.</span><span class="sxs-lookup"><span data-stu-id="fd840-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="fd840-241">Aunque la principal suposición de que el Cloner actúa de forma lineal en el estado de la entrada se puede infringir a través de la adición y medición de qubits auxiliares, estas interacciones también pierden información sobre el sistema a través de las estadísticas de medida y evitan la clonación exacta en estos casos.</span><span class="sxs-lookup"><span data-stu-id="fd840-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="fd840-242">Para obtener una prueba más completa de la teorema sin clonación, vea [para obtener más información](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="fd840-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="fd840-243">La teorema sin clonación es importante para el conocimiento cualitativo de la informática Quantum, ya que si pudiera clonar los Estados de Quantum de forma económica, se le concederá una capacidad casi mágica para aprender de los Estados de Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="fd840-244">En realidad, puede infringir el principio de incertidumbre de vaunted de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="fd840-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="fd840-245">Como alternativa, puede usar una Cloner óptima para tomar una muestra única de una distribución de Quantum compleja y obtener información sobre todo lo que podría obtener más información sobre esa distribución desde un solo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd840-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="fd840-246">Esto sería similar a la forma de voltear una moneda y observar los cabezales y, a continuación, al decirles a un amigo sobre el resultado de responder "Ah la distribución de esa moneda debe ser Bernoulli con $p = 0.512643 \ ldots $ !".</span><span class="sxs-lookup"><span data-stu-id="fd840-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="fd840-247">Este tipo de instrucción sería no SENS, porque un bit de información (el resultado de los cabezales) simplemente no puede proporcionar los numerosos bits de información necesaria para codificar la distribución sin información importante de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="fd840-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="fd840-248">Del mismo modo, sin información previa, no se puede clonar absolutamente un estado de Quantum, al igual que no se puede preparar un conjunto de esas monedas sin conocer $p $ .</span><span class="sxs-lookup"><span data-stu-id="fd840-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="fd840-249">La información no es gratuita en la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="fd840-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="fd840-250">Cada qubit medido proporciona un único bit de información y el teorema sin clonación muestra que no hay ninguna puerta trasera que pueda aprovecharse para evitar el equilibrio fundamental entre la información obtenida sobre el sistema y la perturbación invocada.</span><span class="sxs-lookup"><span data-stu-id="fd840-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
