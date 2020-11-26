---
<span data-ttu-id="d9d59-101">Título: Descripción de las medidas de Pauli: Aprenda a trabajar con operaciones de medición Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="d9d59-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="d9d59-102">Autor: bradben UID: Microsoft. Quantum. Concepts. Pauli ms. Author: v-benbra ms. Date: 12/11/2017 ms. topic: article no-LOC:</span><span class="sxs-lookup"><span data-stu-id="d9d59-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="d9d59-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="d9d59-103">"Q#"</span></span>
- <span data-ttu-id="d9d59-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="d9d59-104">"$$v"</span></span>
- <span data-ttu-id="d9d59-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-105">"$$"</span></span>
- <span data-ttu-id="d9d59-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-106">"$$"</span></span>
- <span data-ttu-id="d9d59-107">"$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-107">"$"</span></span>
- <span data-ttu-id="d9d59-108">"$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-108">"$"</span></span>
- <span data-ttu-id="d9d59-109">"$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-109">"$"</span></span>
- <span data-ttu-id="d9d59-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="d9d59-110">"$$"</span></span>
- <span data-ttu-id="d9d59-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="d9d59-111">"\cdots"</span></span>
- <span data-ttu-id="d9d59-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="d9d59-112">"bmatrix"</span></span>
- <span data-ttu-id="d9d59-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="d9d59-113">"\ddots"</span></span>
- <span data-ttu-id="d9d59-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="d9d59-114">"\equiv"</span></span>
- <span data-ttu-id="d9d59-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="d9d59-115">"\sum"</span></span>
- <span data-ttu-id="d9d59-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="d9d59-116">"\begin"</span></span>
- <span data-ttu-id="d9d59-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="d9d59-117">"\end"</span></span>
- <span data-ttu-id="d9d59-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="d9d59-118">"\sqrt"</span></span>
- <span data-ttu-id="d9d59-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="d9d59-119">"\otimes"</span></span>
- <span data-ttu-id="d9d59-120">"{"</span><span class="sxs-lookup"><span data-stu-id="d9d59-120">"{"</span></span>
- <span data-ttu-id="d9d59-121">"}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-121">"}"</span></span>
- <span data-ttu-id="d9d59-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="d9d59-122">"\text"</span></span>
- <span data-ttu-id="d9d59-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="d9d59-123">"\phi"</span></span>
- <span data-ttu-id="d9d59-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="d9d59-124">"\kappa"</span></span>
- <span data-ttu-id="d9d59-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="d9d59-125">"\psi"</span></span>
- <span data-ttu-id="d9d59-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="d9d59-126">"\alpha"</span></span>
- <span data-ttu-id="d9d59-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="d9d59-127">"\beta"</span></span>
- <span data-ttu-id="d9d59-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="d9d59-128">"\gamma"</span></span>
- <span data-ttu-id="d9d59-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="d9d59-129">"\delta"</span></span>
- <span data-ttu-id="d9d59-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="d9d59-130">"\omega"</span></span>
- <span data-ttu-id="d9d59-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="d9d59-131">"\bra"</span></span>
- <span data-ttu-id="d9d59-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="d9d59-132">"\ket"</span></span>
- <span data-ttu-id="d9d59-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="d9d59-133">"\boldone"</span></span>
- <span data-ttu-id="d9d59-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="d9d59-134">"\\\\"</span></span>
- <span data-ttu-id="d9d59-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="d9d59-135">"\\"</span></span>
- <span data-ttu-id="d9d59-136">"="</span><span class="sxs-lookup"><span data-stu-id="d9d59-136">"="</span></span>
- <span data-ttu-id="d9d59-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="d9d59-137">"\frac"</span></span>
- <span data-ttu-id="d9d59-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="d9d59-138">"\text"</span></span>
- <span data-ttu-id="d9d59-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="d9d59-139">"\mapsto"</span></span>
- <span data-ttu-id="d9d59-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="d9d59-140">"\dagger"</span></span>
- <span data-ttu-id="d9d59-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="d9d59-141">"\to"</span></span>
- <span data-ttu-id="d9d59-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-142">"\begin{cases}"</span></span>
- <span data-ttu-id="d9d59-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-143">"\end{cases}"</span></span>
- <span data-ttu-id="d9d59-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="d9d59-144">"\operatorname"</span></span>
- <span data-ttu-id="d9d59-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="d9d59-145">"\braket"</span></span>
- <span data-ttu-id="d9d59-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="d9d59-146">"\id"</span></span>
- <span data-ttu-id="d9d59-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="d9d59-147">"\expect"</span></span>
- <span data-ttu-id="d9d59-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="d9d59-148">"\defeq"</span></span>
- <span data-ttu-id="d9d59-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="d9d59-149">"\variance"</span></span>
- <span data-ttu-id="d9d59-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="d9d59-150">"\dd"</span></span>
- <span data-ttu-id="d9d59-151">"&"</span><span class="sxs-lookup"><span data-stu-id="d9d59-151">"&"</span></span>
- <span data-ttu-id="d9d59-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-152">"\begin{align}"</span></span>
- <span data-ttu-id="d9d59-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-153">"\end{align}"</span></span>
- <span data-ttu-id="d9d59-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="d9d59-154">"\Lambda"</span></span>
- <span data-ttu-id="d9d59-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="d9d59-155">"\lambda"</span></span>
- <span data-ttu-id="d9d59-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="d9d59-156">"\Omega"</span></span>
- <span data-ttu-id="d9d59-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="d9d59-157">"\mathrm"</span></span>
- <span data-ttu-id="d9d59-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="d9d59-158">"\left"</span></span>
- <span data-ttu-id="d9d59-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="d9d59-159">"\right"</span></span>
- <span data-ttu-id="d9d59-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="d9d59-160">"\qquad"</span></span>
- <span data-ttu-id="d9d59-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="d9d59-161">"\times"</span></span>
- <span data-ttu-id="d9d59-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="d9d59-162">"\big"</span></span>
- <span data-ttu-id="d9d59-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="d9d59-163">"\langle"</span></span>
- <span data-ttu-id="d9d59-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="d9d59-164">"\rangle"</span></span>
- <span data-ttu-id="d9d59-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="d9d59-165">"\bigg"</span></span>
- <span data-ttu-id="d9d59-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="d9d59-166">"\Big"</span></span>
- <span data-ttu-id="d9d59-167">"|"</span><span class="sxs-lookup"><span data-stu-id="d9d59-167">"|"</span></span>
- <span data-ttu-id="d9d59-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="d9d59-168">"\mathbb"</span></span>
- <span data-ttu-id="d9d59-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="d9d59-169">"\vec"</span></span>
- <span data-ttu-id="d9d59-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="d9d59-170">"\in"</span></span>
- <span data-ttu-id="d9d59-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="d9d59-171">"\texttt"</span></span>
- <span data-ttu-id="d9d59-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="d9d59-172">"\ne"</span></span>
- <span data-ttu-id="d9d59-173">"<"</span><span class="sxs-lookup"><span data-stu-id="d9d59-173">"<"</span></span>
- <span data-ttu-id="d9d59-174">">"</span><span class="sxs-lookup"><span data-stu-id="d9d59-174">">"</span></span>
- <span data-ttu-id="d9d59-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="d9d59-175">"\leq"</span></span>
- <span data-ttu-id="d9d59-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="d9d59-176">"\geq"</span></span>
- <span data-ttu-id="d9d59-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="d9d59-177">"~~"</span></span>
- <span data-ttu-id="d9d59-178">"~"</span><span class="sxs-lookup"><span data-stu-id="d9d59-178">"~"</span></span>
- <span data-ttu-id="d9d59-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="d9d59-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d9d59-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="d9d59-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="d9d59-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="d9d59-182">Medidas Pauli</span><span class="sxs-lookup"><span data-stu-id="d9d59-182">Pauli Measurements</span></span>

<span data-ttu-id="d9d59-183">En las conversaciones anteriores, nos hemos centrado en las mediciones de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="d9d59-184">De hecho, hay otras medidas comunes que se producen en la informática Quantum que, desde una perspectiva de notación, son convenientes para expresar en términos de mediciones de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="d9d59-185">A medida que trabaje con Q# , el tipo más común de medidas en las que se ejecutará probablemente serán *mediciones Paulis*, que generalizan las mediciones de base de cálculo para incluir medidas en otras bases y de paridad entre diferentes qubits.</span><span class="sxs-lookup"><span data-stu-id="d9d59-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="d9d59-186">En tales casos, es habitual analizar un operador Pauli, en general un operador como $ X, Y, z $ o $ z \otimes z, x \otimes x, x y \otimes , etc $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span> 

> [!TIP]
<span data-ttu-id="d9d59-187">> En Q# , los operadores de Pauli de varios qubit suelen estar representados por matrices de tipo `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="d9d59-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="d9d59-188">> Por ejemplo, para representar $ X \otimes Z \otimes Y $ , puede usar la matriz `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="d9d59-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="d9d59-189">La explicación de la medida en términos de operadores Pauli es especialmente común en el subcampo de la corrección de errores Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="d9d59-190">En Q# , seguimos una Convención similar; ahora explicaremos esta vista alternativa de las medidas.</span><span class="sxs-lookup"><span data-stu-id="d9d59-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="d9d59-191">Antes de profundizar en los detalles de cómo pensar en una medición Pauli, es útil pensar en qué medida un qubit único dentro de un equipo Quantum se realiza en el estado de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="d9d59-192">Imagine que tenemos un $ $ Estado de Quantum n-qubit; después, la medición de una qubit de inmediato pone a la mitad de las $ 2 ^ n $ posibilidades de que el Estado pudiera estar en.</span><span class="sxs-lookup"><span data-stu-id="d9d59-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="d9d59-193">En otras palabras, la medida proyecta el estado de cuanto en uno de los dos espacios a medio.</span><span class="sxs-lookup"><span data-stu-id="d9d59-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="d9d59-194">Podemos generalizar el modo en que pensamos en medida para reflejar este Intuition.</span><span class="sxs-lookup"><span data-stu-id="d9d59-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="d9d59-195">Para identificar de manera concisa estos subespacios, necesitamos un lenguaje para describirlos.</span><span class="sxs-lookup"><span data-stu-id="d9d59-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="d9d59-196">Una manera de describir los dos subespacios es mediante la especificación de una matriz que solo tiene dos vectores propios únicos, tomadas por Convención para que sea $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="d9d59-197">Para obtener un ejemplo sencillo de la descripción de los subespacios de esta manera, considere $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="d9d59-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="d9d59-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="d9d59-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d9d59-199">Al leer los elementos diagonales de la matriz Pauli- $ z $ , podemos ver que $ Z $ tiene dos vectores propios, $ \ket { 0 } $ y $ \ket { 1 } $ , con vectores propios $ \pm 1 correspondiente $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="d9d59-200">Por lo tanto, si se mide el qubit y se obtiene `Zero` (correspondiente al estado $ \ket { 0 } $ ), sabemos que el estado de nuestro qubit es un $ eigenstate + 1 $ del $ $ operador Z.</span><span class="sxs-lookup"><span data-stu-id="d9d59-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="d9d59-201">Del mismo modo, si obtenemos `One` , sabemos que el estado de nuestro qubit es $ -1 $ eigenstate de $ Z $ . Este proceso se conoce en el idioma de las medidas de Pauli como "medición de Pauli $ Z $ " y es totalmente equivalente a realizar una medición de base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="d9d59-202">Cualquier $ \times matriz 2 2 $ que sea una transformación unitario de $ Z $ también cumple este criterio.</span><span class="sxs-lookup"><span data-stu-id="d9d59-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="d9d59-203">Es decir, también podríamos usar una matriz u $ = ^ \dagger Z u $ , donde $ U $ es cualquier otra matriz de unidades unitarios, para proporcionar una matriz que defina los dos resultados de una medida en su $ \pm 1 $ vectores propios.</span><span class="sxs-lookup"><span data-stu-id="d9d59-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="d9d59-204">La notación de las medidas Pauli hace referencia a esta equivalencia de unitarios mediante la identificación de las $ medidas X, Y, Z $ como medidas equivalentes que puede hacer para obtener información de un qubit.</span><span class="sxs-lookup"><span data-stu-id="d9d59-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="d9d59-205">Estas medidas se proporcionan a continuación para mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="d9d59-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="d9d59-206">|Pauli  | transformación unitario de medida  |</span><span class="sxs-lookup"><span data-stu-id="d9d59-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="d9d59-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="d9d59-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="d9d59-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="d9d59-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="d9d59-209">|$ $ Y | $Hs ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="d9d59-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="d9d59-210">Es decir, con este lenguaje, "Measure $ Y $ " es equivalente a aplicar $ HS ^ \dagger $ y luego medir en función del cálculo, donde [`S`](xref:Microsoft.Quantum.Intrinsic.S) es una operación de Quantum intrínseca que a veces se denomina "puerta de fase" y se puede simular mediante la matriz de la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="d9d59-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:Microsoft.Quantum.Intrinsic.S) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="d9d59-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="d9d59-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="d9d59-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="d9d59-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d9d59-213">También es equivalente a aplicar $ HS ^ \dagger $ al vector de estado de Quantum y después medir $ Z $ , de modo que la operación siguiente sea equivalente a `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="d9d59-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="d9d59-214">A continuación, se encontraría el estado correcto transformando de nuevo a la base de cálculo, que equivale a aplicar $ SH $ al vector de estado de Quantum; en el fragmento de código anterior, la transformación de vuelta a la base de cálculo se controla automáticamente mediante el uso del `within … apply` bloque.</span><span class="sxs-lookup"><span data-stu-id="d9d59-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="d9d59-215">En Q# , se indica el resultado---es decir, la información clásica extraída de la interacción con el estado---se proporciona mediante un `Result` valor $ j \in \\ { \texttt { cero } , \texttt { uno } \\ } $ que indica si el resultado está en el $ (-1) ^ j $ eigenspace del operador Pauli medido.</span><span class="sxs-lookup"><span data-stu-id="d9d59-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="d9d59-216">Mediciones de varios qubit</span><span class="sxs-lookup"><span data-stu-id="d9d59-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="d9d59-217">Las medidas de los operadores qubit de Pauli se definen de forma similar, como se aprecia en:</span><span class="sxs-lookup"><span data-stu-id="d9d59-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="d9d59-218">Z \otimes z = \begin{bmatrix} 1 & 0 & 0 0 0 & \\\\ & -1 & 0 & 0 0 0 \\\\ & & -1 0 0 0 & \\\\ & & & 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="d9d59-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="d9d59-219">Por lo tanto, los productos tensores de dos operadores Pauli- $ Z $ forman una matriz formada por dos espacios compuestos de $ + 1 $ y $ -1 $ vectores propios.</span><span class="sxs-lookup"><span data-stu-id="d9d59-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="d9d59-220">Al igual que en el caso de un solo qubit, ambos constituyen un medio de espacio, lo que significa que la mitad del espacio de vector accesible pertenece a la $ eigenspace + 1 $ y la mitad restante al $ eigenspace-1 $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="d9d59-221">En general, es fácil ver a partir de la definición del producto tensores que cualquier producto tensores de los operadores Pauli- $ Z $ y la identidad también obedece esto.</span><span class="sxs-lookup"><span data-stu-id="d9d59-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="d9d59-222">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="d9d59-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="d9d59-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="d9d59-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="d9d59-224">1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="d9d59-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="d9d59-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="d9d59-227">0 0 0 & & & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="d9d59-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d9d59-228">Como antes, cualquier transformación unitario de estas matrices también describe dos espacios a la mitad etiquetados por $ \pm 1 $ vectores propios.</span><span class="sxs-lookup"><span data-stu-id="d9d59-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="d9d59-229">Por ejemplo, $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  de la identidad que $ Z = HxH $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="d9d59-230">Al igual que en el caso de una qubit, todas las medidas Pauli-qubit se pueden escribir como $ u ^ \dagger (Z \otimes \id ) u $ para $ 4 \times 4 $ matrices unitarios $ u $ . En la tabla siguiente se enumeran las transformaciones.</span><span class="sxs-lookup"><span data-stu-id="d9d59-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="d9d59-231">>En la tabla siguiente, usamos $ \operatorname { swap } $ para indicar la matriz >$$</span><span class="sxs-lookup"><span data-stu-id="d9d59-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="d9d59-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="d9d59-232">> \begin{align}</span></span>
<span data-ttu-id="d9d59-233">>     \operatorname{INTERCAMBIO } & de =</span><span class="sxs-lookup"><span data-stu-id="d9d59-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="d9d59-234">>     \left( \begin { matriz}</span><span class="sxs-lookup"><span data-stu-id="d9d59-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="d9d59-235">>1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="d9d59-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="d9d59-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="d9d59-238">>0 & 0 & 0 & 1 > \end { matriz } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="d9d59-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="d9d59-239">> $$</span><span class="sxs-lookup"><span data-stu-id="d9d59-239">> $$</span></span>
<span data-ttu-id="d9d59-240">> se usa para simular la operación intrínseca [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="d9d59-240">> used to simulate the intrinsic operation [`SWAP`](xref:Microsoft.Quantum.Intrinsic).</span></span>

<span data-ttu-id="d9d59-241">|Pauli     | transformación unitario de medida  |</span><span class="sxs-lookup"><span data-stu-id="d9d59-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="d9d59-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="d9d59-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="d9d59-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="d9d59-244">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="d9d59-245">|$\boldone \otimes $ | $ \operatorname { intercambio } Z $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d9d59-246">|$\boldone \otimes $ | $ \otimes \boldone \operatorname { intercambio } X (H $ )|</span><span class="sxs-lookup"><span data-stu-id="d9d59-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d9d59-247">|$\boldone \otimes s $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { swap } $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d9d59-248">|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="d9d59-249">|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="d9d59-250">|$Y \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="d9d59-251">|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="d9d59-252">|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="d9d59-253">|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="d9d59-254">|$Z \otimes S $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="d9d59-255">|$X \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="d9d59-256">|$Y \otimes S $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="d9d59-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="d9d59-257">En este caso, la [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operación aparece por el siguiente motivo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-257">Here, the [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operation appears for the following reason.</span></span>
<span data-ttu-id="d9d59-258">Cada medida de Pauli que no incluya la $ \boldone $ matriz es equivalente a una unitario a $ z \otimes z $ por la razón anterior.</span><span class="sxs-lookup"><span data-stu-id="d9d59-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="d9d59-259">El vectores propios de $ z \otimes z $ solo depende de la paridad de la qubits que conforman cada vector de base de cálculo y las operaciones controladas no sirven para calcular esta paridad y almacenarla en el primer bit.</span><span class="sxs-lookup"><span data-stu-id="d9d59-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="d9d59-260">Después, una vez que se mide el primer bit, podemos recuperar la identidad del espacio medio resultante, que es equivalente a medir el operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="d9d59-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="d9d59-261">Una nota adicional: aunque puede ser tentador asumir que la medida z $ \otimes z $ es la misma que la medición secuencial de $ z \otimes \mathbb { 1 } $ y, a continuación, $ \mathbb { 1 } \otimes z $ , esta suposición sería falsa.</span><span class="sxs-lookup"><span data-stu-id="d9d59-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="d9d59-262">La razón es que medir $ z \otimes z $ proyecta el estado de cuanto en el $ eigenstate + 1 $ o $ -1 $ de estos operadores.</span><span class="sxs-lookup"><span data-stu-id="d9d59-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="d9d59-263">$La medida \otimes \mathbb { de z 1 } $ y, a continuación, $ \mathbb { 1 } \otimes Z $ proyecta el vector de estado de Quantum primero en un espacio medio de $ Z \otimes \mathbb { 1 } $ y, a continuación, en un espacio medio de $ \mathbb { 1 } \otimes Z $ . Como hay cuatro vectores de base de cálculo, al realizar ambas mediciones se reduce el estado a un cuarto de espacio y, por tanto, se reduce a un vector de base de cálculo único.</span><span class="sxs-lookup"><span data-stu-id="d9d59-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="d9d59-264">Correlaciones entre bits cuánticos</span><span class="sxs-lookup"><span data-stu-id="d9d59-264">Correlations between qubits</span></span>
<span data-ttu-id="d9d59-265">Otra forma de ver los productos de tensores de matrices de Pauli como $ x \otimes x $ o $ z \otimes z $ es que estas medidas permiten examinar la información almacenada en las correlaciones entre las dos qubits.</span><span class="sxs-lookup"><span data-stu-id="d9d59-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="d9d59-266">$La medición \otimes \id $ de X permite examinar la información que se almacena localmente en el primer qubit.</span><span class="sxs-lookup"><span data-stu-id="d9d59-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="d9d59-267">Aunque ambos tipos de medidas son igualmente valiosos en la informática Quantum, el primero ilumina la potencia de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="d9d59-268">Revela que, con frecuencia, la información que desea aprender no se almacena en ningún qubit único, sino que se almacena de forma no local en todas las qubits a la vez y, por lo tanto, solo al examinarla a través de una medida conjunta (por ejemplo, $ z \otimes z $ ) hace que esta información se convierta en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d9d59-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="d9d59-269">Por ejemplo, en la corrección de errores, a menudo queremos obtener información sobre el error que se produjo al no aprender nada sobre el estado que estamos intentando proteger.</span><span class="sxs-lookup"><span data-stu-id="d9d59-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="d9d59-270">El [ejemplo de código bit-Flip](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) muestra un ejemplo de cómo puede hacerlo con medidas como $ z \otimes z \otimes \id $ y $ \id \otimes z \otimes z $ . < --TODO: cámbielo a un vínculo al explorador de ejemplos en cuanto se incorpora el ejemplo de código bit-flip.</span><span class="sxs-lookup"><span data-stu-id="d9d59-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="d9d59-271">$ \otimes \otimes \otimes \boldone $ También se pueden medir los operadores de Pauli arbitrarios como X Y Z.</span><span class="sxs-lookup"><span data-stu-id="d9d59-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="d9d59-272">Todos estos productos tensores de los operadores Pauli tienen solo dos vectores propios $ \pm 1 $ y ambos eigenspaces constituyen caracteres de medio ancho del espacio vectorial completo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="d9d59-273">Por lo tanto, coinciden con los requisitos indicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d9d59-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="d9d59-274">En Q# , tales mediciones devuelven $ j $ si la medida produce un resultado en el eigenspace de signo $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="d9d59-275">Tener medidas de Pauli como característica integrada en Q# es útil porque la medición de estos operadores requiere largas cadenas de puertas y transformaciones controladas no para describir la puerta U de la estructura de la diagonal $ $ necesaria para expresar la operación como un producto tensores de $ Z $ y $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="d9d59-276">Al poder especificar que desea realizar una de estas medidas predefinidas, no es necesario preocuparse por cómo transformar la base de forma que una medición de base de cálculo proporcione la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="d9d59-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="d9d59-277">Q# controla todas las transformaciones de base necesarias automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d9d59-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="d9d59-278">Para obtener más información, vea [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) las [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operaciones y.</span><span class="sxs-lookup"><span data-stu-id="d9d59-278">For more information, see the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) and [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="d9d59-279">No-Cloning Teorema</span><span class="sxs-lookup"><span data-stu-id="d9d59-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="d9d59-280">La información de Quantum es eficaz.</span><span class="sxs-lookup"><span data-stu-id="d9d59-280">Quantum information is powerful.</span></span>
<span data-ttu-id="d9d59-281">Nos permite hacer cosas sorprendentes, como números de factor exponencialmente más rápidos que los mejores algoritmos clásicos conocidos, o simular eficazmente sistemas de electrones correlacionados que requieran el costo exponencial para simular con precisión.</span><span class="sxs-lookup"><span data-stu-id="d9d59-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="d9d59-282">Sin embargo, existen limitaciones en cuanto a la eficacia de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="d9d59-283">Una de estas limitaciones viene determinada por el *teorema sin clonación*.</span><span class="sxs-lookup"><span data-stu-id="d9d59-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="d9d59-284">El No-Cloning teorema tiene un nombre apropiado.</span><span class="sxs-lookup"><span data-stu-id="d9d59-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="d9d59-285">No permite la clonación de Estados de Quantum genéricos por un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="d9d59-286">La prueba de Teorema es bastante sencilla.</span><span class="sxs-lookup"><span data-stu-id="d9d59-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="d9d59-287">Aunque una prueba completa del teorema sin clonación es un poco técnico para nuestro debate aquí, la prueba en caso de que no haya ningún qubits auxiliar adicional en nuestro ámbito.</span><span class="sxs-lookup"><span data-stu-id="d9d59-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope.</span></span>

<span data-ttu-id="d9d59-288">Para este tipo de equipo Quantum, la operación de clonación debe describirse mediante una matriz de unitario.</span><span class="sxs-lookup"><span data-stu-id="d9d59-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="d9d59-289">No permitimos la medición, ya que dañaría el estado de Quantum que estamos intentando clonar.</span><span class="sxs-lookup"><span data-stu-id="d9d59-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="d9d59-290">Para simular la operación de clonación, queremos que la matriz de unitarios se use para tener la propiedad que $$</span><span class="sxs-lookup"><span data-stu-id="d9d59-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="d9d59-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="d9d59-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="d9d59-292">para cualquier estado $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="d9d59-293">La propiedad linearity de la multiplicación de matrices implica que, para cualquier segundo estado de Quantum $ \ket { \phi } $ ,</span><span class="sxs-lookup"><span data-stu-id="d9d59-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="d9d59-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="d9d59-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="d9d59-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="d9d59-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="d9d59-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="d9d59-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="d9d59-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="d9d59-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="d9d59-298">\right) \\\\</span></span>
    <span data-ttu-id="d9d59-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="d9d59-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="d9d59-300">Esto proporciona el Intuition fundamental detrás del No-Cloning teorema: cualquier dispositivo que copie un estado de Quantum desconocido debe inducir errores en al menos algunos de los Estados que copia.</span><span class="sxs-lookup"><span data-stu-id="d9d59-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="d9d59-301">Aunque la principal suposición de que el Cloner actúa de forma lineal en el estado de la entrada se puede infringir a través de la adición y medición de qubits auxiliares, estas interacciones también pierden información sobre el sistema a través de las estadísticas de medida y evitan la clonación exacta en estos casos.</span><span class="sxs-lookup"><span data-stu-id="d9d59-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="d9d59-302">Para obtener una prueba más completa de los No-Cloning teorema vea [para obtener más información](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="d9d59-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="d9d59-303">El No-Cloning Teorema es importante para el conocimiento cualitativo de la informática Quantum, ya que si pudiera clonar los Estados de Quantum de forma económica, se le concederá una capacidad casi mágica para aprender de los Estados de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="d9d59-304">En realidad, puede infringir el principio de incertidumbre de vaunted de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="d9d59-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="d9d59-305">Como alternativa, puede usar una Cloner óptima para tomar una muestra única de una distribución de Quantum compleja y obtener información sobre todo lo que podría obtener más información sobre esa distribución desde un solo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d9d59-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="d9d59-306">Esto sería similar a la forma de voltear una moneda y observar los cabezales y, a continuación, al decir a un amigo sobre el resultado de responder "Ah la distribución de esa moneda debe ser Bernoulli con $ p = 0.512643 \ ldots $ !".</span><span class="sxs-lookup"><span data-stu-id="d9d59-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="d9d59-307">Este tipo de instrucción sería no SENS, porque un bit de información (el resultado de los cabezales) simplemente no puede proporcionar los numerosos bits de información necesaria para codificar la distribución sin información importante de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="d9d59-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="d9d59-308">Del mismo modo, sin información previa, no se puede clonar absolutamente un estado de Quantum, al igual que no se puede preparar un conjunto de esas monedas sin conocer $ p $ .</span><span class="sxs-lookup"><span data-stu-id="d9d59-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="d9d59-309">La información no es gratuita en la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="d9d59-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="d9d59-310">Cada qubit medida proporciona un único bit de información y el No-Cloning teorema muestra que no hay ninguna puerta trasera que pueda aprovecharse para evitar el equilibrio fundamental entre la información obtenida sobre el sistema y la perturbación invocada.</span><span class="sxs-lookup"><span data-stu-id="d9d59-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
