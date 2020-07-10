---
<span data-ttu-id="7c75a-101">title: vectores y matrices en Quantum Computing Description: Conozca los conceptos básicos sobre cómo trabajar con vectores y matrices.</span><span class="sxs-lookup"><span data-stu-id="7c75a-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="7c75a-102">Autor: QuantumWriter UID: Microsoft. Quantum. Concepts. vectores ms. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 ms. topic: article no-LOC:</span><span class="sxs-lookup"><span data-stu-id="7c75a-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="7c75a-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-103">"$$"</span></span>
- <span data-ttu-id="7c75a-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-104">"$$"</span></span>
- <span data-ttu-id="7c75a-105">"$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-105">"$"</span></span>
- <span data-ttu-id="7c75a-106">"$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-106">"$"</span></span>
- <span data-ttu-id="7c75a-107">"$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-107">"$"</span></span>
- <span data-ttu-id="7c75a-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="7c75a-108">"$$"</span></span>
- <span data-ttu-id="7c75a-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="7c75a-109">"\cdots"</span></span>
- <span data-ttu-id="7c75a-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="7c75a-110">"bmatrix"</span></span>
- <span data-ttu-id="7c75a-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="7c75a-111">"\ddots"</span></span>
- <span data-ttu-id="7c75a-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="7c75a-112">"\equiv"</span></span>
- <span data-ttu-id="7c75a-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="7c75a-113">"\sum"</span></span>
- <span data-ttu-id="7c75a-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="7c75a-114">"\begin"</span></span>
- <span data-ttu-id="7c75a-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="7c75a-115">"\end"</span></span>
- <span data-ttu-id="7c75a-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="7c75a-116">"\sqrt"</span></span>
- <span data-ttu-id="7c75a-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="7c75a-117">"\otimes"</span></span>
- <span data-ttu-id="7c75a-118">"{"</span><span class="sxs-lookup"><span data-stu-id="7c75a-118">"{"</span></span>
- <span data-ttu-id="7c75a-119">"}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-119">"}"</span></span>
- <span data-ttu-id="7c75a-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="7c75a-120">"\text"</span></span>
- <span data-ttu-id="7c75a-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="7c75a-121">"\phi"</span></span>
- <span data-ttu-id="7c75a-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="7c75a-122">"\kappa"</span></span>
- <span data-ttu-id="7c75a-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="7c75a-123">"\psi"</span></span>
- <span data-ttu-id="7c75a-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="7c75a-124">"\alpha"</span></span>
- <span data-ttu-id="7c75a-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="7c75a-125">"\beta"</span></span>
- <span data-ttu-id="7c75a-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="7c75a-126">"\gamma"</span></span>
- <span data-ttu-id="7c75a-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="7c75a-127">"\delta"</span></span>
- <span data-ttu-id="7c75a-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="7c75a-128">"\omega"</span></span>
- <span data-ttu-id="7c75a-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="7c75a-129">"\bra"</span></span>
- <span data-ttu-id="7c75a-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="7c75a-130">"\ket"</span></span>
- <span data-ttu-id="7c75a-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="7c75a-131">"\boldone"</span></span>
- <span data-ttu-id="7c75a-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="7c75a-132">"\\\\"</span></span>
- <span data-ttu-id="7c75a-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="7c75a-133">"\\"</span></span>
- <span data-ttu-id="7c75a-134">"="</span><span class="sxs-lookup"><span data-stu-id="7c75a-134">"="</span></span>
- <span data-ttu-id="7c75a-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="7c75a-135">"\frac"</span></span>
- <span data-ttu-id="7c75a-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="7c75a-136">"\text"</span></span>
- <span data-ttu-id="7c75a-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="7c75a-137">"\mapsto"</span></span>
- <span data-ttu-id="7c75a-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="7c75a-138">"\dagger"</span></span>
- <span data-ttu-id="7c75a-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="7c75a-139">"\to"</span></span>
- <span data-ttu-id="7c75a-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-140">"\begin{cases}"</span></span>
- <span data-ttu-id="7c75a-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-141">"\end{cases}"</span></span>
- <span data-ttu-id="7c75a-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="7c75a-142">"\operatorname"</span></span>
- <span data-ttu-id="7c75a-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="7c75a-143">"\braket"</span></span>
- <span data-ttu-id="7c75a-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="7c75a-144">"\id"</span></span>
- <span data-ttu-id="7c75a-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="7c75a-145">"\expect"</span></span>
- <span data-ttu-id="7c75a-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="7c75a-146">"\defeq"</span></span>
- <span data-ttu-id="7c75a-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="7c75a-147">"\variance"</span></span>
- <span data-ttu-id="7c75a-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="7c75a-148">"\dd"</span></span>
- <span data-ttu-id="7c75a-149">"&"</span><span class="sxs-lookup"><span data-stu-id="7c75a-149">"&"</span></span>
- <span data-ttu-id="7c75a-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-150">"\begin{align}"</span></span>
- <span data-ttu-id="7c75a-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-151">"\end{align}"</span></span>
- <span data-ttu-id="7c75a-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="7c75a-152">"\Lambda"</span></span>
- <span data-ttu-id="7c75a-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="7c75a-153">"\lambda"</span></span>
- <span data-ttu-id="7c75a-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="7c75a-154">"\Omega"</span></span>
- <span data-ttu-id="7c75a-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="7c75a-155">"\mathrm"</span></span>
- <span data-ttu-id="7c75a-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="7c75a-156">"\left"</span></span>
- <span data-ttu-id="7c75a-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="7c75a-157">"\right"</span></span>
- <span data-ttu-id="7c75a-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="7c75a-158">"\qquad"</span></span>
- <span data-ttu-id="7c75a-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="7c75a-159">"\times"</span></span>
- <span data-ttu-id="7c75a-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="7c75a-160">"\big"</span></span>
- <span data-ttu-id="7c75a-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="7c75a-161">"\langle"</span></span>
- <span data-ttu-id="7c75a-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="7c75a-162">"\rangle"</span></span>
- <span data-ttu-id="7c75a-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="7c75a-163">"\bigg"</span></span>
- <span data-ttu-id="7c75a-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="7c75a-164">"\Big"</span></span>
- <span data-ttu-id="7c75a-165">"|"</span><span class="sxs-lookup"><span data-stu-id="7c75a-165">"|"</span></span>
- <span data-ttu-id="7c75a-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="7c75a-166">"\mathbb"</span></span>
- <span data-ttu-id="7c75a-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="7c75a-167">"\vec"</span></span>
- <span data-ttu-id="7c75a-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="7c75a-168">"\in"</span></span>
- <span data-ttu-id="7c75a-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="7c75a-169">"\texttt"</span></span>
- <span data-ttu-id="7c75a-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="7c75a-170">"\ne"</span></span>
- <span data-ttu-id="7c75a-171">"<"</span><span class="sxs-lookup"><span data-stu-id="7c75a-171">"<"</span></span>
- <span data-ttu-id="7c75a-172">">"</span><span class="sxs-lookup"><span data-stu-id="7c75a-172">">"</span></span>
- <span data-ttu-id="7c75a-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="7c75a-173">"\leq"</span></span>
- <span data-ttu-id="7c75a-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="7c75a-174">"\geq"</span></span>
- <span data-ttu-id="7c75a-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="7c75a-175">"~~"</span></span>
- <span data-ttu-id="7c75a-176">"~"</span><span class="sxs-lookup"><span data-stu-id="7c75a-176">"~"</span></span>
- <span data-ttu-id="7c75a-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="7c75a-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="7c75a-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="7c75a-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="7c75a-179">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="7c75a-180">Vectores y matrices</span><span class="sxs-lookup"><span data-stu-id="7c75a-180">Vectors and Matrices</span></span>

<span data-ttu-id="7c75a-181">Algunos conocimientos sobre vectores y matrices son esenciales para comprender la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="7c75a-181">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="7c75a-182">Se proporciona una breve introducción y se recomienda a los lectores interesados leer una referencia estándar sobre álgebra lineal, como *Strang, G (1993). Introducción a álgebra lineal (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o una referencia en línea como [álgebra lineal](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="7c75a-182">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="7c75a-183">Un vector de columna (o simplemente [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ de dimensión (o tamaño) $ n $ es una colección de $ n $ números complejos $ (V_1, v_2, \ldots, v_n) $ organizados como una columna:</span><span class="sxs-lookup"><span data-stu-id="7c75a-183">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

$$<span data-ttu-id="7c75a-184">v=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-184">v =\begin{bmatrix}</span></span>
<span data-ttu-id="7c75a-185">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-185">v_1\\\\</span></span>
<span data-ttu-id="7c75a-186">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-186">v_2\\\\</span></span>
<span data-ttu-id="7c75a-187">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-187">\vdots\\\\</span></span>
<span data-ttu-id="7c75a-188">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="7c75a-188">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="7c75a-189">La norma de un vector $ v $ se define como $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-189">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="7c75a-190">Se dice que un vector es de norma unitaria (o, como alternativa, se denomina [*Vector de unidad*](https://en.wikipedia.org/wiki/Unit_vector)) si su norma es $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-190">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="7c75a-191">El [*contiguo de un vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ se indica $ como v ^ \dagger $ y se define como el siguiente vector de fila donde $ \* $ denota el conjugado complejo.</span><span class="sxs-lookup"><span data-stu-id="7c75a-191">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

$$<span data-ttu-id="7c75a-192">\begin{bmatrix}V_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="7c75a-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="7c75a-193">La manera más común de multiplicar dos vectores juntos es a través del [*producto interno*](https://en.wikipedia.org/wiki/Inner_product_space), también conocido como producto punto.</span><span class="sxs-lookup"><span data-stu-id="7c75a-193">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="7c75a-194">El producto interno proporciona la proyección de un vector en otro y es muy útil para describir cómo expresar un vector como una suma de otros vectores más sencillos.</span><span class="sxs-lookup"><span data-stu-id="7c75a-194">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="7c75a-195">El producto interno entre $ u $ y $ v $ , indicado $ \left \langle u, v \right \rangle $ se define como</span><span class="sxs-lookup"><span data-stu-id="7c75a-195">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
\langle<span data-ttu-id="7c75a-196">u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="7c75a-196"> u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="7c75a-197">Esta notación también permite escribir la norma de un vector $ v $ como $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-197">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="7c75a-198">Podemos multiplicar un vector con un número $ c $ para formar un nuevo vector cuyas entradas se multiplican por $ c $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-198">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="7c75a-199">También podemos agregar dos vectores $ u $ y $ v $ para formar un nuevo vector cuyas entradas son la suma de las entradas de $ u $ y $ v $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-199">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="7c75a-200">Estas operaciones se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="7c75a-200">These operations are depicted below:</span></span>

$$<span data-ttu-id="7c75a-201">\mathrm{Si } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-201">\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="7c75a-202">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-202">u_1\\\\</span></span>
<span data-ttu-id="7c75a-203">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-203">u_2\\\\</span></span>
<span data-ttu-id="7c75a-204">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-204">\vdots\\\\</span></span>
<span data-ttu-id="7c75a-205">u_n \end{bmatrix} ~ \mathrm { y}~</span><span class="sxs-lookup"><span data-stu-id="7c75a-205">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="7c75a-206">v=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-206">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="7c75a-207">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-207">v_1\\\\</span></span>
    <span data-ttu-id="7c75a-208">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-208">v_2\\\\</span></span>
    <span data-ttu-id="7c75a-209">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-209">\vdots\\\\</span></span>
    <span data-ttu-id="7c75a-210">v_n \end{bmatrix} , ~ \mathrm {}~</span><span class="sxs-lookup"><span data-stu-id="7c75a-210">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="7c75a-211">au + BV=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-211">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="7c75a-212">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-212">au_1+bv_1\\\\</span></span>
<span data-ttu-id="7c75a-213">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-213">au_2+bv_2\\\\</span></span>
<span data-ttu-id="7c75a-214">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-214">\vdots\\\\</span></span>
<span data-ttu-id="7c75a-215">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="7c75a-215">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="7c75a-216">Una [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamaño $ m \times n $ es una colección de $ MN $ Complex Numbers organizada en $ m $ Rows y $ n $ columnas, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7c75a-216">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

$$<span data-ttu-id="7c75a-217">F=</span><span class="sxs-lookup"><span data-stu-id="7c75a-217">M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="7c75a-218">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-218">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="7c75a-219">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2N}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-219">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="7c75a-220">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-220">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
\end{bmatrix}<span data-ttu-id="7c75a-221">.$$</span><span class="sxs-lookup"><span data-stu-id="7c75a-221">.$$</span></span>

<span data-ttu-id="7c75a-222">Tenga en cuenta que un vector de dimensión $ n $ es simplemente una matriz de tamaño $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-222">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="7c75a-223">Al igual que con los vectores, se puede multiplicar una matriz con un número $ c $ para obtener una nueva matriz en la que cada entrada se multiplica por $ c $ y se pueden agregar dos matrices del mismo tamaño para generar una nueva matriz cuyas entradas son la suma de las entradas correspondientes de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="7c75a-223">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="7c75a-224">Productos de multiplicación y tensores de matrices</span><span class="sxs-lookup"><span data-stu-id="7c75a-224">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="7c75a-225">También podemos multiplicar dos matrices $ m $ de Dimension $ m \times n $ y $ n $ de Dimension $ n \times p $ para obtener una nueva matriz $ p $ de Dimension $ m \times p $ como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7c75a-225">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="7c75a-226">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-226">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="7c75a-227">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2N}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-227">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="7c75a-228">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}</span><span class="sxs-lookup"><span data-stu-id="7c75a-228">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="7c75a-229">N_ { 11 } ~~ n_ { 12 } ~~ \cdots ~~ n_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-229">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="7c75a-230">N_ { 21 } ~~ n_ { 22 } ~~ \cdots ~~ n_ { 2P}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-230">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="7c75a-231">N_ { N1 } ~~ n_ { N2 } ~~ \cdots ~~ n_ { NP}</span><span class="sxs-lookup"><span data-stu-id="7c75a-231">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="7c75a-232">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-232">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="7c75a-233">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2P}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-233">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="7c75a-234">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="7c75a-234">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="7c75a-235">donde las entradas de $ P $ se $ P_n a la { inversa } = \sum _j M_ { ij } n_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-235">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="7c75a-236">Por ejemplo, la entrada $ P_ { 11 } $ es el producto interno de la primera fila de $ M $ con la primera columna de $ N $ . Tenga en cuenta que, puesto que un vector es simplemente un caso especial de una matriz, esta definición se extiende a la multiplicación de vectores de matriz.</span><span class="sxs-lookup"><span data-stu-id="7c75a-236">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="7c75a-237">Todas las matrices que consideramos serán matrices cuadradas, donde el número de filas y columnas es igual, o vectores, que corresponde a una $ sola $ columna.</span><span class="sxs-lookup"><span data-stu-id="7c75a-237">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="7c75a-238">Una matriz cuadrada especial es la [*matriz de identidad*](https://en.wikipedia.org/wiki/Identity_matrix), indicada $ \boldone $ , que tiene todos sus elementos diagonales iguales a $ 1 $ y los elementos restantes son iguales a $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="7c75a-238">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="7c75a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="7c75a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
~~<span data-ttu-id="7c75a-241"> \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-241"> \ddots\\\\</span></span>
<span data-ttu-id="7c75a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="7c75a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="7c75a-243">En el caso de una matriz cuadrada $ a $ , se $ indica que la matriz B $ es [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) si $ AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-243">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="7c75a-244">No es necesario que el inverso de una matriz exista, pero cuando existe, es único y se le indica que es $ ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-244">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="7c75a-245">En el caso de cualquier matriz $ m $ , la transposición de m o $ del $ tipo de variable es una matriz $ N $ tal que $ n_ { ij } = m_ { ji } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-245">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="7c75a-246">El colindante de $ M $ se indica normalmente como $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-246">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="7c75a-247">Decimos que una matriz $ u $ es [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) si $ UU ^ \dagger = u ^ \dagger u = \boldone $ o equivalente, $ u ^ { -1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-247">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="7c75a-248">Quizás la propiedad más importante de las matrices de unitarios sea que conserven la norma de un vector.</span><span class="sxs-lookup"><span data-stu-id="7c75a-248">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="7c75a-249">Esto sucede porque</span><span class="sxs-lookup"><span data-stu-id="7c75a-249">This happens because</span></span> 

$$<span data-ttu-id="7c75a-250">\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="7c75a-250">\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="7c75a-251">$ $ Se dice que una matriz M es [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="7c75a-251">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="7c75a-252">Por último, el [*producto tensores*](https://en.wikipedia.org/wiki/Tensor_product) (o producto Kronecker) de dos $ matrices $ de tamaño $ m \times n $ y $ n $ de tamaño $ p \times q $ es una matriz mayor $ = de tamaño p M \otimes n $ de $ MP \times NQ $ , y se obtiene de $ M y n de la $ $ $ manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c75a-252">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="7c75a-253">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="7c75a-253">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="7c75a-254">M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-254">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="7c75a-255">M_ { M1 } ~~ \cdots ~~ m_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="7c75a-255">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="7c75a-256">N_ { 11 } ~~ \cdots ~~ n_ { 1P  }\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-256">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="7c75a-257">N_ { P1 } ~~ \cdots ~~ n_ { pq}</span><span class="sxs-lookup"><span data-stu-id="7c75a-257">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="7c75a-258">M_ { 11 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="7c75a-258">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="7c75a-259">M_ { 1N } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-259">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="7c75a-260">M_ { M1 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="7c75a-260">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="7c75a-261">M_ { MN } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1P } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-261">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    \end{bmatrix}<span data-ttu-id="7c75a-262">.</span><span class="sxs-lookup"><span data-stu-id="7c75a-262">.</span></span>
\end{align}

<span data-ttu-id="7c75a-263">Esto se demuestra mejor con algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="7c75a-263">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="7c75a-264">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="7c75a-264">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="7c75a-265">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-265">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        \\\\<span data-ttu-id="7c75a-266">[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-266">[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    =<span data-ttu-id="7c75a-267">\begin{bmatrix}a \\\\ d a e b a b \\\\ \\\\ c \\\\ d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-267"> \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="7c75a-268">y</span><span class="sxs-lookup"><span data-stu-id="7c75a-268">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="7c75a-269">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-269">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="7c75a-270">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-270">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="7c75a-271">un\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-271">a\begin{bmatrix}</span></span>
    <span data-ttu-id="7c75a-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-272">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="7c75a-273">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-273">b\begin{bmatrix}</span></span>
    <span data-ttu-id="7c75a-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \\\\<span data-ttu-id="7c75a-275">[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-275">[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="7c75a-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="7c75a-277">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-277">d\begin{bmatrix}</span></span>
    <span data-ttu-id="7c75a-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="7c75a-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="7c75a-279">AE \ AF \ \ BF\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-279">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="7c75a-280">AG \ ah \ BG \ BH\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-280">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="7c75a-281">CE \ CF \ de \ DF\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-281">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="7c75a-282">CG \ CH \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="7c75a-282">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="7c75a-283">Una Convención de notación útil final que rodea a los productos de tensores es que, para cualquier vector $ v $ o Matrix $ M $ , $ v ^ { \otimes n } $ o $ m ^ { \otimes n } $ es una mano corta para un $ $ producto tensores repetido de n veces.</span><span class="sxs-lookup"><span data-stu-id="7c75a-283">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="7c75a-284">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c75a-284">For example:</span></span>

\begin{align}
&<span data-ttu-id="7c75a-285">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="7c75a-285">\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  &<span data-ttu-id="7c75a-286">\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="7c75a-286">\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
