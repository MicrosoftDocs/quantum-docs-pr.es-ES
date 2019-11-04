---
title: Oracle Quantum | Microsoft Docs
description: Oracle Quantum
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184719"
---
# <a name="quantum-oracles"></a><span data-ttu-id="c625e-103">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="c625e-103">Quantum Oracles</span></span>

<span data-ttu-id="c625e-104">Oracle $O $ es una operación de "caja negra" que se usa como entrada para otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="c625e-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="c625e-105">A menudo, estas operaciones se definen mediante una función clásica $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, que toma una $n entrada binaria de $ bits y genera una $m Salida binaria de $ bits.</span><span class="sxs-lookup"><span data-stu-id="c625e-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="c625e-106">Para ello, considere una entrada binaria determinada $x = (x_{0}, x_{1}, \dots, x_ {n-1}) $.</span><span class="sxs-lookup"><span data-stu-id="c625e-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="c625e-107">Podemos etiquetar los Estados de qubit como $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}} $.</span><span class="sxs-lookup"><span data-stu-id="c625e-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="c625e-108">Es posible que primero intentemos definir $O $ para que $O \ket{x} = \ket{f (x)} $, pero esto tiene un par de problemas.</span><span class="sxs-lookup"><span data-stu-id="c625e-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="c625e-109">En primer lugar, $f $ puede tener un tamaño diferente de entrada y salida ($n \ne m $), de modo que la aplicación de $O $ cambiaría el número de qubits en el registro.</span><span class="sxs-lookup"><span data-stu-id="c625e-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="c625e-110">En segundo lugar, aunque $n = m $, la función no se puede invertir: si $f (x) = f (y) $ para algunos $x \ne y $, entonces $O \ket{x} = O\ket {y} $ pero $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.</span><span class="sxs-lookup"><span data-stu-id="c625e-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="c625e-111">Esto significa que no se puede crear la operación de "contiguo" $O ^ \dagger $ y que las Oracle tienen que tener un método contiguo definido para ellos.</span><span class="sxs-lookup"><span data-stu-id="c625e-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="c625e-112">Definir un Oracle por su efecto en Estados de base de cálculo</span><span class="sxs-lookup"><span data-stu-id="c625e-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="c625e-113">Podemos tratar estos dos problemas introduciendo un segundo registro de $m $ qubits para mantener la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c625e-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="c625e-114">A continuación, se definirá el efecto de Oracle en todos los Estados de base de cálculo: para todos los $x \en \\{0, 1\\} ^ n $ y $y \en \\{0, 1\\} ^ m $,</span><span class="sxs-lookup"><span data-stu-id="c625e-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="c625e-115">$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="c625e-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="c625e-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c625e-116">\end{align} $$</span></span>

<span data-ttu-id="c625e-117">Ahora $O = O ^ \dagger $ por construcción, por lo que hemos resuelto ambos problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="c625e-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="c625e-118">Para ver que $O = O ^ {\dagger} $, tenga en cuenta que $O ^ 2 = \boldone $ desde $a \oplus b \oplus b = a $ para todos los $a, b \en \{0, 1\}$.</span><span class="sxs-lookup"><span data-stu-id="c625e-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="c625e-119">Como resultado, $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.</span><span class="sxs-lookup"><span data-stu-id="c625e-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="c625e-120">Lo importante es que la definición de Oracle de este modo para cada estado de base de cálculo $ \ket{x}\ket{y} $ también define cómo $O $ actúa para cualquier otro Estado.</span><span class="sxs-lookup"><span data-stu-id="c625e-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="c625e-121">Esto se sigue inmediatamente desde el hecho de que $O $, al igual que todas las operaciones Quantum, es lineal en el estado en el que actúa.</span><span class="sxs-lookup"><span data-stu-id="c625e-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="c625e-122">Considere la operación Hadamard, por ejemplo, definida por $H \ket{0} = \ket{+} $ y $H \ket{1} = \ket{-}$.</span><span class="sxs-lookup"><span data-stu-id="c625e-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="c625e-123">Si deseamos saber cómo $H $ actúa en $ \ket{+} $, podemos usar ese $H $ es lineal.</span><span class="sxs-lookup"><span data-stu-id="c625e-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="c625e-124">$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ les {+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="c625e-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="c625e-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c625e-125">\end{align} $$</span></span>

<span data-ttu-id="c625e-126">En el caso de definir nuestra $O de Oracle $, podemos usar de forma similar que cualquier estado $ \ket{\psi} $ en $n + m $ qubits se puede escribir como</span><span class="sxs-lookup"><span data-stu-id="c625e-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="c625e-127">$ $ \begin{align} \ket{\psi} & = \sum_{x \en \\{0, 1\\} ^ n, y \en \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c625e-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="c625e-128">donde $ \alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ representa los coeficientes del estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="c625e-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="c625e-129">Modo</span><span class="sxs-lookup"><span data-stu-id="c625e-129">Thus,</span></span>

<span data-ttu-id="c625e-130">$ $ \begin{align} O \ket{\psi} & = O \sum_{x \en \\{0, 1\\} ^ n, y \en \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \en \\{0 , 1\\} ^ n, y \en \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \en \\{0, 1\\} ^ n, y \en \\{0 , 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="c625e-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="c625e-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c625e-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="c625e-132">Oracle de fase</span><span class="sxs-lookup"><span data-stu-id="c625e-132">Phase oracles</span></span>
<span data-ttu-id="c625e-133">Como alternativa, podemos codificar $f $ en un Oracle $O $ aplicando una _fase_ basada en la entrada a $O $.</span><span class="sxs-lookup"><span data-stu-id="c625e-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="c625e-134">Por ejemplo, podríamos definir $O $ tal que $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.</span><span class="sxs-lookup"><span data-stu-id="c625e-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="c625e-135">\end{align} $ $ si una fase Oracle actúa en un registro inicialmente en el estado de base de cálculo $ \ket{x} $, esta fase es una fase global y, por lo tanto, no observable.</span><span class="sxs-lookup"><span data-stu-id="c625e-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="c625e-136">Pero este tipo de Oracle puede ser un recurso muy eficaz si se aplica a una superposición o como una operación controlada.</span><span class="sxs-lookup"><span data-stu-id="c625e-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="c625e-137">Por ejemplo, considere una fase orcale $O _f $ para una función única qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="c625e-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="c625e-138">Después, $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.</span><span class="sxs-lookup"><span data-stu-id="c625e-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="c625e-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c625e-139">\end{align} $$</span></span>

<span data-ttu-id="c625e-140">En general, se pueden ampliar ambas vistas de Oracle para representar funciones clásicas que devuelven números reales en lugar de un solo bit.</span><span class="sxs-lookup"><span data-stu-id="c625e-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="c625e-141">Elegir la mejor manera de implementar Oracle depende en gran medida de cómo se utilizará este Oracle dentro de un algoritmo determinado.</span><span class="sxs-lookup"><span data-stu-id="c625e-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="c625e-142">Por ejemplo, el [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) se basa en la implementación de Oracle en primer lugar, mientras que el [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) se basa en Oracle implementado de la segunda manera.</span><span class="sxs-lookup"><span data-stu-id="c625e-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="c625e-143">Para obtener más detalles, se recomienda la explicación de [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="c625e-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
