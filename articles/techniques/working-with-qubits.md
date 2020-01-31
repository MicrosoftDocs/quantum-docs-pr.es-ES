---
title: Trabajar con qubits
description: 'Trabajar con las técnicas qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820001"
---
# <a name="working-with-qubits"></a><span data-ttu-id="18071-103">Trabajar con qubits</span><span class="sxs-lookup"><span data-stu-id="18071-103">Working with Qubits</span></span>

<span data-ttu-id="18071-104">Teniendo en cuenta que ahora hay una variedad de diferentes partes del lenguaje de preguntas y respuestas, vamos a profundizar en ella y veremos cómo usar qubits.</span><span class="sxs-lookup"><span data-stu-id="18071-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="18071-105">Asignar qubits</span><span class="sxs-lookup"><span data-stu-id="18071-105">Allocating Qubits</span></span>

<span data-ttu-id="18071-106">En primer lugar, para obtener un qubit que podamos usar en Q #, *asignamos* qubits dentro de un bloque `using`:</span><span class="sxs-lookup"><span data-stu-id="18071-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="18071-107">Los qubits asignados de esta manera se inician en $ \ket{0}$ State; en el ejemplo anterior, `register` está por tanto en el estado $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="18071-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="18071-108">Al final del bloque `using`, se desasignan inmediatamente los qubits asignados por ese bloque y no se pueden usar más.</span><span class="sxs-lookup"><span data-stu-id="18071-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="18071-109">Los equipos de destino esperan que los qubits se encuentren en $ \ket{0}$ State inmediatamente antes de la desasignación, de modo que se puedan volver a usar y ofrecer a otros bloques de `using` para su asignación.</span><span class="sxs-lookup"><span data-stu-id="18071-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="18071-110">Siempre que sea posible, use las operaciones de unitario para devolver cualquier qubits asignada a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="18071-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="18071-111">Si es necesario, la operación de @"microsoft.quantum.intrinsic.reset" se puede usar para medir un qubit en su lugar y para usar ese resultado de medida para asegurarse de que el qubit medido se devuelve a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="18071-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="18071-112">Dicha medida destruirá cualquier inenredo con el resto de qubits y, por tanto, puede afectar al cálculo.</span><span class="sxs-lookup"><span data-stu-id="18071-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="18071-113">Operaciones intrínsecas</span><span class="sxs-lookup"><span data-stu-id="18071-113">Intrinsic Operations</span></span>

<span data-ttu-id="18071-114">Una vez asignado, una qubit se puede pasar a las funciones y operaciones.</span><span class="sxs-lookup"><span data-stu-id="18071-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="18071-115">En cierto sentido, esto es todo lo que puede hacer un programa de Q # con un qubit, ya que las acciones que se pueden realizar se definen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="18071-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="18071-116">Veremos estas operaciones con más detalle en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), pero por ahora se mencionan algunas operaciones útiles que se pueden usar para interactuar con qubits.</span><span class="sxs-lookup"><span data-stu-id="18071-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="18071-117">En primer lugar, los operadores de Pauli de qubit único $X $, $Y $ y $Z $ se representan en Q # por las operaciones intrínsecas `X`, `Y`y `Z`, cada una de las cuales tiene el tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="18071-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="18071-118">Tal y como se describe en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ y, por lo tanto, `X` como una operación de volteo de bits o no como una puerta.</span><span class="sxs-lookup"><span data-stu-id="18071-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="18071-119">La operación `X` nos permite preparar estados con el formato $ \ket{s_0 s_1 \dots s_n} $ para algunas cadenas de bits clásicas $s $:</span><span class="sxs-lookup"><span data-stu-id="18071-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="18071-120">Más adelante, veremos formas más compactas de escribir esta operación que no requieren el control de flujo manual.</span><span class="sxs-lookup"><span data-stu-id="18071-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="18071-121">También podemos preparar estados como $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ y $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ mediante la transformación Hadamard $H $, que se representa en Q # mediante la operación intrínseca `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="18071-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="18071-122">Medidas</span><span class="sxs-lookup"><span data-stu-id="18071-122">Measurements</span></span>

<span data-ttu-id="18071-123">Con la operación de `Measure`, que es una operación no unitario intrínseca integrada, podemos extraer información clásica de un objeto de tipo `Qubit` y asignar un valor clásico como resultado, que tiene un tipo reservado `Result`, que indica que el resultado ya no es un estado Quantum.</span><span class="sxs-lookup"><span data-stu-id="18071-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="18071-124">La entrada a `Measure` es un eje Pauli en la esfera Bloch, representada por un valor de tipo `Pauli` (por ejemplo `PauliX`) y un valor de tipo `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="18071-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="18071-125">Un ejemplo sencillo es la siguiente operación, que asigna un qubit en $ \ket{0}$ State, aplica una operación Hadamard `H` a él y mide el resultado en la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="18071-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="18071-126">La siguiente operación proporciona un ejemplo ligeramente más complicado, que devuelve el valor booleano `true` si todos los qubits de un registro de tipo `Qubit[]` se encuentran en el estado cero cuando se miden en una base de Pauli especificada y devuelve `false` de lo contrario.</span><span class="sxs-lookup"><span data-stu-id="18071-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="18071-127">El lenguaje Q # permite que el flujo de control clásico dependa de los resultados de la medición de qubits.</span><span class="sxs-lookup"><span data-stu-id="18071-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="18071-128">Esta funcionalidad, a su vez, permite implementar gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.</span><span class="sxs-lookup"><span data-stu-id="18071-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="18071-129">Por ejemplo, es fácil implementar los modelos de *repetición-hasta el éxito* (RU) que se conocen en Q #.</span><span class="sxs-lookup"><span data-stu-id="18071-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="18071-130">Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales, pero para los que el costo real depende de una ejecución real y una intercalación real de varias ramas posibles.</span><span class="sxs-lookup"><span data-stu-id="18071-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="18071-131">Para facilitar patrones de repetición hasta la correcta (RU), Q # admite la construcción</span><span class="sxs-lookup"><span data-stu-id="18071-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="18071-132">donde `statementBlock1` y `statementBlock2` son cero o más instrucciones Q # y `expression` cualquier expresión válida que se evalúe como un valor de tipo `Bool`.</span><span class="sxs-lookup"><span data-stu-id="18071-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="18071-133">En un caso de uso típico, la siguiente operación de Q # implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt{5}$ en la esfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="18071-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="18071-134">Esto se logra mediante el uso de un patrón de RU conocido:</span><span class="sxs-lookup"><span data-stu-id="18071-134">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="18071-135">En este ejemplo se muestra el uso de una variable mutable `finished` que está en el ámbito de todo el bucle de repetición hasta la corrección y que se inicializa antes del bucle y se actualiza en el paso de corrección.</span><span class="sxs-lookup"><span data-stu-id="18071-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="18071-136">Por último, se muestra un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partir del estado $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="18071-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="18071-137">Vea también el [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="18071-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="18071-138">Las características de programación más importantes que se muestran en esta operación son una parte más compleja `fixup` del bucle, lo que implica operaciones Quantum y el uso de instrucciones `AssertProb` para determinar la probabilidad de medir el estado de cuanto en determinados puntos especificados en el programa.</span><span class="sxs-lookup"><span data-stu-id="18071-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="18071-139">Vea también [pruebas y depuración](xref:microsoft.quantum.techniques.testing-and-debugging) para obtener más información sobre las operaciones de [`Assert`](xref:microsoft.quantum.intrinsic.assert) y [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .</span><span class="sxs-lookup"><span data-stu-id="18071-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
