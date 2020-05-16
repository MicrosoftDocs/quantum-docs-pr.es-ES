---
title: 'Operaciones y funciones en Q #'
description: Cómo definir y llamar a las operaciones y funciones, así como a las especializaciones de la operación controlada y de la función contigua.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431077"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="40b85-103">Operaciones y funciones en Q #</span><span class="sxs-lookup"><span data-stu-id="40b85-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="40b85-104">Definir nuevas operaciones</span><span class="sxs-lookup"><span data-stu-id="40b85-104">Defining New Operations</span></span>

<span data-ttu-id="40b85-105">Las operaciones son el núcleo de Q #.</span><span class="sxs-lookup"><span data-stu-id="40b85-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="40b85-106">Una vez declarada, se puede llamar desde aplicaciones .NET clásicas, por ejemplo, mediante un simulador u otras operaciones en Q #.</span><span class="sxs-lookup"><span data-stu-id="40b85-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="40b85-107">Cada operación definida en Q # puede llamar a cualquier número de operaciones, incluidas las operaciones intrínsecas integradas definidas por el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="40b85-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="40b85-108">La manera determinada en la que se definen estas operaciones intrínsecas depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="40b85-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="40b85-109">Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="40b85-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="40b85-110">Cada archivo de código fuente de Q # puede definir cualquier número de operaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="40b85-111">Los nombres de operación deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de tipo o función.</span><span class="sxs-lookup"><span data-stu-id="40b85-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="40b85-112">Una declaración de operación consta de la palabra clave `operation` , seguida del símbolo que es el nombre de la operación, una tupla de identificador con tipo que define los argumentos para la operación, dos puntos `:` , una anotación de tipo que describe el tipo de resultado de la operación, opcionalmente una anotación con las características de la operación, una llave `{` de apertura, el cuerpo de la declaración de la operación y una llave de `}`</span><span class="sxs-lookup"><span data-stu-id="40b85-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="40b85-113">Cada operación toma una entrada, genera una salida y especifica la implementación de una o varias especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="40b85-114">Las especializaciones posibles y cómo definirlas o llamarlas se detallan más adelante.</span><span class="sxs-lookup"><span data-stu-id="40b85-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="40b85-115">Por ahora, considere la siguiente operación, que define solo una especialización de cuerpo predeterminada y toma un único qubit como entrada y, a continuación, llama a la <xref:microsoft.quantum.intrinsic.x> operación integrada en esa entrada:</span><span class="sxs-lookup"><span data-stu-id="40b85-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="40b85-116">La palabra clave `operation` comienza la definición de la operación y va seguida del nombre; aquí, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="40b85-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="40b85-117">Después, el tipo de la entrada se define como `Qubit` , junto con un nombre `target` para hacer referencia a la entrada dentro de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="40b85-118">Del mismo modo, `Unit` define que la salida de la operación está vacía.</span><span class="sxs-lookup"><span data-stu-id="40b85-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="40b85-119">Se usa de forma similar a `void` en C# y otros lenguajes imperativos, y es equivalente a `unit` en F # y otros lenguajes funcionales.</span><span class="sxs-lookup"><span data-stu-id="40b85-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="40b85-120">Las operaciones también pueden devolver tipos más interesantes que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="40b85-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="40b85-121">Por ejemplo, la <xref:microsoft.quantum.intrinsic.m> operación devuelve una salida de tipo `Result` , que representa la realización de una medición.</span><span class="sxs-lookup"><span data-stu-id="40b85-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="40b85-122">Podemos pasar el resultado de una operación a otra operación, o bien puede usarlo con la `let` palabra clave para definir una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="40b85-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="40b85-123">Esto permite representar el cálculo clásico que interactúa con las operaciones Quantum en un nivel bajo, como en el caso de la [codificación superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="40b85-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="40b85-124">Cada operación de Q # toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="40b85-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="40b85-125">A continuación, se representan varias entradas y salidas mediante *tuplas*, que recopilan varios valores juntos en un solo valor.</span><span class="sxs-lookup"><span data-stu-id="40b85-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="40b85-126">De manera informativa, decimos que Q # es un lenguaje de "tupla de tupla en".</span><span class="sxs-lookup"><span data-stu-id="40b85-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="40b85-127">Después de este concepto, `()` se debe leer como la tupla "vacía", que tiene el tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="40b85-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="40b85-128">Operaciones controladas y contiguas</span><span class="sxs-lookup"><span data-stu-id="40b85-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="40b85-129">Si una operación implementa una transformación unitario, como es el caso de muchas operaciones en Q #, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*.</span><span class="sxs-lookup"><span data-stu-id="40b85-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="40b85-130">Una *especialización inversa de una operación* especifica cómo actúa el "inverso" de la operación, mientras que una especialización *controlada* especifica cómo actúa una operación cuando su aplicación está condicionada en el estado de un registro de Quantum determinado.</span><span class="sxs-lookup"><span data-stu-id="40b85-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="40b85-131">Los elementos contiguos de las operaciones Quantum son cruciales para muchos aspectos de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="40b85-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="40b85-132">Más adelante, en la sección [conjugados](#conjugations) , encontrará una situación que se describe junto con una técnica de programación de Q # útil.</span><span class="sxs-lookup"><span data-stu-id="40b85-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="40b85-133">La versión controlada de una operación es una operación nueva que aplica eficazmente la operación base solo si todos los qubits de control están en un estado especificado.</span><span class="sxs-lookup"><span data-stu-id="40b85-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="40b85-134">Si el control qubits se encuentra en la superposición, la operación base se aplica de forma coherente a la parte adecuada de la superposición.</span><span class="sxs-lookup"><span data-stu-id="40b85-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="40b85-135">Por lo tanto, las operaciones controladas suelen usarse para generar el inenredo.</span><span class="sxs-lookup"><span data-stu-id="40b85-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="40b85-136">Naturalmente, también podría existir una especialización *contigua controlada* , especificando la aplicación controlada del contiguot de una operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="40b85-137">Si $U $ es la transformación unitario implementada por una operación `U` , `Adjoint U` representa la transformación unitario $U ^ \dagger $, que es la TRANSPOSE de conjugada compleja.</span><span class="sxs-lookup"><span data-stu-id="40b85-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="40b85-138">Aplicar sucesivamente una operación y, a continuación, su unjoin a un estado deja el estado sin modificar, como se muestra por el hecho de que $UU ^ \dagger = U ^ \dagger U = \id $, la matriz de identidad.</span><span class="sxs-lookup"><span data-stu-id="40b85-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="40b85-139">La representación unitario de una operación controlada es ligeramente más Matica, pero puede encontrar más detalles en [conceptos de procesamiento de quantums: varios qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="40b85-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="40b85-140">En la siguiente sección se describe cómo llamar a estas distintas especializaciones en el código de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="40b85-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="40b85-141">A continuación, se detalla cómo definir las operaciones para admitirlos.</span><span class="sxs-lookup"><span data-stu-id="40b85-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="40b85-142">Llamar a especializaciones de operación</span><span class="sxs-lookup"><span data-stu-id="40b85-142">Calling operation specializations</span></span>

<span data-ttu-id="40b85-143">Un *functor* en Q # es un generador que define una nueva operación desde otra operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="40b85-144">Los dos funcdores estándar en Q # son `Adjoint` y `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="40b85-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="40b85-145">Los funcers tienen acceso a la implementación de la operación base al definir la implementación de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="40b85-146">Por lo tanto, los funcdores pueden realizar funciones más complejas que las funciones de nivel superior tradicionales.</span><span class="sxs-lookup"><span data-stu-id="40b85-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="40b85-147">Los inactivos no tienen una representación en el sistema de tipos de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="40b85-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="40b85-148">Por lo tanto, actualmente no es posible enlazarlas a una variable o pasarlas como argumentos.</span><span class="sxs-lookup"><span data-stu-id="40b85-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="40b85-149">Se usa un functor si se aplica a una operación y se devuelve una nueva operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="40b85-150">Por ejemplo, la operación que resulta de aplicar el `Adjoint` functor a la `Y` operación se escribe como `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="40b85-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="40b85-151">La nueva operación se puede invocar después como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="40b85-152">Para que una operación admita la aplicación de los `Adjoint` valores de y/o los `Controlled` funcers, su tipo de valor devuelto debe ser necesariamente `Unit` .</span><span class="sxs-lookup"><span data-stu-id="40b85-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="40b85-153">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="40b85-153">`Adjoint` functor</span></span>

<span data-ttu-id="40b85-154">Por lo tanto, `Adjoint Y(q1)` aplica el funct injoin a la `Y` operación para generar una nueva operación y aplica esa nueva operación a `q1` .</span><span class="sxs-lookup"><span data-stu-id="40b85-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="40b85-155">La nueva operación tiene la misma signatura y el mismo tipo que la operación base `Y` .</span><span class="sxs-lookup"><span data-stu-id="40b85-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="40b85-156">En concreto, la nueva operación también permite `Adjoint` , y permitirá `Controlled` solo si la operación base lo hizo.</span><span class="sxs-lookup"><span data-stu-id="40b85-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="40b85-157">El inverso inmediato es su propio inverso; es decir, `Adjoint Adjoint Op` siempre es igual que `Op` .</span><span class="sxs-lookup"><span data-stu-id="40b85-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="40b85-158">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="40b85-158">`Controlled` functor</span></span>

<span data-ttu-id="40b85-159">Del mismo modo, `Controlled X(controls, target)` aplica el functor controlado a la `X` operación para generar una nueva operación y aplica esa nueva operación `controls` a y `target` .</span><span class="sxs-lookup"><span data-stu-id="40b85-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="40b85-160">En Q #, las versiones controladas siempre toman una matriz de qubits de control, y el estado especificado siempre es para que todos los qubits de control estén en el estado de cálculo ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="40b85-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="40b85-161">El control basado en otros Estados puede lograrse aplicando la operación unitario adecuada al control qubits antes de la operación controlada y aplicando después los inversos de la operación unitario después de la operación controlada.</span><span class="sxs-lookup"><span data-stu-id="40b85-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="40b85-162">Por ejemplo, la aplicación de una `X` operación a un qubit de control antes y después de una operación controlada hará que la operación se controle en el `Zero` Estado ($ \ket {0} $) para ese qubit; la aplicación de una `H` operación antes y después del control se controlará en el `PauliX` `One` Estado, que es-1 eigenvalue de Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ en `PauliZ` `One`</span><span class="sxs-lookup"><span data-stu-id="40b85-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="40b85-163">Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="40b85-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="40b85-164">La firma de la nueva operación se basa en la firma de la operación original.</span><span class="sxs-lookup"><span data-stu-id="40b85-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="40b85-165">El tipo de resultado es el mismo, pero el tipo de entrada es una tupla de dos tuplas con una matriz qubit que contiene el control qubit (s) como primer elemento y los argumentos de la operación original como el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="40b85-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="40b85-166">La nueva operación admite y `Controlled` solo admitirá `Adjoint` si la operación original lo hizo.</span><span class="sxs-lookup"><span data-stu-id="40b85-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="40b85-167">Si la operación original solo tomó un argumento, la equivalencia de la tupla singleton entrará en juego aquí.</span><span class="sxs-lookup"><span data-stu-id="40b85-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="40b85-168">Por ejemplo, `Controlled X` es la versión controlada de la `X` operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="40b85-169">`X`tiene `(Qubit => Unit is Adj + Ctl)` el tipo, por lo que `Controlled X` tiene `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` el tipo; debido a la equivalencia de la tupla singleton, es igual que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="40b85-170">Si la operación base tomó varios argumentos, Recuerde incluir los argumentos correspondientes de la versión controlada de la operación entre paréntesis para convertirlos en una tupla.</span><span class="sxs-lookup"><span data-stu-id="40b85-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="40b85-171">Por ejemplo, `Controlled Rz` es la versión controlada de la `Rz` operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="40b85-172">`Rz`tiene el tipo `((Double, Qubit) => Unit is Adj + Ctl)` , por lo que `Controlled Rz` tiene el tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="40b85-173">Por lo tanto, `Controlled Rz(controls, (0.1, target))` sería una invocación válida de `Controlled Rz` (tenga en cuenta los paréntesis `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="40b85-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="40b85-174">Como otro ejemplo, `CNOT(control, target)` se puede implementar como `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="40b85-175">Si un destino debe controlarse mediante 2 control qubits (CCNOT), se puede usar la `Controlled X([control1, control2], target)` instrucción.</span><span class="sxs-lookup"><span data-stu-id="40b85-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="40b85-176">Los `Controlled` `Adjoint` funcers y los funcs se desactivan, por lo que no hay ninguna diferencia entre aplicar `Controlled Adjoint Op` o `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="40b85-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="40b85-177">Definir implementaciones controladas y contiguas</span><span class="sxs-lookup"><span data-stu-id="40b85-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="40b85-178">En los ejemplos de la primera declaración de operación anteriores, las operaciones `BitFlip` y `DecodeSuperdense` se definieron con las signaturas `(Qubit => Unit)` y `((Qubit, Qubit) => (Result, Result))` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="40b85-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="40b85-179">Como `DecodeSuperdense` incluye las medidas, no es una operación unitario y, por tanto, no pueden existir especializaciones no contiguas controladas (Recuerde el requisito relacionado que devuelve dicha operación `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="40b85-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="40b85-180">Sin embargo, como `BitFlip` simplemente realiza la <xref:microsoft.quantum.intrinsic.x> operación unitario, podríamos haber definido con ambas especializaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="40b85-181">Aquí, detallamos cómo incluir la existencia de especializaciones en las declaraciones de la operación de Q #, por lo que les proporciona la capacidad de llamar junto con los `Adjoint` y/o los `Controlled` funcdores.</span><span class="sxs-lookup"><span data-stu-id="40b85-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="40b85-182">[A continuación](#circumstances-for-validly-defining-specializations)se describen algunas de las situaciones en las que es válido o no es válido declarar ciertas especializaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="40b85-183">Las características de la operación definen qué tipos de funcs se pueden aplicar a la operación declarada y qué efecto tienen.</span><span class="sxs-lookup"><span data-stu-id="40b85-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="40b85-184">La existencia de estas especializaciones se puede declarar como parte de la firma de la operación, en concreto a través de una anotación con las características de la operación: `is Adj` , `is Ctl` o `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="40b85-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="40b85-185">La implementación real de cada especialización puede definirse *implícita* o *explícitamente* .</span><span class="sxs-lookup"><span data-stu-id="40b85-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="40b85-186">Especificar implementaciones implícitamente</span><span class="sxs-lookup"><span data-stu-id="40b85-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="40b85-187">En este caso, el cuerpo de la declaración de operación consta únicamente de la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40b85-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="40b85-188">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="40b85-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="40b85-189">Aquí, el compilador genera automáticamente la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente, que se realizará si `Adjoint` `Controlled` se usan los funcrs o.</span><span class="sxs-lookup"><span data-stu-id="40b85-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="40b85-190">Por lo tanto, una llamada de `Adjoint PrepareEntangledPair` daría como resultado que el compilador implementara el objeto contiguo de `CNOT` y, a continuación, el objeto contiguo de `H` .</span><span class="sxs-lookup"><span data-stu-id="40b85-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="40b85-191">Estas operaciones individuales son ambas autocontiguas, por lo que la `Adjoint PrepareEntangledPair` operación resultante consistiría simplemente en aplicar `CNOT(here, there)` y, a continuación, `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="40b85-192">Por lo tanto, se puede usar para escribir el `DecodeSuperdense` ejemplo anterior de forma más compacta, mediante el uso del contiguo de `PrepareEntangledPair` para transformar el estado desenredado de nuevo en un par de unentangled de qubits:</span><span class="sxs-lookup"><span data-stu-id="40b85-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="40b85-193">La anotación con las características de la operación en la declaración es útil para asegurarse de que el compilador genera automáticamente otras especializaciones basadas en la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40b85-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="40b85-194">Hay una serie de limitaciones importantes que se deben tener en cuenta al diseñar operaciones para usarlas con los funcdores.</span><span class="sxs-lookup"><span data-stu-id="40b85-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="40b85-195">Lo más importante es que el compilador *no puede* generar automáticamente especializaciones para una operación que usa el valor de salida de cualquier otra operación, ya que es ambiguo cómo reordenar las instrucciones en dicha operación para obtener el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="40b85-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="40b85-196">Por lo tanto, a menudo resulta útil especificar explícitamente las distintas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="40b85-197">Especificar implementaciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="40b85-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="40b85-198">En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="40b85-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="40b85-199">Dichas declaraciones de especialización explícita pueden constar de una *Directiva de generación* adecuada o una implementación definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="40b85-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="40b85-200">Aquí se proporciona toda la gama de posibilidades, con los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="40b85-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="40b85-201">Declaraciones de especialización explícitas</span><span class="sxs-lookup"><span data-stu-id="40b85-201">Explicit specialization declarations</span></span>

<span data-ttu-id="40b85-202">Las operaciones de Q # pueden contener las siguientes declaraciones de especialización explícita:</span><span class="sxs-lookup"><span data-stu-id="40b85-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="40b85-203">La `body` especialización especifica la implementación de la operación sin ningún funcón aplicado.</span><span class="sxs-lookup"><span data-stu-id="40b85-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="40b85-204">La `adjoint` especialización especifica la implementación de la operación con el `Adjoint` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="40b85-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="40b85-205">La `controlled` especialización especifica la implementación de la operación con el `Controlled` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="40b85-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="40b85-206">La `controlled adjoint` especialización especifica la implementación de la operación con los dos tipos `Adjoint` y `Controlled` aplicados.</span><span class="sxs-lookup"><span data-stu-id="40b85-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="40b85-207">Esta especialización también puede denominarse `adjoint controlled` , ya que los dos funcs se desactivan.</span><span class="sxs-lookup"><span data-stu-id="40b85-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="40b85-208">Una especialización de operación consta de la etiqueta de especialización (por ejemplo `body` , o `adjoint` , etc.) seguida de una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="40b85-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="40b85-209">Una declaración explícita tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="40b85-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="40b85-210">Una *Directiva* que indica al compilador *Cómo* generar la especialización, una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="40b85-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="40b85-211">`intrinsic`, que indica que el equipo de destino proporciona la especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="40b85-212">`distribute`, que se puede usar con las `controlled` `controlled adjoint` especializaciones y.</span><span class="sxs-lookup"><span data-stu-id="40b85-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="40b85-213">Cuando se usa con `controlled` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de `body` .</span><span class="sxs-lookup"><span data-stu-id="40b85-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="40b85-214">Cuando se usa con `controlled adjoint` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la `adjoint` especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="40b85-215">`invert`, que indica que el compilador debe calcular la especialización invirtiendo `adjoint` `body` , es decir, invertir el orden de las operaciones y aplicar el objeto contiguo a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="40b85-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="40b85-216">Cuando se usa con `adjoint controlled` , esto indica que el compilador debe calcular la especialización invirtiendo la `controlled` especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="40b85-217">`self`, para indicar que la especialización contigua es igual que la `body` especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="40b85-218">Esto es válido para las `adjoint` `adjoint controlled` especializaciones y.</span><span class="sxs-lookup"><span data-stu-id="40b85-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="40b85-219">Para `adjoint controlled` , `self` implica que la `adjoint controlled` especialización es la misma que la `controlled` especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="40b85-220">`auto`, para indicar que el compilador debe seleccionar la Directiva adecuada que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="40b85-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="40b85-221">`auto`no se puede usar para la `body` especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="40b85-222">Las directivas y `auto` requieren un punto y coma de cierre `;` .</span><span class="sxs-lookup"><span data-stu-id="40b85-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="40b85-223">La `auto` Directiva se resuelve como la Directiva de generación siguiente si se proporciona una declaración explícita de `body` :</span><span class="sxs-lookup"><span data-stu-id="40b85-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="40b85-224">La `adjoint` especialización se genera de acuerdo con la directiva `invert` .</span><span class="sxs-lookup"><span data-stu-id="40b85-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="40b85-225">La `controlled` especialización se genera de acuerdo con la directiva `distribute` .</span><span class="sxs-lookup"><span data-stu-id="40b85-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="40b85-226">La `adjoint controlled` especialización se genera de acuerdo con la directiva `invert` si se proporciona una declaración explícita para `controlled` , pero no para `adjoint` , o de `distribute` lo contrario,.</span><span class="sxs-lookup"><span data-stu-id="40b85-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="40b85-227">Si una operación es autocontiguo, especifique explícitamente el o la especialización del tipo contiguo o del adyacente controlado a través de la Directiva de generación `self` para permitir que el compilador haga uso de esa información con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="40b85-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="40b85-228">Una declaración de especialización que contiene una implementación definida por el usuario consta de una tupla de argumento seguida de un bloque de instrucciones con el código de Q # que implementa la especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="40b85-229">En la lista de argumentos, `...` se usa para representar los argumentos declarados para la operación como un todo.</span><span class="sxs-lookup"><span data-stu-id="40b85-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="40b85-230">Para `body` y `adjoint` , la lista de argumentos siempre debe ser `(...)` ; para `controlled` y `adjoint controlled` , la lista de argumentos debe ser un símbolo que represente la matriz de qubits de control, seguida de `...` , entre paréntesis; por ejemplo, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="40b85-231">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="40b85-231">Examples</span></span>

<span data-ttu-id="40b85-232">Una declaración de operación podría ser tan simple como la siguiente, que define la operación Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="40b85-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="40b85-233">Tenga en cuenta que el contiguo de la operación Pauli X se define con la directiva `self` porque por definición `X` es su propio inverso.</span><span class="sxs-lookup"><span data-stu-id="40b85-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="40b85-234">El código `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas:</span><span class="sxs-lookup"><span data-stu-id="40b85-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="40b85-235">La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.</span><span class="sxs-lookup"><span data-stu-id="40b85-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="40b85-236">Implementación de especialización definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="40b85-236">User-defined specialization implementation</span></span>

<span data-ttu-id="40b85-237">Si el compilador no puede generar la implementación para una determinada especialización automáticamente, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.</span><span class="sxs-lookup"><span data-stu-id="40b85-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="40b85-238">En el ejemplo anterior, `adjoint invert;` indica que la especialización de la función contigua se va a generar invirtiendo la implementación del cuerpo e `controlled adjoint invert;` indica que la especialización contigua controlada se va a generar invirtiendo la implementación determinada de la especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="40b85-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="40b85-239">Si es necesario declarar explícitamente una o más especializaciones además del cuerpo predeterminado, la implementación del cuerpo predeterminado debe ajustarse también en una declaración de especialización adecuada:</span><span class="sxs-lookup"><span data-stu-id="40b85-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="40b85-240">Circunstancias para la definición válida de especializaciones</span><span class="sxs-lookup"><span data-stu-id="40b85-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="40b85-241">Declaraciones de operación con el o el control contiguo</span><span class="sxs-lookup"><span data-stu-id="40b85-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="40b85-242">Es válido especificar una operación sin ninguna versión contigua o controlada.</span><span class="sxs-lookup"><span data-stu-id="40b85-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="40b85-243">Por ejemplo, las operaciones de medición no tienen ninguna, porque no se pueden invertir ni controlar.</span><span class="sxs-lookup"><span data-stu-id="40b85-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="40b85-244">Una operación admite los `Adjoint` `Controlled` inactivos y/o si su declaración contiene una declaración implícita o explícita de las especializaciones respectivas.</span><span class="sxs-lookup"><span data-stu-id="40b85-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="40b85-245">Una especialización indefinida o controlada explícitamente declarada implica la existencia de una especialización con o sin control.</span><span class="sxs-lookup"><span data-stu-id="40b85-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="40b85-246">En el caso de una operación cuyo cuerpo contenga bucles de repetición hasta la ejecución correcta, instrucciones SET, medidas, instrucciones Return o llamadas a otras operaciones que no admitan el `Adjoint` functor, no es posible generar automáticamente una especialización de un método contiguo después de la `invert` `auto` Directiva o.</span><span class="sxs-lookup"><span data-stu-id="40b85-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="40b85-247">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no admitan el `Controlled` functor, la generación automática de una especialización controlada después de la `distribute` `auto` Directiva o no es posible.</span><span class="sxs-lookup"><span data-stu-id="40b85-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="40b85-248">Contiguo controlado</span><span class="sxs-lookup"><span data-stu-id="40b85-248">Controlled Adjoint</span></span>

<span data-ttu-id="40b85-249">La versión de la contigua controlada de una operación especifica cómo se implementa una versión controlada por Quantum del método contiguo de la operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="40b85-250">Es válido especificar una operación sin ninguna versión contigua controlada; por ejemplo, las operaciones de medición no tienen ninguna versión contigua controlada porque no se pueden controlar ni invertir.</span><span class="sxs-lookup"><span data-stu-id="40b85-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="40b85-251">Es necesario que exista una especialización del mismo bajo controlada para una operación si y solo si hay un Join y una especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="40b85-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="40b85-252">En ese caso, se infiere la existencia de la especialización contigua controlada y el compilador genera una especialización adecuada si no se ha definido explícitamente ninguna implementación.</span><span class="sxs-lookup"><span data-stu-id="40b85-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="40b85-253">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no tienen una versión de la función contigua controlada, la generación automática de una especialización de un método contiguo después de la `invert` `distribute` Directiva, o `auto` no es posible.</span><span class="sxs-lookup"><span data-stu-id="40b85-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="40b85-254">Compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="40b85-254">Type Compatibility</span></span>

<span data-ttu-id="40b85-255">Se puede usar una operación con funciones de compatibilidad adicionales que admitan en cualquier lugar una operación con menos inactivos, pero se espera la misma firma.</span><span class="sxs-lookup"><span data-stu-id="40b85-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="40b85-256">Por ejemplo, se puede usar una operación de tipo `(Qubit => Unit is Adj)` en cualquier lugar donde se espere una operación de tipo `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="40b85-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="40b85-257">Q # es *covariante* con respecto a los tipos de valor devueltos a los que se puede llamar: una invocable que devuelve un tipo `'A` es compatible con una que se puede llamar con el mismo tipo de entrada y un tipo de resultado `'A` compatible con.</span><span class="sxs-lookup"><span data-stu-id="40b85-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="40b85-258">Q # es *contravariante* con respecto a los tipos de entrada: una invocable que toma un tipo `'A` como entrada es compatible con una operación invocable con el mismo tipo de resultado y un tipo de entrada compatible con `'A` .</span><span class="sxs-lookup"><span data-stu-id="40b85-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="40b85-259">Es decir, dadas las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="40b85-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="40b85-260">lo siguiente es cierto:</span><span class="sxs-lookup"><span data-stu-id="40b85-260">the following are true:</span></span>

- <span data-ttu-id="40b85-261">La función `ConjugateInvertWith` se puede invocar con un `inner` argumento de `Invert` o `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="40b85-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="40b85-262">La función `ConjugateUnitaryWith` se puede invocar con un `inner` argumento de `ApplyUnitary` , pero no `Invert` .</span><span class="sxs-lookup"><span data-stu-id="40b85-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="40b85-263">Un valor de tipo `(Qubit[] => Unit is Adj + Ctl)` se puede devolver desde `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="40b85-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40b85-264">P # 0,3 presentó una diferencia significativa en el comportamiento de los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="40b85-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="40b85-265">Los tipos definidos por el usuario se tratan como una versión ajustada del tipo subyacente, en lugar de como un subtipo.</span><span class="sxs-lookup"><span data-stu-id="40b85-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="40b85-266">Esto significa que un valor de un tipo definido por el usuario no se puede usar cuando se espera un valor del tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="40b85-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="40b85-267">Conjugaciones</span><span class="sxs-lookup"><span data-stu-id="40b85-267">Conjugations</span></span>

<span data-ttu-id="40b85-268">A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito.</span><span class="sxs-lookup"><span data-stu-id="40b85-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="40b85-269">Esto puede evitarse al "deshacer" correctamente los cálculos realizados antes de liberar la memoria.</span><span class="sxs-lookup"><span data-stu-id="40b85-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="40b85-270">Un patrón común en la informática Quantum es, por lo tanto, lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="40b85-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="40b85-271">A partir de la versión 0,9, se admite una instrucción de conjugación que implementa la transformación anterior.</span><span class="sxs-lookup"><span data-stu-id="40b85-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="40b85-272">Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="40b85-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="40b85-273">Obviamente, este tipo de declaración es mucho más útil si la transformación externa e interna no está disponible como operaciones, pero en su lugar es más conveniente describirla mediante un bloque que consta de varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="40b85-274">El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply.</span><span class="sxs-lookup"><span data-stu-id="40b85-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="40b85-275">Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de.</span><span class="sxs-lookup"><span data-stu-id="40b85-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="40b85-276">Definir nuevas funciones</span><span class="sxs-lookup"><span data-stu-id="40b85-276">Defining New Functions</span></span>

<span data-ttu-id="40b85-277">Las funciones son rutinas puramente deterministas en Q #, que son distintas de las operaciones en que no se les permite tener ningún efecto más allá del cálculo de un valor de salida.</span><span class="sxs-lookup"><span data-stu-id="40b85-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="40b85-278">En concreto, las funciones no pueden llamar a las operaciones; actuar sobre, asignar o tomar prestado qubits; números aleatorios de muestra; o, en caso contrario, dependen del estado más allá del valor de entrada de una función.</span><span class="sxs-lookup"><span data-stu-id="40b85-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="40b85-279">Como consecuencia, las funciones Q # son *puras*, ya que siempre asignan los mismos valores de entrada a los mismos valores de salida.</span><span class="sxs-lookup"><span data-stu-id="40b85-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="40b85-280">Esto permite que el compilador de preguntas # reordene de forma segura cómo y cuándo se llama a las funciones al generar especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="40b85-281">Cada archivo de código fuente de Q # puede definir cualquier número de funciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="40b85-282">Los nombres de función deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación o tipo.</span><span class="sxs-lookup"><span data-stu-id="40b85-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="40b85-283">La definición de una función funciona de forma similar a la definición de una operación, con la excepción de que no se puede definir ninguna especialización contigua o controlada para una función.</span><span class="sxs-lookup"><span data-stu-id="40b85-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="40b85-284">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="40b85-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="40b85-285">o</span><span class="sxs-lookup"><span data-stu-id="40b85-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="40b85-286">Lógica clásica en functions = = Good</span><span class="sxs-lookup"><span data-stu-id="40b85-286">Classical logic in functions == good</span></span>

<span data-ttu-id="40b85-287">Siempre que sea posible hacerlo, resulta útil escribir una lógica clásica en términos de funciones en lugar de operaciones, de modo que se pueda utilizar más fácilmente desde las operaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="40b85-288">Por ejemplo, si se hubiera escrito la `Square` declaración anterior como una *operación*, el compilador no habría podido garantizar que la llamada a ella con la misma entrada produciría sistemáticamente los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="40b85-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="40b85-289">Para subrayar la diferencia entre las funciones y las operaciones, tenga en cuenta el problema de realizar un muestreo de forma de un número aleatorio en una operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="40b85-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="40b85-290">Cada vez que `U` se llama a, tendrá una acción diferente en `target` .</span><span class="sxs-lookup"><span data-stu-id="40b85-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="40b85-291">En concreto, el compilador no puede garantizar que si se agrega una `adjoint auto` declaración de especialización a `U` , `U(target); Adjoint U(target);` actuará como identidad (es decir, como una operación no operativa).</span><span class="sxs-lookup"><span data-stu-id="40b85-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="40b85-292">Esto infringe la definición del método contiguo que vimos en [vectores y matrices](xref:microsoft.quantum.concepts.vectors), de modo que permitir la generación automática de una especialización de tipo contiguo en una operación en la que se ha llamado a la operación <xref:microsoft.quantum.math.randomreal> interrumpiría las garantías proporcionadas por el compilador; <xref:microsoft.quantum.math.randomreal> es una operación para la que no existe ninguna versión contigua o controlada.</span><span class="sxs-lookup"><span data-stu-id="40b85-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="40b85-293">Por otro lado, permitir llamadas a funciones como `Square` es seguro, en el que el compilador puede estar seguro de que solo necesita conservar la entrada `Square` en para mantener su salida estable.</span><span class="sxs-lookup"><span data-stu-id="40b85-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="40b85-294">Por lo tanto, el aislamiento de la lógica más clásica posible en las funciones facilita la reutilización de esa lógica en otras funciones y operaciones similares.</span><span class="sxs-lookup"><span data-stu-id="40b85-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="40b85-295">Llamadas genéricas (con parámetros de tipo)</span><span class="sxs-lookup"><span data-stu-id="40b85-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="40b85-296">Muchas funciones y operaciones que podríamos querer definir no se basan en gran medida en los tipos de sus entradas, sino que solo usan implícitamente sus tipos a través de otra función u operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="40b85-297">Por ejemplo, considere el concepto de *mapa* común a muchos idiomas funcionales; dada una función $f (x) $ y una colección de valores $ \{ x_1, x_2, \dots, x_n \} $, Map devuelve una nueva colección $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="40b85-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="40b85-298">Para implementar esto en Q #, podemos aprovechar las ventajas de que las funciones son de primera clase.</span><span class="sxs-lookup"><span data-stu-id="40b85-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="40b85-299">Vamos a escribir un ejemplo rápido de `Map` , usando ★ como un marcador de posición mientras averiguamos qué tipos necesitamos.</span><span class="sxs-lookup"><span data-stu-id="40b85-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="40b85-300">Tenga en cuenta que esta función tiene un aspecto muy similar al de los tipos reales que se sustituyen en.</span><span class="sxs-lookup"><span data-stu-id="40b85-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="40b85-301">Una asignación de enteros a Paulis, por ejemplo, se parece mucho a una asignación de números de punto flotante a cadenas:</span><span class="sxs-lookup"><span data-stu-id="40b85-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="40b85-302">En principio, podríamos escribir una versión de `Map` para cada par de tipos que encontramos, pero esto presenta una serie de dificultades.</span><span class="sxs-lookup"><span data-stu-id="40b85-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="40b85-303">Por ejemplo, si encontramos un error en `Map` , debemos asegurarnos de que la corrección se aplique uniformemente en todas las versiones de `Map` .</span><span class="sxs-lookup"><span data-stu-id="40b85-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="40b85-304">Además, si creamos una nueva tupla o UDT, ahora debemos crear también un nuevo `Map` para ir junto con el nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="40b85-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="40b85-305">Aunque esto es tractable para un número pequeño de estas funciones, a medida que recopilamos más funciones de la misma forma que `Map` , el costo de introducir nuevos tipos se vuelve injustificable en un orden bastante corto.</span><span class="sxs-lookup"><span data-stu-id="40b85-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="40b85-306">Sin embargo, gran parte de este problema se debe a que no se ha proporcionado al compilador la información necesaria para reconocer cómo se relacionan las distintas versiones de `Map` .</span><span class="sxs-lookup"><span data-stu-id="40b85-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="40b85-307">En efecto, queremos que el compilador trate `Map` como algún tipo de función matemática de *tipos* q # a funciones q #.</span><span class="sxs-lookup"><span data-stu-id="40b85-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="40b85-308">Esta noción se formaliza permitiendo que las funciones y las operaciones tengan *parámetros de tipo*, así como sus parámetros de tupla normales.</span><span class="sxs-lookup"><span data-stu-id="40b85-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="40b85-309">En los ejemplos anteriores, deseamos pensar en que `Map` tiene parámetros de tipo `Int, Pauli` en el primer caso y `Double, String` en el segundo caso.</span><span class="sxs-lookup"><span data-stu-id="40b85-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="40b85-310">En su mayor parte, estos parámetros de tipo se pueden usar como si fueran tipos normales: usamos valores de parámetros de tipo para crear matrices y tuplas, llamar a funciones y operaciones, y asignar a variables ordinarias o mutables.</span><span class="sxs-lookup"><span data-stu-id="40b85-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="40b85-311">El caso más extremo de dependencia indirecta es el de qubits, donde un programa de Q # no puede confiar directamente en la estructura del `Qubit` tipo, sino que **debe** pasar estos tipos a otras operaciones y funciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="40b85-312">Volviendo al ejemplo anterior, podemos ver que necesitamos `Map` tener parámetros de tipo, uno para representar la entrada `fn` y otro para representar la salida de `fn` .</span><span class="sxs-lookup"><span data-stu-id="40b85-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="40b85-313">En Q #, esto se escribe agregando corchetes angulares (es decir `<>` , no frenos $ \braket {} $!) después del nombre de una función u operación en su declaración y enumerando cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="40b85-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="40b85-314">El nombre de cada parámetro de tipo debe empezar con un paso `'` , lo que indica que se trata de un parámetro de tipo y no de un tipo ordinario (también conocido como tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="40b85-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="40b85-315">Para `Map` , por lo tanto, escribimos:</span><span class="sxs-lookup"><span data-stu-id="40b85-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="40b85-316">Tenga en cuenta que la definición de `Map<'Input, 'Output>` es muy similar a las versiones que escribimos antes.</span><span class="sxs-lookup"><span data-stu-id="40b85-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="40b85-317">La única diferencia es que hemos informado explícitamente al compilador que `Map` no depende directamente de lo que `'Input` y `'Output` son, pero funciona para dos tipos mediante el uso indirecto a través de `fn` .</span><span class="sxs-lookup"><span data-stu-id="40b85-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="40b85-318">Una vez que hemos definido `Map<'Input, 'Output>` de esta manera, podemos llamarlo como si fuera una función ordinaria:</span><span class="sxs-lookup"><span data-stu-id="40b85-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="40b85-319">La escritura de funciones y operaciones genéricas es un lugar donde "tupla en tupla" es una forma muy útil de pensar en las funciones y operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="40b85-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="40b85-320">Dado que cada función toma exactamente una entrada y devuelve exactamente una salida, una entrada de tipo `'T -> 'U` coincide con *cualquier* función de Q #.</span><span class="sxs-lookup"><span data-stu-id="40b85-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="40b85-321">De igual forma, cualquier operación se puede pasar a una entrada de tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="40b85-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="40b85-322">Como segundo ejemplo, considere el reto de escribir una función que devuelva la composición de otras dos funciones:</span><span class="sxs-lookup"><span data-stu-id="40b85-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="40b85-323">Aquí, debemos especificar exactamente qué `A` , `B` y `C` son, por lo que limitan gravemente la utilidad de la nueva `Compose` función.</span><span class="sxs-lookup"><span data-stu-id="40b85-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="40b85-324">Después de todo, `Compose` solo depende de `A` , `B` y `C` *a través* de `innerFn` y `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="40b85-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="40b85-325">Como alternativa, se pueden agregar parámetros de tipo a `Compose` que indiquen que funciona para *cualquier* `A` , `B` y `C` , siempre y cuando estos parámetros coincidan con los esperados por `innerFn` y `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="40b85-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="40b85-326">Las bibliotecas de preguntas # estándar proporcionan una gama de funciones y operaciones parametrizadas de tipo para facilitar la rápida creación de un flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="40b85-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="40b85-327">Estos se describen con más detalle en la guía de la [biblioteca estándar de preguntas y respuestas](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="40b85-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="40b85-328">Se puede llamar como valores de primera clase</span><span class="sxs-lookup"><span data-stu-id="40b85-328">Callables as First-Class Values</span></span>

<span data-ttu-id="40b85-329">Una técnica crítica para el razonamiento sobre el flujo de control y la lógica clásica con funciones en lugar de operaciones es usar las operaciones y las funciones de Q # como *primera clase*.</span><span class="sxs-lookup"><span data-stu-id="40b85-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="40b85-330">Es decir, cada uno de los valores del lenguaje se encuentra en su propio derecho.</span><span class="sxs-lookup"><span data-stu-id="40b85-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="40b85-331">Por ejemplo, lo siguiente es código de Q # perfectamente válido, si un poco indirecto:</span><span class="sxs-lookup"><span data-stu-id="40b85-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="40b85-332">El valor de la variable `ourH` en el fragmento de código anterior es la operación <xref:microsoft.quantum.intrinsic.h> , de modo que se puede llamar a ese valor como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="40b85-333">Esto nos permite escribir operaciones que tomen las operaciones como parte de su entrada, formando conceptos de flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="40b85-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="40b85-334">Por ejemplo, podríamos imaginar que quiere "cuadrado" una operación aplicándole dos veces en el mismo qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="40b85-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="40b85-335">Devolver operaciones desde una función</span><span class="sxs-lookup"><span data-stu-id="40b85-335">Returning operations from a function</span></span>

<span data-ttu-id="40b85-336">Hacemos hincapié en que también podemos devolver operaciones como parte de las salidas, de modo que podamos aislar algunos tipos de lógica condicional clásica como una función clásica que devuelve una descripción de un programa Quantum en forma de una operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="40b85-337">Como ejemplo sencillo, considere el ejemplo de teleportabilidad, en el que la entidad que recibe un mensaje clásico de dos bits debe usar el mensaje para descodificar sus qubit en el estado de telepuerto adecuado.</span><span class="sxs-lookup"><span data-stu-id="40b85-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="40b85-338">Podríamos escribir esto en términos de una función que toma esos dos bits clásico y devuelve la operación de descodificación adecuada.</span><span class="sxs-lookup"><span data-stu-id="40b85-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="40b85-339">Esta nueva función es realmente una función, en el caso de que se llame con los mismos valores de `hereBit` y `thereBit` , siempre se devolverá la misma operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="40b85-340">Por lo tanto, el descodificador se puede ejecutar de forma segura dentro de las operaciones sin tener que preocuparse de cómo la lógica de descodificación interactúa con las definiciones de las distintas especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="40b85-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="40b85-341">Es decir, hemos aislado la lógica clásica dentro de una función, garantizando al compilador que la llamada a la función se puede reordenar con Impunity, siempre y cuando se conserve la entrada.</span><span class="sxs-lookup"><span data-stu-id="40b85-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="40b85-342">Aplicación parcial</span><span class="sxs-lookup"><span data-stu-id="40b85-342">Partial Application</span></span>

<span data-ttu-id="40b85-343">Podemos hacer mucho más con funciones que devuelven operaciones mediante el uso de una *aplicación parcial*, en la que podemos proporcionar una o más partes de la entrada a una función u operación sin llamarla realmente.</span><span class="sxs-lookup"><span data-stu-id="40b85-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="40b85-344">Por ejemplo, al volver a llamar al `ApplyTwice` ejemplo anterior, se puede indicar que no queremos especificar, de inmediato, a qué qubit se debe aplicar la operación de entrada:</span><span class="sxs-lookup"><span data-stu-id="40b85-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="40b85-345">En este caso, la variable local `twiceOp` contiene la operación parcialmente aplicada `ApplyTwice(op, _)` , donde se indican las partes de la entrada que todavía no se han especificado `_` .</span><span class="sxs-lookup"><span data-stu-id="40b85-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="40b85-346">Cuando realmente llamamos a `twiceOp` en la línea siguiente, pasamos como entrada a la operación parcialmente aplicada todas las partes restantes de la entrada a la operación original.</span><span class="sxs-lookup"><span data-stu-id="40b85-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="40b85-347">Por lo tanto, el fragmento de código anterior es realmente idéntico a haber llamado `ApplyTwice(op, target)` directamente a y se guarda para que se haya introducido una nueva variable local que nos permita retrasar la llamada mientras se proporcionan algunas partes de la entrada.</span><span class="sxs-lookup"><span data-stu-id="40b85-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="40b85-348">Dado que una operación que se ha aplicado parcialmente no se llama realmente hasta que se ha proporcionado toda la entrada, podemos aplicar de forma segura las operaciones, incluso desde las funciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="40b85-349">En principio, la lógica clásica dentro de `SquareOperation` podría haber sido mucho más complicada, pero sigue estando aislada del resto de una operación mediante la garantía de que el compilador puede ofrecer sobre las funciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="40b85-350">Este enfoque se usará en toda la biblioteca de preguntas y respuestas para expresar el flujo de control clásico de manera que se pueda usar fácilmente dentro de los programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="40b85-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="40b85-351">Recursividad</span><span class="sxs-lookup"><span data-stu-id="40b85-351">Recursion</span></span>

<span data-ttu-id="40b85-352">Se permite que las llamadas a Q # sean recursivas directa o indirectamente.</span><span class="sxs-lookup"><span data-stu-id="40b85-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="40b85-353">Es decir, una operación o función se puede llamar a sí misma, o puede llamar a otra llamada invocable que llama directa o indirectamente a la operación que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="40b85-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="40b85-354">Sin embargo, hay dos comentarios importantes sobre el uso de la recursividad:</span><span class="sxs-lookup"><span data-stu-id="40b85-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="40b85-355">Es probable que el uso de la recursividad en las operaciones interfiera con ciertas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="40b85-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="40b85-356">Esto puede tener un impacto considerable en el tiempo de ejecución del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="40b85-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="40b85-357">Cuando se ejecuta en un dispositivo Quantum real, el espacio de pila puede estar limitado y, por tanto, la recursividad profunda puede provocar un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40b85-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="40b85-358">En concreto, el compilador y el tiempo de ejecución de Q # no identifican y optimizan la recursividad del final.</span><span class="sxs-lookup"><span data-stu-id="40b85-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="whats-next"></a><span data-ttu-id="40b85-359">¿Qué debe hacer a continuación?</span><span class="sxs-lookup"><span data-stu-id="40b85-359">What's Next?</span></span>
<span data-ttu-id="40b85-360">Obtenga información sobre [las variables](xref:microsoft.quantum.guide.variables) en preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="40b85-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>