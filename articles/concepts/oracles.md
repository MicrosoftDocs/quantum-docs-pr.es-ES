---
<span data-ttu-id="6c27b-101">title: Quantum Oracle Description: Obtenga información sobre cómo trabajar con y definir las operaciones de Black Box que se usan como entrada en otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6c27b-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="6c27b-102">Autor: cgranade UID: Microsoft. Quantum. Concepts. Oracle ms. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 ms. topic: article no-LOC:</span><span class="sxs-lookup"><span data-stu-id="6c27b-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="6c27b-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="6c27b-103">"Q#"</span></span>
- <span data-ttu-id="6c27b-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="6c27b-104">"$$v"</span></span>
- <span data-ttu-id="6c27b-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-105">"$$"</span></span>
- <span data-ttu-id="6c27b-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-106">"$$"</span></span>
- <span data-ttu-id="6c27b-107">"$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-107">"$"</span></span>
- <span data-ttu-id="6c27b-108">"$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-108">"$"</span></span>
- <span data-ttu-id="6c27b-109">"$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-109">"$"</span></span>
- <span data-ttu-id="6c27b-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="6c27b-110">"$$"</span></span>
- <span data-ttu-id="6c27b-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="6c27b-111">"\cdots"</span></span>
- <span data-ttu-id="6c27b-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="6c27b-112">"bmatrix"</span></span>
- <span data-ttu-id="6c27b-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="6c27b-113">"\ddots"</span></span>
- <span data-ttu-id="6c27b-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="6c27b-114">"\equiv"</span></span>
- <span data-ttu-id="6c27b-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="6c27b-115">"\sum"</span></span>
- <span data-ttu-id="6c27b-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="6c27b-116">"\begin"</span></span>
- <span data-ttu-id="6c27b-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="6c27b-117">"\end"</span></span>
- <span data-ttu-id="6c27b-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="6c27b-118">"\sqrt"</span></span>
- <span data-ttu-id="6c27b-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="6c27b-119">"\otimes"</span></span>
- <span data-ttu-id="6c27b-120">"{"</span><span class="sxs-lookup"><span data-stu-id="6c27b-120">"{"</span></span>
- <span data-ttu-id="6c27b-121">"}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-121">"}"</span></span>
- <span data-ttu-id="6c27b-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="6c27b-122">"\text"</span></span>
- <span data-ttu-id="6c27b-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="6c27b-123">"\phi"</span></span>
- <span data-ttu-id="6c27b-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="6c27b-124">"\kappa"</span></span>
- <span data-ttu-id="6c27b-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="6c27b-125">"\psi"</span></span>
- <span data-ttu-id="6c27b-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="6c27b-126">"\alpha"</span></span>
- <span data-ttu-id="6c27b-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="6c27b-127">"\beta"</span></span>
- <span data-ttu-id="6c27b-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="6c27b-128">"\gamma"</span></span>
- <span data-ttu-id="6c27b-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="6c27b-129">"\delta"</span></span>
- <span data-ttu-id="6c27b-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="6c27b-130">"\omega"</span></span>
- <span data-ttu-id="6c27b-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="6c27b-131">"\bra"</span></span>
- <span data-ttu-id="6c27b-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="6c27b-132">"\ket"</span></span>
- <span data-ttu-id="6c27b-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="6c27b-133">"\boldone"</span></span>
- <span data-ttu-id="6c27b-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="6c27b-134">"\\\\"</span></span>
- <span data-ttu-id="6c27b-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="6c27b-135">"\\"</span></span>
- <span data-ttu-id="6c27b-136">"="</span><span class="sxs-lookup"><span data-stu-id="6c27b-136">"="</span></span>
- <span data-ttu-id="6c27b-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="6c27b-137">"\frac"</span></span>
- <span data-ttu-id="6c27b-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="6c27b-138">"\text"</span></span>
- <span data-ttu-id="6c27b-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="6c27b-139">"\mapsto"</span></span>
- <span data-ttu-id="6c27b-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="6c27b-140">"\dagger"</span></span>
- <span data-ttu-id="6c27b-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="6c27b-141">"\to"</span></span>
- <span data-ttu-id="6c27b-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-142">"\begin{cases}"</span></span>
- <span data-ttu-id="6c27b-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-143">"\end{cases}"</span></span>
- <span data-ttu-id="6c27b-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="6c27b-144">"\operatorname"</span></span>
- <span data-ttu-id="6c27b-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="6c27b-145">"\braket"</span></span>
- <span data-ttu-id="6c27b-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="6c27b-146">"\id"</span></span>
- <span data-ttu-id="6c27b-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="6c27b-147">"\expect"</span></span>
- <span data-ttu-id="6c27b-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="6c27b-148">"\defeq"</span></span>
- <span data-ttu-id="6c27b-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="6c27b-149">"\variance"</span></span>
- <span data-ttu-id="6c27b-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="6c27b-150">"\dd"</span></span>
- <span data-ttu-id="6c27b-151">"&"</span><span class="sxs-lookup"><span data-stu-id="6c27b-151">"&"</span></span>
- <span data-ttu-id="6c27b-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-152">"\begin{align}"</span></span>
- <span data-ttu-id="6c27b-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-153">"\end{align}"</span></span>
- <span data-ttu-id="6c27b-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="6c27b-154">"\Lambda"</span></span>
- <span data-ttu-id="6c27b-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="6c27b-155">"\lambda"</span></span>
- <span data-ttu-id="6c27b-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="6c27b-156">"\Omega"</span></span>
- <span data-ttu-id="6c27b-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="6c27b-157">"\mathrm"</span></span>
- <span data-ttu-id="6c27b-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="6c27b-158">"\left"</span></span>
- <span data-ttu-id="6c27b-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="6c27b-159">"\right"</span></span>
- <span data-ttu-id="6c27b-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="6c27b-160">"\qquad"</span></span>
- <span data-ttu-id="6c27b-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="6c27b-161">"\times"</span></span>
- <span data-ttu-id="6c27b-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="6c27b-162">"\big"</span></span>
- <span data-ttu-id="6c27b-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="6c27b-163">"\langle"</span></span>
- <span data-ttu-id="6c27b-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="6c27b-164">"\rangle"</span></span>
- <span data-ttu-id="6c27b-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="6c27b-165">"\bigg"</span></span>
- <span data-ttu-id="6c27b-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="6c27b-166">"\Big"</span></span>
- <span data-ttu-id="6c27b-167">"|"</span><span class="sxs-lookup"><span data-stu-id="6c27b-167">"|"</span></span>
- <span data-ttu-id="6c27b-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="6c27b-168">"\mathbb"</span></span>
- <span data-ttu-id="6c27b-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="6c27b-169">"\vec"</span></span>
- <span data-ttu-id="6c27b-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="6c27b-170">"\in"</span></span>
- <span data-ttu-id="6c27b-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="6c27b-171">"\texttt"</span></span>
- <span data-ttu-id="6c27b-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="6c27b-172">"\ne"</span></span>
- <span data-ttu-id="6c27b-173">"<"</span><span class="sxs-lookup"><span data-stu-id="6c27b-173">"<"</span></span>
- <span data-ttu-id="6c27b-174">">"</span><span class="sxs-lookup"><span data-stu-id="6c27b-174">">"</span></span>
- <span data-ttu-id="6c27b-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="6c27b-175">"\leq"</span></span>
- <span data-ttu-id="6c27b-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="6c27b-176">"\geq"</span></span>
- <span data-ttu-id="6c27b-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="6c27b-177">"~~"</span></span>
- <span data-ttu-id="6c27b-178">"~"</span><span class="sxs-lookup"><span data-stu-id="6c27b-178">"~"</span></span>
- <span data-ttu-id="6c27b-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="6c27b-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6c27b-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="6c27b-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="6c27b-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="6c27b-182">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="6c27b-182">Quantum Oracles</span></span>

<span data-ttu-id="6c27b-183">Una $ O Oracle $ es una operación de "caja negra" que se usa como entrada para otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6c27b-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="6c27b-184">A menudo, estas operaciones se definen mediante una función clásica $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ que toma $ una $ entrada binaria de n bits y genera una $ $ salida binaria de m bits.</span><span class="sxs-lookup"><span data-stu-id="6c27b-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="6c27b-185">Para ello, considere una entrada binaria determinada $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="6c27b-186">Podemos etiquetar los Estados de qubit como $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="6c27b-187">En primer lugar, es posible que se intente definir $ o $ para que $ o \ket { x } = \ket { f (x) } $ , pero esto tiene un par de problemas.</span><span class="sxs-lookup"><span data-stu-id="6c27b-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="6c27b-188">En primer lugar, $ f $ puede tener un tamaño diferente de entrada y salida ( $ n \ne m $ ), de modo que $ la aplicación de O cambiaría $ el número de qubits en el registro.</span><span class="sxs-lookup"><span data-stu-id="6c27b-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="6c27b-189">En segundo lugar, incluso si $ n = m $ , es posible que la función no se pueda invertir: Si $ f (x) = f (y) $ para some $ x \ne y $ , entonces $ o \ket { x } = o \ket { y, } $ $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="6c27b-190">Esto significa que no se puede crear la operación de "contiguo" $ o ^ y que las \dagger $ Oracle tienen que tener un método contiguo definido para ellos.</span><span class="sxs-lookup"><span data-stu-id="6c27b-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="6c27b-191">Definir un Oracle por su efecto en Estados de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="6c27b-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="6c27b-192">Podemos tratar estos dos problemas introduciendo un segundo registro de $ m $ qubits para mantener la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c27b-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="6c27b-193">A continuación, se definirá el efecto de Oracle en todos los Estados de base de cálculo: para todos los $ x \in \\ { 0, 1 \\ } ^ n $ e y $ \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="6c27b-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="6c27b-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="6c27b-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="6c27b-195">Ahora $ o = ^ \dagger $ por construcción, hemos resuelto ambos problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="6c27b-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="6c27b-196">>Para ver que $ o = ^ { \dagger } $ , tenga en cuenta que $ o ^ 2 = \boldone $ desde $ \oplus b \oplus b = a $ para todos $ a, b \in \: :: no-LOC ({)::: 0, 1 \: :: no-LOC (})::: $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="6c27b-197">>Como resultado, $ O \ket { x x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="6c27b-198">Lo importante es que la definición de Oracle de este modo para cada estado de base de cálculo $ \ket { x } \ket { y } $ también define cómo $ $ actúa O para cualquier otro Estado.</span><span class="sxs-lookup"><span data-stu-id="6c27b-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="6c27b-199">Esto se sigue inmediatamente desde el hecho de que $ O $ , al igual que todas las operaciones Quantum, es lineal en el estado en el que actúa.</span><span class="sxs-lookup"><span data-stu-id="6c27b-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="6c27b-200">Considere la operación Hadamard, por ejemplo, definida por $ h \ket { 0 } = \ket { + } $ y $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="6c27b-201">Si deseamos saber cómo $ funciona h $ $ \ket { + } $ , podemos usar que $ h $ es lineal,</span><span class="sxs-lookup"><span data-stu-id="6c27b-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="6c27b-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="6c27b-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="6c27b-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="6c27b-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="6c27b-204">En el caso de definir nuestra $ O Oracle $ , podemos usar de forma similar que cualquier estado $ \ket { \psi } $ en $ n + m $ qubits se puede escribir como</span><span class="sxs-lookup"><span data-stu-id="6c27b-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="6c27b-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="6c27b-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="6c27b-206">donde $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representa los coeficientes del estado $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="6c27b-207">Así,</span><span class="sxs-lookup"><span data-stu-id="6c27b-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="6c27b-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="6c27b-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="6c27b-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="6c27b-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="6c27b-210">Oracle de fase</span><span class="sxs-lookup"><span data-stu-id="6c27b-210">Phase oracles</span></span>
<span data-ttu-id="6c27b-211">Como alternativa, podemos codificar $ f $ en Oracle $ O $ aplicando una _fase_ basada en la entrada a $ O $ . Por ejemplo, podríamos definir $ O $ tal que$$</span><span class="sxs-lookup"><span data-stu-id="6c27b-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="6c27b-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="6c27b-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="6c27b-213">Si una fase de Oracle actúa en un registro inicialmente en el estado x de la base de cálculo $ \ket { } $ , esta fase es una fase global y, por lo tanto, no observable.</span><span class="sxs-lookup"><span data-stu-id="6c27b-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="6c27b-214">Pero este tipo de Oracle puede ser un recurso muy eficaz si se aplica a una superposición o como una operación controlada.</span><span class="sxs-lookup"><span data-stu-id="6c27b-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="6c27b-215">Considere, por ejemplo, una fase $ de oracle O_f $ para una función de qubit única $ f $ .</span><span class="sxs-lookup"><span data-stu-id="6c27b-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="6c27b-216">A$$</span><span class="sxs-lookup"><span data-stu-id="6c27b-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="6c27b-217">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="6c27b-217">O_f \ket{+}</span></span>
        <span data-ttu-id="6c27b-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="6c27b-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="6c27b-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="6c27b-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="6c27b-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="6c27b-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="6c27b-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="6c27b-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="6c27b-222">En general, se pueden ampliar ambas vistas de Oracle para representar funciones clásicas que devuelven números reales en lugar de un solo bit.</span><span class="sxs-lookup"><span data-stu-id="6c27b-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="6c27b-223">Elegir la mejor manera de implementar Oracle depende en gran medida de cómo se utilizará este Oracle dentro de un algoritmo determinado.</span><span class="sxs-lookup"><span data-stu-id="6c27b-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="6c27b-224">Por ejemplo, el [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) se basa en la implementación de Oracle en primer lugar, mientras que el [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) se basa en Oracle implementado de la segunda manera.</span><span class="sxs-lookup"><span data-stu-id="6c27b-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="6c27b-225">Para obtener más detalles, se recomienda la explicación de [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="6c27b-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
