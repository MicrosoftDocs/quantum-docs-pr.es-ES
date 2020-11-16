---
title: Trabajo con qubits
description: 'Más información sobre cómo trabajar con qubits en Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 9a3d7e03016332a04ac9d1610428b6fcd546d1f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691577"
---
# <a name="working-with-qubits"></a><span data-ttu-id="61fe8-103">Trabajo con qubits</span><span class="sxs-lookup"><span data-stu-id="61fe8-103">Working with qubits</span></span>

<span data-ttu-id="61fe8-104">Qubits son el objeto fundamental de la información en la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="61fe8-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="61fe8-105">Para obtener una introducción general a qubits, consulte [Descripción de Quantum Computing](xref:microsoft.quantum.overview.understanding)y para profundizar más en su representación matemática, vea [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="61fe8-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="61fe8-106">En este artículo se explica cómo usar qubits en un Q# programa.</span><span class="sxs-lookup"><span data-stu-id="61fe8-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="61fe8-107">Ninguna de las instrucciones que se describen en este artículo son válidas dentro del cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="61fe8-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="61fe8-108">Solo son válidos dentro de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="61fe8-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="61fe8-109">Asignar qubits</span><span class="sxs-lookup"><span data-stu-id="61fe8-109">Allocating Qubits</span></span>

<span data-ttu-id="61fe8-110">Dado que los qubits físicos son recursos valiosos en un equipo Quantum, parte del trabajo del compilador es asegurarse de que se usan de la forma más eficaz posible.</span><span class="sxs-lookup"><span data-stu-id="61fe8-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="61fe8-111">Como tal, debe indicar a que Q# *asigne* qubits para su uso dentro de un bloque de instrucciones determinado.</span><span class="sxs-lookup"><span data-stu-id="61fe8-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="61fe8-112">Puede asignar qubits como un qubit único o como una matriz de qubits, que se conoce como *registro* .</span><span class="sxs-lookup"><span data-stu-id="61fe8-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register* .</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="61fe8-113">Limpiar qubits</span><span class="sxs-lookup"><span data-stu-id="61fe8-113">Clean qubits</span></span>

<span data-ttu-id="61fe8-114">Use la `using` instrucción para asignar nuevos qubits para su uso durante un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="61fe8-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="61fe8-115">La instrucción consta de la palabra clave `using` , seguida de un enlace entre paréntesis `( )` y el bloque de instrucciones en el que están disponibles los qubits.</span><span class="sxs-lookup"><span data-stu-id="61fe8-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="61fe8-116">El enlace sigue el mismo patrón que las `let` instrucciones: un solo símbolo o una tupla de símbolos, seguido de un signo igual `=` y un solo valor o una tupla coincidente de *inicializadores* .</span><span class="sxs-lookup"><span data-stu-id="61fe8-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers* .</span></span>

<span data-ttu-id="61fe8-117">Los inicializadores están disponibles para un único qubit, indicado como `Qubit()` , o una matriz de qubits, `Qubit[n]` , donde `n` es una `Int` expresión.</span><span class="sxs-lookup"><span data-stu-id="61fe8-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="61fe8-118">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="61fe8-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="61fe8-119">Cualquier qubits asignado de este modo se inicia en el estado $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="61fe8-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="61fe8-120">Por lo tanto, en el ejemplo anterior, `auxiliary` es un único qubit en el estado $ \ket {0} $ y `register` está en el estado de cinco qubit $ \ket {00000} = \ket \otimes \ket \otimes {0} {0} \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="61fe8-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="61fe8-121">Al final del `using` bloque, cualquier qubits asignado por ese bloque se desasigna inmediatamente y no se puede usar más.</span><span class="sxs-lookup"><span data-stu-id="61fe8-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="61fe8-122">Los equipos de destino pueden reutilizar qubits desasignadas y ofrecerlas a otros `using` bloques para su asignación.</span><span class="sxs-lookup"><span data-stu-id="61fe8-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="61fe8-123">Como tal, el equipo de destino espera que qubits se encuentren en el {0} Estado $ \ket $ inmediatamente antes de la desasignación.</span><span class="sxs-lookup"><span data-stu-id="61fe8-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="61fe8-124">Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="61fe8-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="61fe8-125">Si es necesario, puede usar la @"microsoft.quantum.intrinsic.reset" operación, que devuelve qubit a $ \ket {0} $ mediante la medición y la realización condicional de una operación basada en el resultado.</span><span class="sxs-lookup"><span data-stu-id="61fe8-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="61fe8-126">Esta medida destruye cualquier inenredo con el Qubits restante y, por tanto, puede afectar al cálculo.</span><span class="sxs-lookup"><span data-stu-id="61fe8-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="61fe8-127">Qubits prestado</span><span class="sxs-lookup"><span data-stu-id="61fe8-127">Borrowed Qubits</span></span>

<span data-ttu-id="61fe8-128">Use la `borrowing` instrucción para asignar qubits para uso temporal, que no tienen que estar en un estado específico.</span><span class="sxs-lookup"><span data-stu-id="61fe8-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="61fe8-129">Puede usar qubits prestado como espacio de desecho durante un cálculo.</span><span class="sxs-lookup"><span data-stu-id="61fe8-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="61fe8-130">Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="61fe8-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="61fe8-131">A menudo se hace referencia a ellos como "sucios" qubits porque su estado es desconocido e incluso pueden estar inscritos con otras partes de la memoria del equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="61fe8-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="61fe8-132">El enlace sigue el mismo patrón y las mismas reglas que la `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="61fe8-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="61fe8-133">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="61fe8-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="61fe8-134">Los qubits prestados se encuentran en un estado desconocido y salen del ámbito al final del bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="61fe8-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="61fe8-135">El prestatario confirma que se abandone el qubits en el mismo estado en que se encontraban cuando los prestó. es decir, su estado al principio y al final del bloque de instrucciones debe ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="61fe8-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="61fe8-136">Dado que este estado no es necesariamente un estado clásico, en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas.</span><span class="sxs-lookup"><span data-stu-id="61fe8-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="61fe8-137">Al tomar prestado qubits, el sistema primero intenta rellenar la solicitud de qubits que se están usando pero no se puede tener acceso a ella durante el cuerpo de la `borrowing` instrucción.</span><span class="sxs-lookup"><span data-stu-id="61fe8-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="61fe8-138">Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="61fe8-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="61fe8-139">Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.</span><span class="sxs-lookup"><span data-stu-id="61fe8-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="61fe8-140">Para ver un ejemplo de su uso en Q# , consulte el [ejemplo de qubits de préstamos](#borrowing-qubits-example) de este artículo, o la factorización de papel que [*usa 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para un algoritmo que utiliza qubits prestado.</span><span class="sxs-lookup"><span data-stu-id="61fe8-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="61fe8-141">Operaciones intrínsecas</span><span class="sxs-lookup"><span data-stu-id="61fe8-141">Intrinsic Operations</span></span>

<span data-ttu-id="61fe8-142">Una vez asignada, puede pasar un qubit a las funciones y operaciones.</span><span class="sxs-lookup"><span data-stu-id="61fe8-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="61fe8-143">En cierto sentido, esto es todo lo que un Q# programa puede hacer con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="61fe8-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="61fe8-144">En este artículo se describen algunas Q# operaciones útiles que puede usar para interactuar con qubits.</span><span class="sxs-lookup"><span data-stu-id="61fe8-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="61fe8-145">Para obtener más información sobre estos y otros, consulte [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="61fe8-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="61fe8-146">En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q# mediante las operaciones intrínsecas [`X`](xref:Microsoft.Quantum.Intrinsic.X) , [`Y`](xref:Microsoft.Quantum.Intrinsic.Y) y [`Z`](xref:Microsoft.Quantum.Intrinsic.Z) , cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="61fe8-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:Microsoft.Quantum.Intrinsic.X), [`Y`](xref:Microsoft.Quantum.Intrinsic.Y), and [`Z`](xref:Microsoft.Quantum.Intrinsic.Z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="61fe8-147">Como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), piense en $X $ y `X` , por tanto, en una operación de volteo de bits o no en una puerta.</span><span class="sxs-lookup"><span data-stu-id="61fe8-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="61fe8-148">Puede usar la `X` operación para preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:</span><span class="sxs-lookup"><span data-stu-id="61fe8-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="61fe8-149">Más adelante, verá formas más compactas de escribir esta operación que no requieren el flujo de control manual.</span><span class="sxs-lookup"><span data-stu-id="61fe8-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="61fe8-150">También puede preparar estados como $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ y $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ mediante {2} la transformación Hadamard $H $, que se representa en Q# mediante la operación intrínseca [`H`](xref:Microsoft.Quantum.Intrinsic.H) (también de tipo (qubit => unidad es ADJ + CTL) '):</span><span class="sxs-lookup"><span data-stu-id="61fe8-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:Microsoft.Quantum.Intrinsic.H) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="61fe8-151">Medidas</span><span class="sxs-lookup"><span data-stu-id="61fe8-151">Measurements</span></span>

<span data-ttu-id="61fe8-152">Las medidas de qubits individuales se pueden realizar en diferentes bases, cada una representada por un eje Pauli en la [esfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="61fe8-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="61fe8-153">La *base de cálculo* se refiere a la `PauliZ` base y es la base más común que se usa para la medición.</span><span class="sxs-lookup"><span data-stu-id="61fe8-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="61fe8-154">Medir un único qubit de `PauliZ` base</span><span class="sxs-lookup"><span data-stu-id="61fe8-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="61fe8-155">Use la [`M`](xref:Microsoft.Quantum.Intrinsic.M) operación, que es una operación intrínseca no unitario integrada, para medir un único qubit en `PauliZ` base y asignar un valor clásico al resultado.</span><span class="sxs-lookup"><span data-stu-id="61fe8-155">Use the [`M`](xref:Microsoft.Quantum.Intrinsic.M) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="61fe8-156">`M` tiene un tipo de valor devuelto reservado, `Result` , que solo puede tomar valores `Zero` o `One` que corresponden a los Estados medidos $ \ket {0} $ o $ \ket {1} $-, lo que indica que el resultado ya no es un estado Quantum.</span><span class="sxs-lookup"><span data-stu-id="61fe8-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="61fe8-157">Un ejemplo sencillo es la siguiente operación, que asigna una qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="61fe8-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="61fe8-158">Medir uno o más qubits en bases específicas</span><span class="sxs-lookup"><span data-stu-id="61fe8-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="61fe8-159">Para medir una matriz de uno o varios qubits en bases específicas, puede utilizar la [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operación.</span><span class="sxs-lookup"><span data-stu-id="61fe8-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operation.</span></span>

<span data-ttu-id="61fe8-160">Las entradas en `Measure` son una matriz de `Pauli` tipos (por ejemplo, `[PauliX, PauliZ, PauliZ]` ) y una matriz de qubits.</span><span class="sxs-lookup"><span data-stu-id="61fe8-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="61fe8-161">La siguiente operación proporciona un ejemplo ligeramente más complicado, que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` están en el estado cero cuando se miden en una base de Pauli especificada y, de `false` lo contrario, devuelve.</span><span class="sxs-lookup"><span data-stu-id="61fe8-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="61fe8-162">Tenga en cuenta que en este ejemplo solo se realiza `Measure` una qubits individual de una en una, pero la operación se puede extender a las medidas conjuntas en varios qubits.</span><span class="sxs-lookup"><span data-stu-id="61fe8-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="61fe8-163">Ejemplo de qubits de préstamos</span><span class="sxs-lookup"><span data-stu-id="61fe8-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="61fe8-164">Hay ejemplos en el Canon que usan la `borrowing` palabra clave, como la siguiente función `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="61fe8-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="61fe8-165">Si `controls` denota el qubits de control que se va a agregar a una `X` operación, el número de [ancillas](xref:microsoft.quantum.glossary#ancilla) modificados agregados por esta implementación es `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="61fe8-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="61fe8-166">Tenga en cuenta que en este ejemplo se usó un uso extensivo del `With` combinador, en su forma que es aplicable a las operaciones que admiten el tipo de adjoin, por ejemplo, `WithA` .</span><span class="sxs-lookup"><span data-stu-id="61fe8-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="61fe8-167">Este es un buen estilo de programación, ya que agregar el control a las estructuras que implican `With` propaga el control únicamente a la operación interna.</span><span class="sxs-lookup"><span data-stu-id="61fe8-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="61fe8-168">Tenga en cuenta también que, además de la `body` de la operación, `controlled` se proporcionó explícitamente una implementación del cuerpo de la operación, en lugar de recurrir a una `controlled auto` instrucción.</span><span class="sxs-lookup"><span data-stu-id="61fe8-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="61fe8-169">La razón de esto es que, debido a la estructura del circuito, es fácil agregar más controles, que es beneficioso en comparación con agregar el control a cada puerta en `body` .</span><span class="sxs-lookup"><span data-stu-id="61fe8-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="61fe8-170">Es instructivo comparar este código con otra función `MultiControlledXClean` de Canon que logre el mismo objetivo de implementar una operación controlada por multiplicación `X` , sin embargo, que usa varios qubits limpios mediante el `using` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="61fe8-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="61fe8-171">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="61fe8-171">Next steps</span></span>

<span data-ttu-id="61fe8-172">Obtenga información sobre el [flujo de control](xref:microsoft.quantum.guide.controlflow) en Q# .</span><span class="sxs-lookup"><span data-stu-id="61fe8-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>