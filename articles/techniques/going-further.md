---
title: 'Más información: técnicas de Q # | Microsoft Docs'
description: 'Más información: técnicas de Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820205"
---
# <a name="going-further"></a><span data-ttu-id="02256-103">Más información</span><span class="sxs-lookup"><span data-stu-id="02256-103">Going Further</span></span> #

<span data-ttu-id="02256-104">Ahora que ha visto cómo escribir programas Quantum interesantes en p #, en esta sección se explica con más detalle mediante la introducción de algunos temas más avanzados que deberían resultar útiles en el futuro.</span><span class="sxs-lookup"><span data-stu-id="02256-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="02256-105">Operaciones y funciones genéricas</span><span class="sxs-lookup"><span data-stu-id="02256-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="02256-106">En esta sección se da por supuesto que está familiarizado con los [genéricos de C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [genéricos en F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ plantillas](https://docs.microsoft.com/cpp/cpp/templates-cpp)o enfoques similares a la Metaprogramación en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="02256-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="02256-107">Muchas funciones y operaciones que podríamos querer definir no se basan en gran medida en los tipos de sus entradas, sino que solo usan implícitamente sus tipos a través de otra función u operación.</span><span class="sxs-lookup"><span data-stu-id="02256-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="02256-108">Por ejemplo, considere el concepto de *mapa* común a muchos idiomas funcionales; dada una función $f (x) $ y una colección de valores $\{x_1, x_2, \dots, x_n\}$, Map devuelve una nueva colección $\{f (x_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="02256-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="02256-109">Para implementar esto en Q #, podemos aprovechar las ventajas de que las funciones son de primera clase.</span><span class="sxs-lookup"><span data-stu-id="02256-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="02256-110">Vamos a escribir un ejemplo rápido de `Map`, mediante el uso de ★ como un marcador de posición mientras averiguamos qué tipos necesitamos.</span><span class="sxs-lookup"><span data-stu-id="02256-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="02256-111">Tenga en cuenta que esta función tiene un aspecto muy similar al de los tipos reales que se sustituyen en.</span><span class="sxs-lookup"><span data-stu-id="02256-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="02256-112">Una asignación de enteros a Paulis, por ejemplo, se parece mucho a una asignación de números de punto flotante a cadenas:</span><span class="sxs-lookup"><span data-stu-id="02256-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="02256-113">En principio, podríamos escribir una versión de `Map` para cada par de tipos que encontramos, pero esto presenta una serie de dificultades.</span><span class="sxs-lookup"><span data-stu-id="02256-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="02256-114">Por ejemplo, si encontramos un error en `Map`, debemos asegurarnos de que la corrección se aplique uniformemente en todas las versiones de `Map`.</span><span class="sxs-lookup"><span data-stu-id="02256-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="02256-115">Además, si creamos una nueva tupla o UDT, ahora debemos crear también una nueva `Map` para ir junto con el nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="02256-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="02256-116">Aunque esto es tractable para un número pequeño de estas funciones, a medida que recopilamos más funciones de la misma forma que `Map`, el costo de introducir nuevos tipos se vuelve injustificable en un orden bastante corto.</span><span class="sxs-lookup"><span data-stu-id="02256-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="02256-117">Sin embargo, gran parte de este problema se debe a que no se ha proporcionado al compilador la información necesaria para reconocer cómo se relacionan las diferentes versiones de `Map`.</span><span class="sxs-lookup"><span data-stu-id="02256-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="02256-118">En efecto, queremos que el compilador trate `Map` como algún tipo de función matemática de *tipos* q # a funciones q #.</span><span class="sxs-lookup"><span data-stu-id="02256-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="02256-119">Esta noción se formaliza permitiendo que las funciones y las operaciones tengan *parámetros de tipo*, así como sus parámetros de tupla normales.</span><span class="sxs-lookup"><span data-stu-id="02256-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="02256-120">En los ejemplos anteriores, deseamos pensar en `Map` como tener parámetros de tipo `Int, Pauli` en el primer caso y `Double, String` en el segundo caso.</span><span class="sxs-lookup"><span data-stu-id="02256-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="02256-121">En su mayor parte, estos parámetros de tipo se pueden usar como si fueran tipos normales: usamos valores de parámetros de tipo para crear matrices y tuplas, llamar a funciones y operaciones, y asignar a variables ordinarias o mutables.</span><span class="sxs-lookup"><span data-stu-id="02256-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="02256-122">El caso más extremo de dependencia indirecta es el de qubits, donde un programa de Q # no puede confiar directamente en la estructura del tipo de `Qubit`, sino que **debe** pasar estos tipos a otras operaciones y funciones.</span><span class="sxs-lookup"><span data-stu-id="02256-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="02256-123">Volviendo al ejemplo anterior, podemos ver que necesitamos `Map` tener parámetros de tipo, uno para representar la entrada a `fn` y otro para representar la salida de `fn`.</span><span class="sxs-lookup"><span data-stu-id="02256-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="02256-124">En Q #, esto se escribe agregando corchetes angulares (es decir `<>`, no frenos $ \braket{}$!) después del nombre de una función u operación en su declaración, y enumerando cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="02256-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="02256-125">El nombre de cada parámetro de tipo debe comenzar con una marca de paso `'`, lo que indica que se trata de un parámetro de tipo y no de un tipo ordinario (también conocido como tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="02256-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="02256-126">Por lo tanto, para `Map`, escribimos:</span><span class="sxs-lookup"><span data-stu-id="02256-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="02256-127">Tenga en cuenta que la definición de `Map<'Input, 'Output>` tiene un aspecto muy similar al de las versiones que escribimos antes.</span><span class="sxs-lookup"><span data-stu-id="02256-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="02256-128">La única diferencia es que hemos informado explícitamente al compilador de que `Map` no depende directamente de qué `'Input` y `'Output` son, pero funciona para dos tipos mediante el uso indirecto de los `fn`.</span><span class="sxs-lookup"><span data-stu-id="02256-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="02256-129">Una vez que hemos definido `Map<'Input, 'Output>` de este modo, podemos llamarlo como si fuera una función ordinaria:</span><span class="sxs-lookup"><span data-stu-id="02256-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="02256-130">La escritura de funciones y operaciones genéricas es un lugar donde "tupla en tupla" es una forma muy útil de pensar en las funciones y operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="02256-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="02256-131">Dado que cada función toma exactamente una entrada y devuelve exactamente una salida, una entrada de tipo `'T -> 'U` coincide con *cualquier* función de Q #.</span><span class="sxs-lookup"><span data-stu-id="02256-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="02256-132">Del mismo modo, cualquier operación se puede pasar a una entrada de tipo `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="02256-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="02256-133">Como segundo ejemplo, considere el reto de escribir una función que devuelva la composición de otras dos funciones:</span><span class="sxs-lookup"><span data-stu-id="02256-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="02256-134">Aquí, debemos especificar exactamente qué `A`, `B`y `C` son, por lo que limitan gravemente la utilidad de la nueva función de `Compose`.</span><span class="sxs-lookup"><span data-stu-id="02256-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="02256-135">Después de todo, solo `Compose` depende de `A`, `B`y `C` *a través* de `innerFn` y `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="02256-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="02256-136">Como alternativa, se pueden agregar parámetros de tipo a `Compose` que indiquen que funciona con *cualquier* `A`, `B`y `C`, siempre y cuando estos parámetros coincidan con los esperados por `innerFn` y `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="02256-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="02256-137">Las bibliotecas de preguntas # estándar proporcionan una gama de funciones y operaciones parametrizadas de tipo para facilitar la rápida creación de un flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="02256-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="02256-138">Estos se describen con más detalle en la guía de la [biblioteca estándar de preguntas y respuestas](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="02256-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="02256-139">Préstamos qubits</span><span class="sxs-lookup"><span data-stu-id="02256-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="02256-140">El mecanismo de préstamos permite la asignación de qubits que se puede usar como espacio de desecho durante un cálculo.</span><span class="sxs-lookup"><span data-stu-id="02256-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="02256-141">Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="02256-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="02256-142">También habla de qubits "sucio", ya que su estado es desconocido e incluso puede estar inactivado con otras partes de la memoria del equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="02256-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="02256-143">Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.</span><span class="sxs-lookup"><span data-stu-id="02256-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="02256-144">En Canon hay ejemplos que usan la palabra clave `borrowing`, por ejemplo, la función `MultiControlledXBorrow` define a continuación.</span><span class="sxs-lookup"><span data-stu-id="02256-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="02256-145">Si `controls` denota el control qubits que debe agregarse a una operación de `X`, esta implementación agregará un total de `Length(controls)-2` muchos ancillas modificados.</span><span class="sxs-lookup"><span data-stu-id="02256-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="02256-146">Tenga en cuenta que el uso extensivo del `With` combinador---en su forma que es aplicable a las operaciones que admiten el operador de cojoin, es decir, `WithA`---se realizó en este ejemplo, que es un estilo de programación adecuado, ya que agregar el control a las estructuras que implican `With` solo propaga el control a la operación interna.</span><span class="sxs-lookup"><span data-stu-id="02256-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="02256-147">Tenga en cuenta que aquí, además de la `body` de la operación, se proporcionó explícitamente una implementación del cuerpo `controlled` de la operación, en lugar de recurrir a una instrucción `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="02256-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="02256-148">La razón es que sabemos de la estructura del circuito cómo agregar fácilmente más controles, lo que es beneficioso en comparación con la adición de control a cada una de las puertas individuales del `body`.</span><span class="sxs-lookup"><span data-stu-id="02256-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="02256-149">Es instructivo comparar este código con otra función de Canon `MultiControlledXClean` que logra el mismo objetivo de implementar una operación de `X` controlada multiplicada, sin embargo, que usa varios qubits limpios con el mecanismo de `using`.</span><span class="sxs-lookup"><span data-stu-id="02256-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
