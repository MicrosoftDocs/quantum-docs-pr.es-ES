---
title: Operaciones y funciones en Q#
description: Cómo definir y llamar a las operaciones y funciones, así como a las especializaciones de la operación controlada y de la función contigua.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: c2ce999ea2a0fe7204f402fedb4cd3a3c15bd44b
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759431"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="d0ba4-103">Operaciones y funciones en Q#</span><span class="sxs-lookup"><span data-stu-id="d0ba4-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="d0ba4-104">Definir nuevas operaciones</span><span class="sxs-lookup"><span data-stu-id="d0ba4-104">Defining New Operations</span></span>

<span data-ttu-id="d0ba4-105">Las operaciones son el núcleo de Q# .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="d0ba4-106">Una vez declaradas, se pueden llamar desde aplicaciones .NET clásicas, por ejemplo, mediante un simulador u otras operaciones dentro de Q# .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="d0ba4-107">Cada operación definida en Q# puede llamar a cualquier número de operaciones, incluidas las operaciones intrínsecas integradas definidas por el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="d0ba4-108">La manera determinada en la que Q# define estas operaciones intrínsecas depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="d0ba4-109">Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="d0ba4-110">Cada Q# archivo de código fuente puede definir cualquier número de operaciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="d0ba4-111">Los nombres de operación deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de tipo o función.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="d0ba4-112">Una declaración de operación se compone de la palabra clave `operation` , seguida del símbolo que es el nombre de la operación, una tupla de identificador con tipo que define los argumentos de la operación, un signo de dos puntos `:` , una anotación de tipo que describe el tipo de resultado de la operación, opcionalmente una anotación con las características de la operación, una llave de apertura y, a continuación, el cuerpo de la `{ }`</span><span class="sxs-lookup"><span data-stu-id="d0ba4-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="d0ba4-113">Cada operación toma una entrada, genera una salida y especifica la implementación de una o varias especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="d0ba4-114">Las especializaciones posibles y cómo definirlas y llamarlas se detallan en las diferentes secciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="d0ba4-115">Por ahora, considere la siguiente operación, que define solo una especialización de cuerpo predeterminada y toma un único qubit como entrada y, a continuación, llama a la <xref:microsoft.quantum.intrinsic.x> operación integrada en esa entrada:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="d0ba4-116">La palabra clave `operation` comienza la definición de la operación, seguida del nombre; aquí, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="d0ba4-117">A continuación, se define el tipo de entrada ( `Qubit` ), junto con un nombre, `target` , para hacer referencia a la entrada dentro de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="d0ba4-118">Por último, `Unit` define que la salida de la operación está vacía.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="d0ba4-119">`Unit` se usa de forma similar a `void` en C# y otros lenguajes imperativos y es equivalente a `unit` en F # y otros lenguajes funcionales.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="d0ba4-120">Las operaciones también pueden devolver tipos más interesantes que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="d0ba4-121">Por ejemplo, la <xref:microsoft.quantum.intrinsic.m> operación devuelve una salida de tipo `Result` , que representa la realización de una medición.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="d0ba4-122">Puede pasarlo de una operación a otra operación o usarlo con la `let` palabra clave para definir una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="d0ba4-123">Este enfoque permite representar el cálculo clásico que interactúa con las operaciones Quantum en un nivel bajo, como en el caso de la [codificación superdensa](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="d0ba4-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="d0ba4-124">Cada operación de Q# toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="d0ba4-125">Varias entradas y salidas se representan mediante *tuplas*, que recopilan varios valores juntos en un solo valor.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="d0ba4-126">En este sentido, Q# es un lenguaje de "tupla en tupla".</span><span class="sxs-lookup"><span data-stu-id="d0ba4-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="d0ba4-127">Después de este concepto, se debe leer un conjunto de paréntesis vacíos `()` como la tupla "vacía", que tiene el tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="d0ba4-128">Operaciones controladas y contiguas</span><span class="sxs-lookup"><span data-stu-id="d0ba4-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="d0ba4-129">Si una operación implementa una transformación unitario, como es el caso de muchas operaciones en Q# , es posible definir cómo actúa la operación cuando se *adjointed* o *controla*.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="d0ba4-130">Una *especialización inversa de una operación* especifica cómo actúa el "inverso" de la operación, mientras que una especialización *controlada* especifica cómo actúa una operación cuando su aplicación está condicionada en el estado de un registro de Quantum determinado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="d0ba4-131">Los elementos contiguos de las operaciones Quantum son cruciales para muchos aspectos de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="d0ba4-132">Para ver un ejemplo de una situación de este tipo que Q# se describe en una técnica de programación útil, consulte [conjugados](#conjugations) en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="d0ba4-133">La versión controlada de una operación es una operación nueva que aplica eficazmente la operación base solo si todos los qubits de control están en un estado especificado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="d0ba4-134">Si el control qubits se encuentra en la superposición, la operación base se aplica de forma coherente a la parte adecuada de la superposición.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="d0ba4-135">Por lo tanto, las operaciones controladas suelen usarse para generar el inenredo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="d0ba4-136">Naturalmente, también podría existir una especialización *contigua controlada* , especificando la aplicación controlada del contiguot de una operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ba4-137">Si $U $ es la transformación unitario implementada por una operación `U` , `Adjoint U` representa la transformación unitario $U ^ \dagger $, que es la TRANSPOSE de conjugada compleja.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="d0ba4-138">Aplicar sucesivamente una operación y, a continuación, su unjoin a un estado deja el estado sin modificar, como se muestra por el hecho de que $UU ^ \dagger = U ^ \dagger U = \id $, la matriz de identidad.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="d0ba4-139">La representación unitario de una operación controlada es ligeramente más Matica, pero puede encontrar más detalles en [conceptos de procesamiento de quantums: varios qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="d0ba4-140">En la siguiente sección se describe cómo llamar a estas distintas especializaciones en el Q# código y cómo definir las operaciones para admitirlas.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="d0ba4-141">Llamar a especializaciones de operación</span><span class="sxs-lookup"><span data-stu-id="d0ba4-141">Calling operation specializations</span></span>

<span data-ttu-id="d0ba4-142">Un *functor* en Q# es un generador que define una nueva operación desde otra operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="d0ba4-143">Los dos funcdores estándar de Q# son `Adjoint` y `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="d0ba4-144">Los funcers tienen acceso a la implementación de la operación base al definir la implementación de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="d0ba4-145">Por lo tanto, los funcdores pueden realizar funciones más complejas que las funciones de nivel superior tradicionales.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="d0ba4-146">Los funcers no tienen una representación en el Q# sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="d0ba4-147">Por lo tanto, actualmente no es posible enlazarlas a una variable o pasarlas como argumentos.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="d0ba4-148">Para usar un functor, aplíquelo a una operación, que devuelve una nueva operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="d0ba4-149">Por ejemplo, al aplicar el `Adjoint` functor a la `Y` operación se devuelve la nueva operación `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="d0ba4-150">Puede invocar la nueva operación como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="d0ba4-151">Para que una operación admita la aplicación de los `Adjoint` `Controlled` funcrs o, su tipo de valor devuelto debe ser necesariamente `Unit` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="d0ba4-152">`Adjoint` functor</span><span class="sxs-lookup"><span data-stu-id="d0ba4-152">`Adjoint` functor</span></span>

<span data-ttu-id="d0ba4-153">Por lo tanto, `Adjoint Y(q1)` aplica el `Adjoint` functor a la `Y` operación para generar una nueva operación y aplica esa nueva operación a `q1` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="d0ba4-154">La nueva operación tiene la misma signatura y el mismo tipo que la operación base `Y` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="d0ba4-155">En concreto, la nueva operación también admite y `Adjoint` `Controlled` solo si la operación base lo hizo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="d0ba4-156">El `Adjoint` functor es su propio inverso; es decir, `Adjoint Adjoint Op` siempre es igual que `Op` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="d0ba4-157">`Controlled` functor</span><span class="sxs-lookup"><span data-stu-id="d0ba4-157">`Controlled` functor</span></span>

<span data-ttu-id="d0ba4-158">Del mismo modo, `Controlled X(controls, target)` aplica el `Controlled` functor a la `X` operación para generar una nueva operación y aplica esa nueva operación a `controls` y `target` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ba4-159">En Q# , las versiones controladas siempre toman una matriz de qubits de control y el control siempre se basa en todo el control qubits que se encuentra en el estado de cálculo ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="d0ba4-160">El control basado en otros Estados se logra aplicando la operación unitario adecuada al control qubits antes de la operación controlada y aplicando después los inversos de la operación unitario después de la operación controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="d0ba4-161">Por ejemplo, la aplicación de una `X` operación a un qubit de control antes y después de una operación controlada hace que la operación controle el `Zero` Estado ($ \ket {0} $) para ese qubit; aplicar una `H` operación antes y después de los controles en el `PauliX` `One` Estado, es decir, 1 eigenvalue de Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ en lugar del `PauliZ` `One` Estado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="d0ba4-162">Dada una expresión de operación, puede formar una nueva expresión de operación utilizando el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="d0ba4-163">La firma de la nueva operación se basa en la firma de la operación original.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="d0ba4-164">El tipo de resultado es el mismo, pero el tipo de entrada es una tupla de dos tuplas con una matriz qubit que contiene el control qubit (s) como primer elemento y los argumentos de la operación original como el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="d0ba4-165">La nueva operación admite y `Controlled` solo admitirá `Adjoint` si la operación original lo hizo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="d0ba4-166">Si la operación original solo tomó un argumento, la equivalencia de la [tupla singleton](xref:microsoft.quantum.guide.types) entra en juego aquí.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="d0ba4-167">Por ejemplo, `Controlled X` es la versión controlada de la `X` operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="d0ba4-168">`X` tiene `(Qubit => Unit is Adj + Ctl)` el tipo, por lo que `Controlled X` tiene `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` el tipo; debido a la equivalencia de la tupla singleton, es igual que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="d0ba4-169">Si la operación base tomó varios argumentos, Recuerde incluir los argumentos correspondientes de la versión controlada de la operación entre paréntesis para convertirlos en una tupla.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="d0ba4-170">Por ejemplo, `Controlled Rz` es la versión controlada de la `Rz` operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="d0ba4-171">`Rz` tiene el tipo `((Double, Qubit) => Unit is Adj + Ctl)` , por lo que `Controlled Rz` tiene el tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d0ba4-172">Por lo tanto, `Controlled Rz(controls, (0.1, target))` sería una invocación válida de `Controlled Rz` (tenga en cuenta los paréntesis `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="d0ba4-173">Como otro ejemplo, `CNOT(control, target)` se puede implementar como `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="d0ba4-174">Si un destino debe controlar dos qubits de control (CCNOT), use una `Controlled X([control1, control2], target)` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="d0ba4-175">Los `Controlled` `Adjoint` funcers y los funcs se desactivan, por lo que no hay ninguna diferencia entre aplicar `Controlled Adjoint Op` o `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="d0ba4-176">Definir implementaciones controladas y contiguas</span><span class="sxs-lookup"><span data-stu-id="d0ba4-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="d0ba4-177">En la primera declaración de operación de los ejemplos anteriores, las operaciones `BitFlip` y `DecodeSuperdense` se definieron con las signaturas `(Qubit => Unit)` y `((Qubit, Qubit) => (Result, Result))` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="d0ba4-178">Como `DecodeSuperdense` incluye las medidas, no es una operación unitario y, por tanto, no pueden existir especializaciones no contiguas controladas (Recuerde el requisito relacionado que devuelve dicha operación `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="d0ba4-179">Sin embargo, tan `BitFlip` solo realiza la <xref:microsoft.quantum.intrinsic.x> operación de la operación unitario, puede haber sido definida con ambas especializaciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="d0ba4-180">En esta sección se detalla cómo incluir la existencia de especializaciones en las Q# declaraciones de operación, lo que les proporciona la capacidad de llamar junto con `Adjoint` los `Controlled` funcrs o.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="d0ba4-181">Para obtener más información sobre algunas de las situaciones en las que es válido o no es válido declarar ciertas especializaciones, vea [circunstancias para definir especializaciones](#circumstances-for-validly-defining-specializations) de forma válida en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="d0ba4-182">Las características de la operación definen qué tipos de elementos inactivos se pueden aplicar a la operación declarada y qué efecto tienen.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="d0ba4-183">La existencia de estas especializaciones se puede declarar como parte de la firma de la operación, en concreto a través de una anotación con las características de la operación: `is Adj` , `is Ctl` o `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="d0ba4-184">La implementación real de cada especialización puede definirse *implícita* o *explícitamente* .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="d0ba4-185">Especificar implementaciones implícitamente</span><span class="sxs-lookup"><span data-stu-id="d0ba4-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="d0ba4-186">En este caso, el cuerpo de la declaración de operación consta únicamente de la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="d0ba4-187">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="d0ba4-188">Aquí, el compilador genera automáticamente la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente, que se realizará si `Adjoint` `Controlled` se usan los funcrs o.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="d0ba4-189">Por lo tanto, una llamada de `Adjoint PrepareEntangledPair` daría como resultado que el compilador implementara el objeto contiguo de `CNOT` y, a continuación, el objeto contiguo de `H` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="d0ba4-190">Estas operaciones individuales son ambas autocontiguas, por lo que la `Adjoint PrepareEntangledPair` operación resultante consistiría simplemente en aplicar `CNOT(here, there)` y, a continuación, `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="d0ba4-191">Por lo tanto, se puede utilizar para escribir `DecodeSuperdense` en el ejemplo anterior de forma más compacta, mediante el uso del valor del contiguo de `PrepareEntangledPair` para transformar el estado desenredado de nuevo en un par unentangled de qubits:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="d0ba4-192">La anotación con las características de la operación en la declaración es útil para asegurarse de que el compilador genera automáticamente otras especializaciones basadas en la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="d0ba4-193">Hay varias limitaciones importantes que se deben tener en cuenta al diseñar operaciones para usarlas con los funcdores.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="d0ba4-194">Lo más importante es que el compilador *no puede* generar automáticamente especializaciones para una operación que usa el valor de salida de cualquier otra operación, ya que es ambiguo cómo reordenar las instrucciones en dicha operación para obtener el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="d0ba4-195">Por lo tanto, a menudo resulta útil especificar explícitamente las distintas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="d0ba4-196">Especificar implementaciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="d0ba4-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="d0ba4-197">En caso de que el compilador no pueda generar la implementación, puede especificarla explícitamente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="d0ba4-198">Dichas declaraciones de especialización explícita pueden constar de una *Directiva de generación* adecuada o una implementación definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="d0ba4-199">A continuación se muestran todas las posibilidades, con algunos ejemplos de especialización explícita.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="d0ba4-200">Declaraciones de especialización explícitas</span><span class="sxs-lookup"><span data-stu-id="d0ba4-200">Explicit specialization declarations</span></span>

<span data-ttu-id="d0ba4-201">Q# las operaciones pueden contener las siguientes declaraciones de especialización explícita:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="d0ba4-202">La `body` especialización especifica la implementación de la operación sin ningún funcón aplicado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="d0ba4-203">La `adjoint` especialización especifica la implementación de la operación con el `Adjoint` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="d0ba4-204">La `controlled` especialización especifica la implementación de la operación con el `Controlled` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="d0ba4-205">La `controlled adjoint` especialización especifica la implementación de la operación con los dos tipos `Adjoint` y `Controlled` aplicados.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="d0ba4-206">Esta especialización también puede denominarse `adjoint controlled` , ya que los dos funcs se desactivan.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="d0ba4-207">Una especialización de operación consta de la etiqueta de especialización (por ejemplo, `body` o `adjoint` ) seguida de una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="d0ba4-208">Una declaración explícita tal y como se describe en lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="d0ba4-209">Una *Directiva* que indica al compilador *Cómo* generar la especialización, una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="d0ba4-210">`intrinsic`, que indica que el equipo de destino proporciona la especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="d0ba4-211">`distribute`, se utiliza con `controlled` las `controlled adjoint` especializaciones y.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="d0ba4-212">Cuando se usa con `controlled` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de `body` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="d0ba4-213">Cuando se usa con `controlled adjoint` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la `adjoint` especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="d0ba4-214">`invert`, que indica que el compilador debe calcular la especialización invirtiendo `adjoint` `body` , por ejemplo, invertir el orden de las operaciones y aplicar el objeto contiguo a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="d0ba4-215">Cuando se usa con `adjoint controlled` , esto indica que el compilador debe calcular la especialización invirtiendo la `controlled` especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="d0ba4-216">`self`, para indicar que la especialización contigua es igual que la `body` especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="d0ba4-217">`self`El uso de es válido para las `adjoint` `adjoint controlled` especializaciones y.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="d0ba4-218">Para `adjoint controlled` , `self` implica que la `adjoint controlled` especialización es la misma que la `controlled` especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="d0ba4-219">`auto`, para indicar que el compilador debe seleccionar la Directiva adecuada que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="d0ba4-220">No se puede usar `auto` para la `body` especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="d0ba4-221">Las directivas y `auto` requieren un punto y coma de cierre `;` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="d0ba4-222">La `auto` Directiva se resuelve como la siguiente directiva generada si se proporciona una declaración explícita de `body` :</span><span class="sxs-lookup"><span data-stu-id="d0ba4-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="d0ba4-223">La `adjoint` especialización genera de acuerdo con la directiva `invert` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="d0ba4-224">La `controlled` especialización genera de acuerdo con la directiva `distribute` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="d0ba4-225">La `adjoint controlled` especialización genera de acuerdo con la directiva `invert` si se proporciona una declaración explícita para `controlled` , pero no para `adjoint` , o de `distribute` lo contrario,.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="d0ba4-226">Si una operación es autocontiguo, especifique explícitamente el o la especialización del tipo contiguo o del adyacente controlado a través de la Directiva de generación `self` para permitir que el compilador haga uso de esa información con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="d0ba4-227">Una declaración de especialización que contiene una implementación definida por el usuario consta de una tupla de argumento seguida de un bloque de instrucciones con el Q# código que implementa la especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="d0ba4-228">En la lista de argumentos, `...` se usa para representar los argumentos declarados para la operación como un todo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="d0ba4-229">Para `body` y `adjoint` , la lista de argumentos siempre debe ser `(...)` ; para `controlled` y `adjoint controlled` , la lista de argumentos debe ser un símbolo que represente la matriz de qubits de control, seguida de `...` , entre paréntesis; por ejemplo, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="d0ba4-230">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d0ba4-230">Examples</span></span>

<span data-ttu-id="d0ba4-231">Una declaración de operación podría ser tan simple como la siguiente, que define la operación Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="d0ba4-232">Tenga en cuenta que el contiguo de la operación Pauli X se define con la directiva `self` porque por definición `X` es su propio inverso.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="d0ba4-233">En el `PrepareEntangledPair` ejemplo anterior, el código es equivalente al código siguiente que contiene declaraciones de especialización explícitas:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="d0ba4-234">La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="d0ba4-235">Implementación de especialización definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="d0ba4-235">User-defined specialization implementation</span></span>

<span data-ttu-id="d0ba4-236">Si el compilador no puede generar la implementación para una determinada especialización automáticamente, o si se puede proporcionar una implementación más eficaz, puede definir manualmente la implementación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="d0ba4-237">En el ejemplo anterior, `adjoint invert;` indica que la especialización de la función contigua se va a generar invirtiendo la implementación del cuerpo e `controlled adjoint invert;` indica que la especialización contigua controlada se va a generar invirtiendo la implementación determinada de la especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="d0ba4-238">Si es necesario declarar explícitamente una o más especializaciones además del cuerpo predeterminado, la implementación del cuerpo predeterminado debe ajustarse también en una declaración de especialización adecuada:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="d0ba4-239">Circunstancias para la definición válida de especializaciones</span><span class="sxs-lookup"><span data-stu-id="d0ba4-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="d0ba4-240">Declaraciones de operación con el o el control contiguo</span><span class="sxs-lookup"><span data-stu-id="d0ba4-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="d0ba4-241">Es válido especificar una operación sin ninguna versión contigua o controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="d0ba4-242">Por ejemplo, las operaciones de medición no tienen ninguna porque no se pueden invertir ni controlar.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="d0ba4-243">Una operación admite los `Adjoint` `Controlled` funcrs y si su declaración contiene una declaración implícita o explícita de las especializaciones respectivas.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="d0ba4-244">Una especialización indefinida o controlada explícitamente declarada implica la existencia de una especialización con o sin control.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="d0ba4-245">En el caso de una operación cuyo cuerpo contenga bucles de repetición hasta la ejecución correcta, instrucciones SET, medidas, instrucciones Return o llamadas a otras operaciones que no admitan el `Adjoint` functor, no es posible generar automáticamente una especialización de un método contiguo después de la `invert` `auto` Directiva o.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="d0ba4-246">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no admitan el `Controlled` functor, la generación automática de una especialización controlada después de la `distribute` `auto` Directiva o no es posible.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="d0ba4-247">Contiguo controlado</span><span class="sxs-lookup"><span data-stu-id="d0ba4-247">Controlled Adjoint</span></span>

<span data-ttu-id="d0ba4-248">La versión de la contigua controlada de una operación especifica cómo implementar una versión controlada por Quantum del método contiguo de la operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="d0ba4-249">Es válido especificar una operación sin ninguna versión contigua controlada; por ejemplo, las operaciones de medición no tienen ninguna versión contigua controlada porque no se pueden controlar ni invertir.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="d0ba4-250">Es necesario que exista una especialización del mismo bajo controlada para una operación si y solo si hay un Join y una especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="d0ba4-251">En ese caso, se infiere la existencia de la especialización contigua controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="d0ba4-252">Si no se define explícitamente ninguna implementación, la compilación genera una especialización adecuada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="d0ba4-253">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no tienen una versión de la función contigua controlada, la generación automática de una especialización de la función `invert` , `distribute` o `auto` no es posible.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="d0ba4-254">Compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="d0ba4-254">Type Compatibility</span></span>

<span data-ttu-id="d0ba4-255">Use una operación con funciones más inactivas adicionales admitidas en cualquier lugar en el que use una operación con menos funcciones pero con la misma firma.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="d0ba4-256">Por ejemplo, use una operación de tipo `(Qubit => Unit is Adj)` en cualquier lugar en el que use una operación de tipo `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="d0ba4-257">Q# es *covariante* con respecto a los tipos de valor devueltos a los que se puede llamar: una invocable que devuelve un tipo `'A` es compatible con una a la que se puede llamar con el mismo tipo de entrada y un tipo de resultado que es compatible con `'A` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="d0ba4-258">Q# es *contravariante* con respecto a los tipos de entrada: un llamador que toma un tipo `'A` como entrada es compatible con una operación invocable con el mismo tipo de resultado y un tipo de entrada compatible con `'A` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="d0ba4-259">Es decir, dadas las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-259">That is, given the following definitions,</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="d0ba4-260">Puedes</span><span class="sxs-lookup"><span data-stu-id="d0ba4-260">you can</span></span>

- <span data-ttu-id="d0ba4-261">Invoque la función `ConjugateInvertWith` con un `inner` argumento de `Invert` o `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="d0ba4-262">Invocar la función `ConjugateUnitaryWith` con un `inner` argumento de `ApplyUnitary` , pero no `Invert` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="d0ba4-263">Devuelve un valor de tipo `(Qubit[] => Unit is Adj + Ctl)` desde `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0ba4-264">Q# 0,3 presentó una diferencia significativa en el comportamiento de los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="d0ba4-265">Los tipos definidos por el usuario se tratan como una versión ajustada del tipo subyacente, en lugar de como un subtipo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="d0ba4-266">Esto significa que un valor de un tipo definido por el usuario no se puede usar cuando se espera que un valor del tipo subyacente sea.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="d0ba4-267">Conjugaciones</span><span class="sxs-lookup"><span data-stu-id="d0ba4-267">Conjugations</span></span>

<span data-ttu-id="d0ba4-268">A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="d0ba4-269">Estos efectos se pueden evitar al "deshacer" correctamente los cálculos realizados antes de liberar la memoria.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="d0ba4-270">Un patrón común en la informática Quantum es, por lo tanto, lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="d0ba4-271">A partir de la versión 0,9, Q# admite una instrucción de conjugación que implementa la transformación anterior.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="d0ba4-272">Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="d0ba4-273">Este tipo de instrucción de conjugación resulta mucho más útil si las transformaciones externas e internas no están disponibles como operaciones, sino que son más cómodas de describir en un bloque que consta de varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="d0ba4-274">El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="d0ba4-275">Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="d0ba4-276">Definir nuevas funciones</span><span class="sxs-lookup"><span data-stu-id="d0ba4-276">Defining New Functions</span></span>

<span data-ttu-id="d0ba4-277">Las funciones son rutinas puramente deterministas en Q# , que son distintas de las operaciones en que no se les permite tener ningún efecto más allá del cálculo de un valor de salida.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="d0ba4-278">En concreto, las funciones no pueden llamar a las operaciones; actuar sobre, asignar o tomar prestado qubits; números aleatorios de muestra; o, en caso contrario, dependen del estado más allá del valor de entrada de una función.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="d0ba4-279">Como consecuencia, Q# las funciones son *puras*, ya que siempre asignan los mismos valores de entrada a los mismos valores de salida.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="d0ba4-280">Este comportamiento permite Q# que el compilador reordene de forma segura cómo y cuándo llamar a funciones al generar especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="d0ba4-281">Cada Q# archivo de código fuente puede definir cualquier número de funciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="d0ba4-282">Los nombres de función deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación o tipo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="d0ba4-283">La definición de una función funciona de forma similar a la definición de una operación, con la excepción de que no se puede definir ninguna especialización contigua o controlada para una función.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="d0ba4-284">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="d0ba4-285">o</span><span class="sxs-lookup"><span data-stu-id="d0ba4-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="d0ba4-286">Lógica clásica en functions = = Good</span><span class="sxs-lookup"><span data-stu-id="d0ba4-286">Classical logic in functions == good</span></span>

<span data-ttu-id="d0ba4-287">Siempre que sea posible hacerlo, resulta útil escribir una lógica clásica en cuanto a funciones, en lugar de operaciones para que las operaciones puedan usarla más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="d0ba4-288">Por ejemplo, si ha escrito la declaración anterior `Square` como una *operación*, el compilador no habría podido garantizar que la llamada a ella con la misma entrada produciría sistemáticamente los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="d0ba4-289">Para subrayar la diferencia entre las funciones y las operaciones, tenga en cuenta el problema de realizar un muestreo de forma de un número aleatorio en una Q# operación:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="d0ba4-290">Cada vez que `U` se llama a, tiene una acción diferente en `target` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="d0ba4-291">En concreto, el compilador no puede garantizar que si agrega una `adjoint auto` declaración de especialización a `U` , `U(target); Adjoint U(target);` actúa como identidad (es decir, como una operación no operativa).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="d0ba4-292">Esto infringe la definición del método contiguo definido en [vectores y matrices](xref:microsoft.quantum.concepts.vectors), de modo que permitir que el compilador genere automáticamente una especialización de tipo contiguo en una operación en la que se llama a la operación <xref:microsoft.quantum.math.randomreal> interrumpiría las garantías proporcionadas por el compilador; <xref:microsoft.quantum.math.randomreal> es una operación para la que no existe ninguna versión contigua o controlada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="d0ba4-293">Por otro lado, permitir llamadas a funciones como `Square` es segura y garantiza que el compilador solo necesita conservar la entrada en `Square` para mantener su salida estable.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="d0ba4-294">Por lo tanto, el aislamiento de la lógica más clásica posible en las funciones facilita la reutilización de esa lógica en otras funciones y operaciones similares.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="d0ba4-295">Llamadas genéricas (con parámetros de tipo)</span><span class="sxs-lookup"><span data-stu-id="d0ba4-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="d0ba4-296">Muchas funciones y operaciones que puede desear definir no dependen en gran medida de los tipos de sus entradas, sino que solo usan implícitamente sus tipos a través de otra función u operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="d0ba4-297">Por ejemplo, considere el concepto de *mapa* común a muchos idiomas funcionales; dada una función $f (x) $ y una colección de valores $ \{ x_1, x_2, \dots, x_n \} $, Map devuelve una nueva colección $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="d0ba4-298">Para implementar esto en Q# , aproveche el hecho de que las funciones son de primera clase.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="d0ba4-299">Este es un ejemplo rápido de `Map` , que usa `T` como marcador de posición mientras averigua qué tipos necesita.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="d0ba4-300">Tenga en cuenta que esta función tiene un aspecto muy similar al de los tipos reales que se sustituyen.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="d0ba4-301">Una asignación de enteros a Paulis, por ejemplo, se parece mucho a una asignación de números de punto flotante a cadenas:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="d0ba4-302">En principio, puede escribir una versión de `Map` para cada par de tipos que encuentre, pero esto presenta varias dificultades.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="d0ba4-303">Por ejemplo, si encuentra un error en `Map` , debe asegurarse de que la corrección se aplica uniformemente en todas las versiones de `Map` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="d0ba4-304">Además, si crea una nueva tupla o UDT, ahora también debe construir un nuevo `Map` para ir junto con el nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="d0ba4-305">Aunque esto es tractable para un número pequeño de estas funciones, a medida que se recopilan más funciones de la misma forma que `Map` , el costo de introducir nuevos tipos se vuelve injustificable en un orden bastante corto.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="d0ba4-306">Sin embargo, gran parte de esta dificultad se debe al hecho de que no se ha proporcionado al compilador la información necesaria para reconocer cómo `Map` se relacionan las distintas versiones de.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="d0ba4-307">De hecho, desea que el compilador trate `Map` como algún tipo de función matemática de Q# *tipos* a Q# funciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="d0ba4-308">Q# formaliza esta noción permitiendo que las funciones y operaciones tengan *parámetros de tipo*, así como sus parámetros de tupla normales.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="d0ba4-309">En los ejemplos anteriores, desea considerar que `Map` tienen parámetros de tipo `Int, Pauli` en el primer caso y `Double, String` en el segundo caso.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="d0ba4-310">En su mayor parte, use estos parámetros de tipo como si fueran tipos normales.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="d0ba4-311">Use valores de parámetros de tipo para crear matrices y tuplas, llamar a funciones y operaciones y asignarlas a variables ordinarias o mutables.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ba4-312">El caso más extremo de dependencia indirecta es el de qubits, donde un Q# programa no puede confiar directamente en la estructura del `Qubit` tipo, sino que **debe** pasar estos tipos a otras operaciones y funciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="d0ba4-313">Volviendo al ejemplo anterior, verá que `Map` debe tener parámetros de tipo, uno para representar la entrada `fn` y otro para representar la salida de `fn` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="d0ba4-314">En Q# , esto se escribe agregando corchetes angulares (es decir `<>` , no frenos $ \braket {} $!) después del nombre de una función u operación en su declaración y enumerando cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="d0ba4-315">El nombre de cada parámetro de tipo debe empezar con un paso `'` , lo que indica que se trata de un parámetro de tipo y no de un tipo ordinario (también conocido como tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="d0ba4-316">Por lo tanto, `Map` se escribe:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="d0ba4-317">Tenga en cuenta que la definición de `Map<'Input, 'Output>` es muy similar a las versiones de previoius.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="d0ba4-318">La única diferencia es que ha informado explícitamente al compilador que `Map` no depende directamente de lo que `'Input` y `'Output` son, pero funciona para dos tipos mediante el uso indirecto a través de `fn` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="d0ba4-319">Una vez que haya definido `Map<'Input, 'Output>` de esta manera, puede llamarlo como si fuera una función ordinaria:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="d0ba4-320">La escritura de funciones y operaciones genéricas es un lugar donde "tupla en tupla" es una forma muy útil de pensar en Q# las funciones y operaciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="d0ba4-321">Puesto que cada función toma exactamente una entrada y devuelve exactamente una salida, una entrada de tipo `'T -> 'U` coincide con *cualquier* Q# función.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="d0ba4-322">Del mismo modo, puede pasar cualquier operación a una entrada de tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="d0ba4-323">Como segundo ejemplo, considere el reto de escribir una función que devuelva la composición de otras dos funciones:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="d0ba4-324">En este caso, debe especificar exactamente qué `A` , `B` y son, por lo que `C` limitan gravemente la utilidad de la nueva `Compose` función.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="d0ba4-325">Después de todo, `Compose` solo depende de `A` , `B` y `C` *a través* de `innerFn` y `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="d0ba4-326">Como alternativa, puede agregar parámetros de tipo a `Compose` que indiquen que funciona para *cualquier* `A` , `B` y `C` , siempre y cuando estos parámetros coincidan con los esperados por `innerFn` y `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="d0ba4-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="d0ba4-327">Las Q# bibliotecas estándar proporcionan una gama de funciones y operaciones parametrizadas de tipo para facilitar la rápida creación de un flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="d0ba4-328">Estos se describen con más detalle en la guía de la [ Q# biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="d0ba4-329">Se puede llamar como valores de primera clase</span><span class="sxs-lookup"><span data-stu-id="d0ba4-329">Callables as First-Class Values</span></span>

<span data-ttu-id="d0ba4-330">Una técnica crítica para el razonamiento sobre el flujo de control y la lógica clásica mediante funciones en lugar de las operaciones es usar las operaciones y funciones de Q# *la primera clase*.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="d0ba4-331">Es decir, cada uno de los valores del lenguaje se encuentra en su propio derecho.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="d0ba4-332">Por ejemplo, el siguiente código es perfectamente válido Q# , si un poco indirecto:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="d0ba4-333">El valor de la variable `ourH` en el fragmento de código anterior es la operación <xref:microsoft.quantum.intrinsic.h> , de modo que puede llamar a ese valor como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="d0ba4-334">Con esta capacidad, puede escribir operaciones que tomen las operaciones como parte de su entrada, formando conceptos de flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="d0ba4-335">Por ejemplo, podría imaginar que desea "cuadrado" una operación aplicándole dos veces en el mismo qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="d0ba4-336">Devolver operaciones desde una función</span><span class="sxs-lookup"><span data-stu-id="d0ba4-336">Returning operations from a function</span></span>

<span data-ttu-id="d0ba4-337">Es importante resaltar que también puede devolver las operaciones como parte de las salidas, de modo que pueda aislar algunos tipos de lógica condicional clásica como una función clásica, que devuelve una descripción de un programa Quantum en forma de una operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="d0ba4-338">Como ejemplo sencillo, considere el ejemplo de teleportabilidad, en el que la entidad que recibe un mensaje clásico de dos bits debe usar el mensaje para descodificar sus qubit en el estado de telepuerto adecuado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="d0ba4-339">Podría escribir esto en términos de una función que toma esos dos bits clásico y devuelve la operación de descodificación adecuada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="d0ba4-340">Esta nueva función es realmente una función, en que si se llama con los mismos valores de `hereBit` y `thereBit` , siempre se obtiene la misma operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="d0ba4-341">Por lo tanto, el descodificador puede ejecutarse de forma segura dentro de las operaciones sin tener que preocuparse de cómo la lógica de descodificación interactúa con las definiciones de las distintas especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="d0ba4-342">Es decir, la lógica clásica dentro de una función está aislada, garantizando al compilador que la llamada a la función se puede reordenar con Impunity, siempre y cuando se conserve la entrada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="d0ba4-343">Aplicación parcial</span><span class="sxs-lookup"><span data-stu-id="d0ba4-343">Partial Application</span></span>

<span data-ttu-id="d0ba4-344">Puede hacer mucho más con funciones que devuelven operaciones mediante el uso de una *aplicación parcial*, en la que proporciona una o más partes de la entrada a una función u operación sin llamarla realmente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="d0ba4-345">En el `ApplyTwice` ejemplo anterior, puede indicar que no desea especificar, de inmediato, a qué qubit se debe aplicar la operación de entrada:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="d0ba4-346">En este caso, la variable local `twiceOp` contiene la operación parcialmente aplicada `ApplyTwice(op, _)` , donde `_` indica las partes de la entrada que todavía no se han especificado.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="d0ba4-347">Cuando se llama a `twiceOp` en la línea siguiente, se pasa como entrada a la operación parcialmente aplicada todas las partes restantes de la entrada a la operación original.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="d0ba4-348">Por lo tanto, el fragmento de código anterior es realmente idéntico a haber llamado `ApplyTwice(op, target)` directamente a, guardar para que haya introducido una nueva variable local para que pueda retrasar la llamada mientras proporciona algunas partes de la entrada.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="d0ba4-349">Dado que una operación que se ha aplicado parcialmente no se llama realmente hasta que se ha proporcionado toda la entrada, puede aplicar de forma segura operaciones parcialmente incluso desde dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="d0ba4-350">En principio, la lógica clásica dentro de `SquareOperation` podría haber sido mucho más complicada, pero sigue estando aislada del resto de una operación mediante la garantía de que el compilador puede ofrecer sobre las funciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="d0ba4-351">La Q# biblioteca estándar usa este enfoque para expresar el flujo de control clásico de manera que los programas Quantum puedan usarse fácilmente.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="d0ba4-352">Recursividad</span><span class="sxs-lookup"><span data-stu-id="d0ba4-352">Recursion</span></span>

<span data-ttu-id="d0ba4-353">Q# se permite que las llamadas se puedan realizar de forma directa o indirecta.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="d0ba4-354">Es decir, una operación o función se puede llamar a sí misma, o puede llamar a otra llamada invocable que llama directa o indirectamente a la operación que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="d0ba4-355">Sin embargo, hay dos comentarios importantes sobre el uso de la recursividad:</span><span class="sxs-lookup"><span data-stu-id="d0ba4-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="d0ba4-356">Es probable que el uso de la recursividad en las operaciones interfiera con ciertas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="d0ba4-357">Estas interferencias pueden tener un impacto considerable en el tiempo de ejecución del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="d0ba4-358">Cuando se ejecuta en un dispositivo Quantum real, el espacio de pila podría estar limitado y, por tanto, la recursividad profunda puede provocar un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="d0ba4-359">En concreto, el Q# compilador y el runtime no identifican ni optimizan la recursividad del final.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0ba4-360">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d0ba4-360">Next steps</span></span>

<span data-ttu-id="d0ba4-361">Obtenga información sobre [las variables](xref:microsoft.quantum.guide.variables) en Q# .</span><span class="sxs-lookup"><span data-stu-id="d0ba4-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>