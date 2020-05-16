---
title: Trabajo con qubits
description: Descripción de relleno
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430941"
---
# <a name="working-with-qubits"></a><span data-ttu-id="8b7de-103">Trabajo con qubits</span><span class="sxs-lookup"><span data-stu-id="8b7de-103">Working with qubits</span></span>

<span data-ttu-id="8b7de-104">Teniendo en cuenta que ahora hay una variedad de diferentes partes del lenguaje de preguntas y respuestas, vamos a profundizar en ella y veremos cómo usar qubits.</span><span class="sxs-lookup"><span data-stu-id="8b7de-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="8b7de-105">Tenga en cuenta que ninguna de estas instrucciones está permitida dentro del cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="8b7de-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="8b7de-106">Solo son válidos dentro de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="8b7de-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="8b7de-107">Asignar qubits</span><span class="sxs-lookup"><span data-stu-id="8b7de-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="8b7de-108">Limpiar qubits</span><span class="sxs-lookup"><span data-stu-id="8b7de-108">Clean qubits</span></span>

<span data-ttu-id="8b7de-109">La `using` instrucción se usa para *asignar* nuevos qubits para su uso durante un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8b7de-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="8b7de-110">La instrucción consta de la palabra clave `using` , seguida de un paréntesis de apertura `(` , un enlace, un paréntesis de cierre `)` y el bloque de instrucciones en el que estará disponible el qubits.</span><span class="sxs-lookup"><span data-stu-id="8b7de-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="8b7de-111">El enlace sigue el mismo patrón que las `let` instrucciones: un solo símbolo o una tupla de símbolos, seguido de un signo igual `=` y un solo valor o una tupla coincidente de *inicializadores*.</span><span class="sxs-lookup"><span data-stu-id="8b7de-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="8b7de-112">Los inicializadores están disponibles para un único qubit, indicado como `Qubit()` , o una matriz de qubits, `Qubit[n]` , donde `n` es una `Int` expresión.</span><span class="sxs-lookup"><span data-stu-id="8b7de-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="8b7de-113">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="8b7de-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="8b7de-114">Los qubits asignados de esta manera se inician en el {0} Estado $ \ket $; en el ejemplo anterior, `register` es así en el estado $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8b7de-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="8b7de-115">Al final del `using` bloque, cualquier qubits asignado por ese bloque se desasigna inmediatamente y no se puede usar más.</span><span class="sxs-lookup"><span data-stu-id="8b7de-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="8b7de-116">Los equipos de destino esperan que los qubits se encuentren en el estado $ \ket {0} $ inmediatamente antes de la desasignación, de modo que se puedan volver a usar y ofrecer a otros `using` bloques para su asignación.</span><span class="sxs-lookup"><span data-stu-id="8b7de-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="8b7de-117">Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8b7de-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="8b7de-118">Si es necesario, la @"microsoft.quantum.intrinsic.reset" operación se puede usar para medir un qubit en su lugar y para usar ese resultado de medida para asegurarse de que el qubit medido se devuelve a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8b7de-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="8b7de-119">Dicha medida destruirá cualquier inenredo con el resto de qubits y, por tanto, puede afectar al cálculo.</span><span class="sxs-lookup"><span data-stu-id="8b7de-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="8b7de-120">Qubits prestado</span><span class="sxs-lookup"><span data-stu-id="8b7de-120">Borrowed Qubits</span></span>

<span data-ttu-id="8b7de-121">La `borrowing` instrucción se usa para hacer que qubits esté disponible para uso temporal, que no es necesario que esté en un estado específico.</span><span class="sxs-lookup"><span data-stu-id="8b7de-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="8b7de-122">El mecanismo de préstamos permite la asignación de qubits que se puede usar como espacio de desecho durante un cálculo.</span><span class="sxs-lookup"><span data-stu-id="8b7de-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="8b7de-123">Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8b7de-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="8b7de-124">A menudo se hace referencia a ellos como "sucios" qubits porque su estado es desconocido e incluso pueden estar inscritos con otras partes de la memoria del equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="8b7de-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="8b7de-125">El enlace sigue el mismo patrón y las mismas reglas que el de una `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8b7de-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="8b7de-126">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="8b7de-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="8b7de-127">Los qubits prestados se encuentran en un estado desconocido y salen del ámbito al final del bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8b7de-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="8b7de-128">El prestatario se compromete a mantener el qubits en el mismo estado en que se encontraban cuando se prestó, es decir, su estado al principio y al final del bloque de instrucciones se espera que sea el mismo.</span><span class="sxs-lookup"><span data-stu-id="8b7de-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="8b7de-129">En concreto, este estado no es necesariamente un estado clásico, de modo que en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas.</span><span class="sxs-lookup"><span data-stu-id="8b7de-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="8b7de-130">Al tomar prestado qubits, el sistema intentará en primer lugar rellenar la solicitud de qubits en uso, pero no se podrá acceder a ella durante el cuerpo de la `borrowing` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8b7de-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="8b7de-131">Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8b7de-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="8b7de-132">Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.</span><span class="sxs-lookup"><span data-stu-id="8b7de-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="8b7de-133">Vea el [ejemplo de qubits de préstamos](#borrowing-qubits-example) que se muestra a continuación para ver un ejemplo de su uso en Q # o la factorización del papel que [*usa 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para un algoritmo que utiliza qubits prestado.</span><span class="sxs-lookup"><span data-stu-id="8b7de-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="8b7de-134">Operaciones intrínsecas</span><span class="sxs-lookup"><span data-stu-id="8b7de-134">Intrinsic Operations</span></span>

<span data-ttu-id="8b7de-135">Una vez asignado, una qubit se puede pasar a las funciones y operaciones.</span><span class="sxs-lookup"><span data-stu-id="8b7de-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="8b7de-136">En cierto sentido, esto es todo lo que puede hacer un programa de Q # con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="8b7de-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="8b7de-137">Veremos estas operaciones con más detalle en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), pero por ahora se mencionan algunas operaciones útiles que se pueden usar para interactuar con qubits.</span><span class="sxs-lookup"><span data-stu-id="8b7de-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="8b7de-138">En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q # mediante las operaciones intrínsecas `X` , `Y` y `Z` , cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="8b7de-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="8b7de-139">Como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ y `X` , por lo tanto, como una operación de volteo de bits o no como una puerta.</span><span class="sxs-lookup"><span data-stu-id="8b7de-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="8b7de-140">La `X` operación nos permite preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:</span><span class="sxs-lookup"><span data-stu-id="8b7de-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="8b7de-141">Más adelante, veremos formas más compactas de escribir esta operación que no requieren el control de flujo manual.</span><span class="sxs-lookup"><span data-stu-id="8b7de-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="8b7de-142">También podemos preparar estados como $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ y $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ mediante {2} la transformación Hadamard $H $, que está representada en Q # por la operación intrínseca `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="8b7de-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="8b7de-143">Medidas</span><span class="sxs-lookup"><span data-stu-id="8b7de-143">Measurements</span></span>

<span data-ttu-id="8b7de-144">Mediante la `Measure` operación, que es una operación intrínseca no unitario integrada, podemos extraer información clásica de un objeto de tipo `Qubit` y asignar un valor clásico como resultado, que tiene un tipo reservado `Result` , que indica que el resultado ya no es un estado de Quantum.</span><span class="sxs-lookup"><span data-stu-id="8b7de-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="8b7de-145">La entrada de `Measure` es un eje Pauli en la esfera Bloch, representada por un valor de tipo `Pauli` (por ejemplo, `PauliX` ) y un valor de tipo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="8b7de-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="8b7de-146">Un ejemplo sencillo es la siguiente operación, que asigna una qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="8b7de-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="8b7de-147">La siguiente operación proporciona un ejemplo ligeramente más complicado, que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` están en el estado cero cuando se miden en una base de Pauli especificada y, de `false` lo contrario, devuelve.</span><span class="sxs-lookup"><span data-stu-id="8b7de-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

## <a name="borrowing-qubits-example"></a><span data-ttu-id="8b7de-148">Ejemplo de qubits de préstamos</span><span class="sxs-lookup"><span data-stu-id="8b7de-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="8b7de-149">En Canon hay ejemplos que usan la `borrowing` palabra clave, por ejemplo, la función que se `MultiControlledXBorrow` define a continuación.</span><span class="sxs-lookup"><span data-stu-id="8b7de-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="8b7de-150">Si `controls` denota el qubits de control que se debe agregar a una `X` operación, `Length(controls)-2` esta implementación agregará un total de muchos ancillas modificados.</span><span class="sxs-lookup"><span data-stu-id="8b7de-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="8b7de-151">Tenga en cuenta que el uso extensivo del `With` combinador---en su forma que es aplicable a las operaciones que admiten el modo contiguo, es decir, `WithA` ---se realizó en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8b7de-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="8b7de-152">Este es un buen estilo de programación, ya que agregar el control a las estructuras que implican `With` propaga el control únicamente a la operación interna.</span><span class="sxs-lookup"><span data-stu-id="8b7de-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="8b7de-153">Además, tenga en cuenta que aquí, además de la `body` de la operación, `controlled` se proporcionó explícitamente una implementación del cuerpo de la operación, en lugar de recurrir a una `controlled auto` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8b7de-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="8b7de-154">La razón es que sabemos de la estructura del circuito cómo agregar fácilmente más controles, lo que es beneficioso en comparación con la adición de control a cada una de las puertas individuales de `body` .</span><span class="sxs-lookup"><span data-stu-id="8b7de-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="8b7de-155">Es instructivo comparar este código con otra función `MultiControlledXClean` de Canon que logre el mismo objetivo de implementar una operación controlada por multiplicación `X` , sin embargo, que usa varios qubits limpios mediante el `using` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="8b7de-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="8b7de-156">¿Qué debe hacer a continuación?</span><span class="sxs-lookup"><span data-stu-id="8b7de-156">What's Next?</span></span>
<span data-ttu-id="8b7de-157">Obtenga información sobre el [flujo de control](xref:microsoft.quantum.guide.controlflow) en Q #.</span><span class="sxs-lookup"><span data-stu-id="8b7de-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>