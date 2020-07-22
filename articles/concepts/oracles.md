---
<span data-ttu-id="e38d4-101">title: Quantum Oracle Description: Obtenga información sobre cómo trabajar con y definir las operaciones de Black Box que se usan como entrada en otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e38d4-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="e38d4-102">Autor: cgranade UID: Microsoft. Quantum. Concepts. Oracle ms. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 ms. topic: article no-LOC:</span><span class="sxs-lookup"><span data-stu-id="e38d4-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="e38d4-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-103">"$$"</span></span>
- <span data-ttu-id="e38d4-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-104">"$$"</span></span>
- <span data-ttu-id="e38d4-105">"$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-105">"$"</span></span>
- <span data-ttu-id="e38d4-106">"$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-106">"$"</span></span>
- <span data-ttu-id="e38d4-107">"$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-107">"$"</span></span>
- <span data-ttu-id="e38d4-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="e38d4-108">"$$"</span></span>
- <span data-ttu-id="e38d4-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="e38d4-109">"\cdots"</span></span>
- <span data-ttu-id="e38d4-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="e38d4-110">"bmatrix"</span></span>
- <span data-ttu-id="e38d4-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="e38d4-111">"\ddots"</span></span>
- <span data-ttu-id="e38d4-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="e38d4-112">"\equiv"</span></span>
- <span data-ttu-id="e38d4-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="e38d4-113">"\sum"</span></span>
- <span data-ttu-id="e38d4-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="e38d4-114">"\begin"</span></span>
- <span data-ttu-id="e38d4-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="e38d4-115">"\end"</span></span>
- <span data-ttu-id="e38d4-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="e38d4-116">"\sqrt"</span></span>
- <span data-ttu-id="e38d4-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="e38d4-117">"\otimes"</span></span>
- <span data-ttu-id="e38d4-118">"{"</span><span class="sxs-lookup"><span data-stu-id="e38d4-118">"{"</span></span>
- <span data-ttu-id="e38d4-119">"}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-119">"}"</span></span>
- <span data-ttu-id="e38d4-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="e38d4-120">"\text"</span></span>
- <span data-ttu-id="e38d4-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="e38d4-121">"\phi"</span></span>
- <span data-ttu-id="e38d4-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="e38d4-122">"\kappa"</span></span>
- <span data-ttu-id="e38d4-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="e38d4-123">"\psi"</span></span>
- <span data-ttu-id="e38d4-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="e38d4-124">"\alpha"</span></span>
- <span data-ttu-id="e38d4-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="e38d4-125">"\beta"</span></span>
- <span data-ttu-id="e38d4-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="e38d4-126">"\gamma"</span></span>
- <span data-ttu-id="e38d4-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="e38d4-127">"\delta"</span></span>
- <span data-ttu-id="e38d4-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="e38d4-128">"\omega"</span></span>
- <span data-ttu-id="e38d4-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="e38d4-129">"\bra"</span></span>
- <span data-ttu-id="e38d4-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="e38d4-130">"\ket"</span></span>
- <span data-ttu-id="e38d4-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="e38d4-131">"\boldone"</span></span>
- <span data-ttu-id="e38d4-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="e38d4-132">"\\\\"</span></span>
- <span data-ttu-id="e38d4-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="e38d4-133">"\\"</span></span>
- <span data-ttu-id="e38d4-134">"="</span><span class="sxs-lookup"><span data-stu-id="e38d4-134">"="</span></span>
- <span data-ttu-id="e38d4-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="e38d4-135">"\frac"</span></span>
- <span data-ttu-id="e38d4-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="e38d4-136">"\text"</span></span>
- <span data-ttu-id="e38d4-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="e38d4-137">"\mapsto"</span></span>
- <span data-ttu-id="e38d4-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="e38d4-138">"\dagger"</span></span>
- <span data-ttu-id="e38d4-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="e38d4-139">"\to"</span></span>
- <span data-ttu-id="e38d4-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-140">"\begin{cases}"</span></span>
- <span data-ttu-id="e38d4-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-141">"\end{cases}"</span></span>
- <span data-ttu-id="e38d4-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="e38d4-142">"\operatorname"</span></span>
- <span data-ttu-id="e38d4-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="e38d4-143">"\braket"</span></span>
- <span data-ttu-id="e38d4-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="e38d4-144">"\id"</span></span>
- <span data-ttu-id="e38d4-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="e38d4-145">"\expect"</span></span>
- <span data-ttu-id="e38d4-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="e38d4-146">"\defeq"</span></span>
- <span data-ttu-id="e38d4-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="e38d4-147">"\variance"</span></span>
- <span data-ttu-id="e38d4-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="e38d4-148">"\dd"</span></span>
- <span data-ttu-id="e38d4-149">"&"</span><span class="sxs-lookup"><span data-stu-id="e38d4-149">"&"</span></span>
- <span data-ttu-id="e38d4-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-150">"\begin{align}"</span></span>
- <span data-ttu-id="e38d4-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-151">"\end{align}"</span></span>
- <span data-ttu-id="e38d4-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="e38d4-152">"\Lambda"</span></span>
- <span data-ttu-id="e38d4-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="e38d4-153">"\lambda"</span></span>
- <span data-ttu-id="e38d4-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="e38d4-154">"\Omega"</span></span>
- <span data-ttu-id="e38d4-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="e38d4-155">"\mathrm"</span></span>
- <span data-ttu-id="e38d4-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="e38d4-156">"\left"</span></span>
- <span data-ttu-id="e38d4-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="e38d4-157">"\right"</span></span>
- <span data-ttu-id="e38d4-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="e38d4-158">"\qquad"</span></span>
- <span data-ttu-id="e38d4-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="e38d4-159">"\times"</span></span>
- <span data-ttu-id="e38d4-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="e38d4-160">"\big"</span></span>
- <span data-ttu-id="e38d4-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="e38d4-161">"\langle"</span></span>
- <span data-ttu-id="e38d4-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="e38d4-162">"\rangle"</span></span>
- <span data-ttu-id="e38d4-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="e38d4-163">"\bigg"</span></span>
- <span data-ttu-id="e38d4-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="e38d4-164">"\Big"</span></span>
- <span data-ttu-id="e38d4-165">"|"</span><span class="sxs-lookup"><span data-stu-id="e38d4-165">"|"</span></span>
- <span data-ttu-id="e38d4-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="e38d4-166">"\mathbb"</span></span>
- <span data-ttu-id="e38d4-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="e38d4-167">"\vec"</span></span>
- <span data-ttu-id="e38d4-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="e38d4-168">"\in"</span></span>
- <span data-ttu-id="e38d4-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="e38d4-169">"\texttt"</span></span>
- <span data-ttu-id="e38d4-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="e38d4-170">"\ne"</span></span>
- <span data-ttu-id="e38d4-171">"<"</span><span class="sxs-lookup"><span data-stu-id="e38d4-171">"<"</span></span>
- <span data-ttu-id="e38d4-172">">"</span><span class="sxs-lookup"><span data-stu-id="e38d4-172">">"</span></span>
- <span data-ttu-id="e38d4-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="e38d4-173">"\leq"</span></span>
- <span data-ttu-id="e38d4-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="e38d4-174">"\geq"</span></span>
- <span data-ttu-id="e38d4-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="e38d4-175">"~~"</span></span>
- <span data-ttu-id="e38d4-176">"~"</span><span class="sxs-lookup"><span data-stu-id="e38d4-176">"~"</span></span>
- <span data-ttu-id="e38d4-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="e38d4-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e38d4-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="e38d4-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="e38d4-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="e38d4-180">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="e38d4-180">Quantum Oracles</span></span>

<span data-ttu-id="e38d4-181">Una $ O Oracle $ es una operación de "caja negra" que se usa como entrada para otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e38d4-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="e38d4-182">A menudo, estas operaciones se definen mediante una función clásica $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ que toma $ una $ entrada binaria de n bits y genera una $ $ salida binaria de m bits.</span><span class="sxs-lookup"><span data-stu-id="e38d4-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="e38d4-183">Para ello, considere una entrada binaria determinada $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="e38d4-184">Podemos etiquetar los Estados de qubit como $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="e38d4-185">En primer lugar, es posible que se intente definir $ o $ para que $ o \ket { x } = \ket { f (x) } $ , pero esto tiene un par de problemas.</span><span class="sxs-lookup"><span data-stu-id="e38d4-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="e38d4-186">En primer lugar, $ f $ puede tener un tamaño diferente de entrada y salida ( $ n \ne m $ ), de modo que $ la aplicación de O cambiaría $ el número de qubits en el registro.</span><span class="sxs-lookup"><span data-stu-id="e38d4-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="e38d4-187">En segundo lugar, incluso si $ n = m $ , es posible que la función no se pueda invertir: Si $ f (x) = f (y) $ para some $ x \ne y $ , entonces $ o \ket { x } = o \ket { y, } $ $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="e38d4-188">Esto significa que no se puede crear la operación de "contiguo" $ o ^ y que las \dagger $ Oracle tienen que tener un método contiguo definido para ellos.</span><span class="sxs-lookup"><span data-stu-id="e38d4-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="e38d4-189">Definir un Oracle por su efecto en Estados de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="e38d4-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="e38d4-190">Podemos tratar estos dos problemas introduciendo un segundo registro de $ m $ qubits para mantener la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e38d4-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="e38d4-191">A continuación, se definirá el efecto de Oracle en todos los Estados de base de cálculo: para todos los $ x \in \\ { 0, 1 \\ } ^ n $ e y $ \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="e38d4-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="e38d4-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="e38d4-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="e38d4-193">Ahora $ o = ^ \dagger $ por construcción, hemos resuelto ambos problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="e38d4-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="e38d4-194">Para ver que $ o = ^ { \dagger } $ , tenga en cuenta que $ o ^ 2 = \boldone $ desde $ una \oplus b \oplus b = a $ para todo $ a, b \in \[ ! Operador. NO-LOC ({)] 0, 1 \[ ! Operador. NO-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="e38d4-195">Como resultado, $ O \ket { x x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="e38d4-196">Lo importante es que la definición de Oracle de este modo para cada estado de base de cálculo $ \ket { x } \ket { y } $ también define cómo $ $ actúa O para cualquier otro Estado.</span><span class="sxs-lookup"><span data-stu-id="e38d4-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="e38d4-197">Esto se sigue inmediatamente desde el hecho de que $ O $ , al igual que todas las operaciones Quantum, es lineal en el estado en el que actúa.</span><span class="sxs-lookup"><span data-stu-id="e38d4-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="e38d4-198">Considere la operación Hadamard, por ejemplo, definida por $ h \ket { 0 } = \ket { + } $ y $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="e38d4-199">Si deseamos saber cómo $ funciona h $ $ \ket { + } $ , podemos usar que $ h $ es lineal,</span><span class="sxs-lookup"><span data-stu-id="e38d4-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="e38d4-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="e38d4-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="e38d4-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="e38d4-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="e38d4-202">En el caso de definir nuestra $ O Oracle $ , podemos usar de forma similar que cualquier estado $ \ket { \psi } $ en $ n + m $ qubits se puede escribir como</span><span class="sxs-lookup"><span data-stu-id="e38d4-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="e38d4-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="e38d4-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="e38d4-204">donde $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representa los coeficientes del estado $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="e38d4-205">Así,</span><span class="sxs-lookup"><span data-stu-id="e38d4-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="e38d4-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="e38d4-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="e38d4-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="e38d4-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="e38d4-208">Oracle de fase</span><span class="sxs-lookup"><span data-stu-id="e38d4-208">Phase oracles</span></span>
<span data-ttu-id="e38d4-209">Como alternativa, podemos codificar $ f $ en Oracle $ O $ aplicando una _fase_ basada en la entrada a $ O $ . Por ejemplo, podríamos definir $ O $ tal que$$</span><span class="sxs-lookup"><span data-stu-id="e38d4-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="e38d4-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="e38d4-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="e38d4-211">Si una fase de Oracle actúa en un registro inicialmente en el estado x de la base de cálculo $ \ket { } $ , esta fase es una fase global y, por lo tanto, no observable.</span><span class="sxs-lookup"><span data-stu-id="e38d4-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="e38d4-212">Pero este tipo de Oracle puede ser un recurso muy eficaz si se aplica a una superposición o como una operación controlada.</span><span class="sxs-lookup"><span data-stu-id="e38d4-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="e38d4-213">Considere, por ejemplo, una fase $ de oracle O_f $ para una función de qubit única $ f $ .</span><span class="sxs-lookup"><span data-stu-id="e38d4-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="e38d4-214">A$$</span><span class="sxs-lookup"><span data-stu-id="e38d4-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="e38d4-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="e38d4-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="e38d4-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="e38d4-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="e38d4-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="e38d4-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="e38d4-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="e38d4-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="e38d4-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="e38d4-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="e38d4-220">En general, se pueden ampliar ambas vistas de Oracle para representar funciones clásicas que devuelven números reales en lugar de un solo bit.</span><span class="sxs-lookup"><span data-stu-id="e38d4-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="e38d4-221">Elegir la mejor manera de implementar Oracle depende en gran medida de cómo se utilizará este Oracle dentro de un algoritmo determinado.</span><span class="sxs-lookup"><span data-stu-id="e38d4-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="e38d4-222">Por ejemplo, el [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) se basa en la implementación de Oracle en primer lugar, mientras que el [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) se basa en Oracle implementado de la segunda manera.</span><span class="sxs-lookup"><span data-stu-id="e38d4-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="e38d4-223">Para obtener más detalles, se recomienda la explicación de [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="e38d4-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
