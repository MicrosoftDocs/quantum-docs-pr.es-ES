---
title: 'Bibliotecas de preguntas y respuestas: control y flujo | Microsoft Docs'
description: 'Bibliotecas de preguntas y respuestas: control y flujo'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185654"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="6d420-103">Flujo de control de orden superior</span><span class="sxs-lookup"><span data-stu-id="6d420-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="6d420-104">Uno de los roles principales de la biblioteca estándar es facilitar la rápida creación de ideas algorítmicas de alto nivel como [programas Quantum](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="6d420-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="6d420-105">Por lo tanto, Q # Canon proporciona una variedad de diferentes construcciones de control de flujo, cada una de las cuales se implementa mediante la aplicación parcial de funciones y operaciones.</span><span class="sxs-lookup"><span data-stu-id="6d420-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="6d420-106">Saltar inmediatamente a un ejemplo, considere el caso en el que uno desea construir una "CNOT escalera" en un registro:</span><span class="sxs-lookup"><span data-stu-id="6d420-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="6d420-107">Podemos expresar este patrón mediante bucles de iteración y `for`:</span><span class="sxs-lookup"><span data-stu-id="6d420-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="6d420-108">Sin embargo, expresado en términos de <xref:microsoft.quantum.canon.applytoeachca> y funciones de manipulación de matrices como <xref:microsoft.quantum.arrays.zip>, esto es mucho más corto y más fácil de leer:</span><span class="sxs-lookup"><span data-stu-id="6d420-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="6d420-109">En el resto de esta sección, proporcionaremos una serie de ejemplos de cómo usar las distintas operaciones y funciones de control de flujo que proporciona Canon para compactar los programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="6d420-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="6d420-110">Aplicar operaciones y funciones sobre matrices e intervalos</span><span class="sxs-lookup"><span data-stu-id="6d420-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="6d420-111">Una de las abstracciones principales que proporciona la Canon es la de la iteración.</span><span class="sxs-lookup"><span data-stu-id="6d420-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="6d420-112">Por ejemplo, considere una unidad con el formato $U \otimes U \otimes \cdots \otimes U $ para una unidad de qubit única $U $.</span><span class="sxs-lookup"><span data-stu-id="6d420-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="6d420-113">En Q #, podríamos usar <xref:microsoft.quantum.arrays.indexrange> para representarlo como un bucle `for` sobre un registro:</span><span class="sxs-lookup"><span data-stu-id="6d420-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="6d420-114">A continuación, podemos usar esta nueva operación como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H $.</span><span class="sxs-lookup"><span data-stu-id="6d420-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="6d420-115">Sin embargo, esto resulta complicado, especialmente en un algoritmo mayor.</span><span class="sxs-lookup"><span data-stu-id="6d420-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="6d420-116">Además, este enfoque se especializa en la operación concreta que se desea aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="6d420-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="6d420-117">Podemos usar el hecho de que las operaciones sean de primera clase para expresar este concepto algorítmico más explícitamente:</span><span class="sxs-lookup"><span data-stu-id="6d420-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="6d420-118">Aquí, el sufijo `CA` indica que la llamada a `ApplyToEach` es adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="6d420-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="6d420-119">Por lo tanto, si `U` admite `Adjoint` y `Controlled`, las líneas siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6d420-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="6d420-120">En concreto, esto significa que las llamadas a `ApplyToEachCA` pueden aparecer en las operaciones para las que se genera automáticamente una especialización de unjoin.</span><span class="sxs-lookup"><span data-stu-id="6d420-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="6d420-121">Del mismo modo, <xref:microsoft.quantum.canon.applytoeachindex> resulta útil para representar patrones de la forma `U(0, targets[0]); U(1, targets[1]); ...`y ofrece versiones para cada combinación de funciones de tipo que admite su entrada.</span><span class="sxs-lookup"><span data-stu-id="6d420-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="6d420-122">`ApplyToEach` es con parámetros de tipo, de modo que se puede utilizar con operaciones que toman entradas distintas de `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="6d420-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="6d420-123">Por ejemplo, supongamos que `codeBlocks` es una matriz de valores <xref:microsoft.quantum.errorcorrection.logicalregister> que deben recuperarse.</span><span class="sxs-lookup"><span data-stu-id="6d420-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="6d420-124">A continuación, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará el código de corrección de errores `code` y la función de recuperación `recoveryFn` en cada bloque de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="6d420-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="6d420-125">Esto se mantiene incluso para las entradas clásicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará un giro de $ \pi/$2 sobre $X $ seguido de un giro de $pi/$3 sobre $Y $.</span><span class="sxs-lookup"><span data-stu-id="6d420-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="6d420-126">Q # Canon también proporciona compatibilidad con patrones de enumeración clásicas conocidos para la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="6d420-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="6d420-127">Por ejemplo, <xref:microsoft.quantum.arrays.fold> implementa el patrón $f (f (f (s\_{\text{Initial}}, x\_0), x\_1), \dots) $ para reducir una función en una lista.</span><span class="sxs-lookup"><span data-stu-id="6d420-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="6d420-128">Este patrón se puede usar para implementar sumas, productos, mínimos, máximos y otras funciones de este tipo:</span><span class="sxs-lookup"><span data-stu-id="6d420-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="6d420-129">Del mismo modo, se pueden usar funciones como <xref:microsoft.quantum.arrays.mapped> y <xref:microsoft.quantum.arrays.mappedbyindex> para expresar conceptos de programación funcional en Q #.</span><span class="sxs-lookup"><span data-stu-id="6d420-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="6d420-130">Componer operaciones y funciones</span><span class="sxs-lookup"><span data-stu-id="6d420-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="6d420-131">Las construcciones de flujo de control que ofrece Canon toman las operaciones y las funciones como sus entradas, de modo que resulta útil poder componer varias operaciones o funciones en un único que se pueda llamar.</span><span class="sxs-lookup"><span data-stu-id="6d420-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="6d420-132">Por ejemplo, el patrón $UVU ^ {\dagger} $ es muy común en la programación de Quantum, de modo que Canon proporciona la operación <xref:microsoft.quantum.canon.applywith> como una abstracción para este patrón.</span><span class="sxs-lookup"><span data-stu-id="6d420-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="6d420-133">Esta abstracción también permite una mayor eficacia en los circuitos, como `Controlled` actúa en la secuencia `U(qubit); V(qubit); Adjoint U(qubit);` no necesita actuar en cada `U`.</span><span class="sxs-lookup"><span data-stu-id="6d420-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="6d420-134">Para ver esto, deje que $c (U) $ sea la unidad que representa `Controlled U([control], target)` y deje que $c (V) $ se defina de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="6d420-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="6d420-135">A continuación, para un estado arbitrario $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ les{1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="6d420-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="6d420-136">\end{align} por la definición de `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="6d420-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="6d420-137">Por otro lado, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="6d420-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="6d420-138">\end{align} por linealidad, podemos concluir que podemos factorizar $U $ de esta manera para todos los Estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="6d420-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="6d420-139">Es decir, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="6d420-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="6d420-140">Puesto que el control de las operaciones puede ser costoso en general, el uso de variantes controladas como `WithC` y `WithCA` puede ayudar a reducir el número de activadores de control que se deben aplicar.</span><span class="sxs-lookup"><span data-stu-id="6d420-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="6d420-141">Otra consecuencia de la división de $U $ es que no es necesario saber incluso cómo aplicar el `Controlled` functor a `U`.</span><span class="sxs-lookup"><span data-stu-id="6d420-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="6d420-142">por lo tanto, `ApplyWithCA` tiene una firma más débil de lo que cabría esperar:</span><span class="sxs-lookup"><span data-stu-id="6d420-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="6d420-143">Del mismo modo, <xref:microsoft.quantum.canon.bind> produce operaciones que aplican una secuencia de otras operaciones a su vez.</span><span class="sxs-lookup"><span data-stu-id="6d420-143">Similarly, <xref:microsoft.quantum.canon.bind> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="6d420-144">Por ejemplo, los siguientes elementos son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6d420-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

<span data-ttu-id="6d420-145">La combinación con patrones de iteración puede hacer esto especialmente útil:</span><span class="sxs-lookup"><span data-stu-id="6d420-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="6d420-146">Composición ordenada por hora</span><span class="sxs-lookup"><span data-stu-id="6d420-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="6d420-147">Todavía podemos seguir pensando en el control de flujo en términos de aplicación parcial y en funciones clásicas, y puede modelar incluso conceptos de Quantum bastante sofisticados en términos de control de flujo clásico.</span><span class="sxs-lookup"><span data-stu-id="6d420-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="6d420-148">Esta analogía se hace precisa al reconocer que los operadores unitarios corresponden exactamente a los efectos secundarios de las operaciones de llamada, de modo que cualquier descomposición de operadores unitarios en términos de otros operadores unitarios corresponde a construir un determinado secuencia de llamada para subrutinas clásicas que emiten instrucciones para actuar como operadores unitarios determinados.</span><span class="sxs-lookup"><span data-stu-id="6d420-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="6d420-149">En esta vista, `Bind` es precisamente la representación del producto de matriz, ya que `Bind([A, B])(target)` es equivalente a `A(target); B(target);`, que a su vez es la secuencia de llamada correspondiente a $BA $.</span><span class="sxs-lookup"><span data-stu-id="6d420-149">Under this view, `Bind` is precisely the representation of the matrix product, since `Bind([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="6d420-150">Un ejemplo más sofisticado es la [expansión Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="6d420-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="6d420-151">Como se describe en la sección representación dinámica del generador de [estructuras de datos](xref:microsoft.quantum.libraries.data-structures), la expansión Trotter – Suzuki proporciona una manera especialmente útil de expresar la exponencial de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6d420-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="6d420-152">Por ejemplo, si se aplica la expansión en el orden más bajo, se produce que para los operadores $A $ y $B $, $A = A ^ \dagger $ y $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i A t/n) \exp ) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="6d420-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="6d420-153">\end{align} suele, esto indica que podemos desarrollar aproximadamente un estado en $A + B $ cambiando de forma alternativa en $A $ y $B $ solo.</span><span class="sxs-lookup"><span data-stu-id="6d420-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="6d420-154">Si se representa la evolución en $A $ por una operación `A : (Double, Qubit[]) => Unit` que se aplica $e ^ {i t A} $, la representación de la expansión Trotter – Suzuki en lo que respecta a la reorganización de las secuencias de llamada queda clara.</span><span class="sxs-lookup"><span data-stu-id="6d420-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="6d420-155">Concretamente, dada una operación `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` tal que `A = U(0, _, _)` y `B = U(1, _, _)`, podemos definir una nueva operación que represente la parte entera de `U` en el tiempo $t $ generando secuencias del formulario</span><span class="sxs-lookup"><span data-stu-id="6d420-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="6d420-156">Llegados a este punto, ahora podemos pensar en la expansión Trotter – Suzuki *sin hacer referencia a la mecánica de Quantum*.</span><span class="sxs-lookup"><span data-stu-id="6d420-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="6d420-157">La expansión es en realidad un patrón de iteración muy concreto motivado por $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="6d420-158">Este patrón de iteración se implementa mediante <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span><span class="sxs-lookup"><span data-stu-id="6d420-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="6d420-159">La firma de `DecomposeIntoTimeStepsCA` sigue un patrón común en Q #, donde las colecciones que pueden estar respaldadas por matrices o por algo que los elementos de cálculo sobre la marcha se representan mediante tuplas cuyos primeros elementos son `Int` valores que indican sus longitudes.</span><span class="sxs-lookup"><span data-stu-id="6d420-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="6d420-160">Reunir juntos: controlar las operaciones</span><span class="sxs-lookup"><span data-stu-id="6d420-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="6d420-161">Por último, la Canon se basa en el `Controlled` functor, ya que proporciona métodos adicionales para la condición de las operaciones Quantum.</span><span class="sxs-lookup"><span data-stu-id="6d420-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="6d420-162">Es habitual, especialmente en la aritmética de Quantum, realizar operaciones de condición en Estados de base de cálculo distintos de $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="6d420-163">Con las operaciones de control y las funciones que se introdujeron anteriormente, podemos obtener condiciones de cuanto más generales en una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="6d420-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="6d420-164">Vamos a entrar en el modo en que <xref:microsoft.quantum.canon.controlledonbitstring> (parámetros de tipo de San), vamos a desglosar las partes una a una.</span><span class="sxs-lookup"><span data-stu-id="6d420-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="6d420-165">Lo primero que debemos hacer es definir una operación que realmente realiza el pesado trabajo de implementar el control en Estados de base de cálculo arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="6d420-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="6d420-166">Sin embargo, no llamaremos a esta operación directamente, así que agregaremos `_` al principio del nombre para indicar que es una implementación de otra construcción en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="6d420-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

<span data-ttu-id="6d420-167">Tenga en cuenta que tomamos una cadena de bits, representada como una matriz de `Bool`, que usamos para especificar el acondicionamiento que queremos aplicar a la operación `oracle` que se les proporciona.</span><span class="sxs-lookup"><span data-stu-id="6d420-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="6d420-168">Puesto que esta operación realmente realiza la aplicación directamente, también es necesario tomar los registros de control y de destino, que se representan aquí como `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="6d420-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="6d420-169">A continuación, observamos que el control del estado de base de cálculo $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ para una cadena de bits $ \vec{s} $ se puede realizar transformando $ \ket{\vec{s}} $ en $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="6d420-170">En concreto, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="6d420-171">Desde $X ^ {\dagger} = X $, esto implica que $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="6d420-172">Por lo tanto, podemos aplicar $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, aplicar `Controlled oracle`y transformar de nuevo a $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="6d420-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="6d420-173">Esta construcción es precisamente `ApplyWith`, por lo que escribimos el cuerpo de la nueva operación en consecuencia:</span><span class="sxs-lookup"><span data-stu-id="6d420-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="6d420-174">Aquí hemos usado <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P $, aplicar parcialmente a través de su destino para su uso con `ApplyWith`.</span><span class="sxs-lookup"><span data-stu-id="6d420-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="6d420-175">Sin embargo, tenga en cuenta que es necesario transformar el registro de *control* en el formulario deseado, por lo que aplicamos parcialmente la operación interna `(Controlled oracle)` en el *destino*.</span><span class="sxs-lookup"><span data-stu-id="6d420-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="6d420-176">Esto deja `ApplyWith` que actúen entre corchetes el registro de control con $P $, exactamente como se desea.</span><span class="sxs-lookup"><span data-stu-id="6d420-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="6d420-177">En este punto, podríamos hacer esto, pero de algún modo es que la nueva operación no "se siente" como aplicar el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="6d420-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="6d420-178">Por lo tanto, terminamos de definir el nuevo concepto de flujo de control escribiendo una función que toma el control de Oracle y que devuelve una nueva operación.</span><span class="sxs-lookup"><span data-stu-id="6d420-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="6d420-179">De esta manera, la nueva función tiene un aspecto muy similar al de `Controlled`, lo que ilustra que podemos definir fácilmente nuevas construcciones eficaces de flujo de control con Q # y la Canon conjuntamente:</span><span class="sxs-lookup"><span data-stu-id="6d420-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
