---
title: 'Operaciones y funciones de Q #'
description: 'Obtenga información sobre las operaciones y funciones de Q # y cómo se aplican en un programa Quantum.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907671"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="408c7-103">Operaciones y funciones de Q #</span><span class="sxs-lookup"><span data-stu-id="408c7-103">Q# Operations and Functions</span></span>

<span data-ttu-id="408c7-104">Los programas de preguntas y respuestas se componen de una o varias *operaciones* que describen las operaciones de Quantum de efectos secundarios que pueden tener los datos de Quantum y una o varias *funciones* que permiten realizar modificaciones en los datos clásico.</span><span class="sxs-lookup"><span data-stu-id="408c7-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="408c7-105">A diferencia de las operaciones, las funciones se usan para describir el comportamiento puramente clásico y no tienen ningún efecto además de calcular los valores de salida clásico.</span><span class="sxs-lookup"><span data-stu-id="408c7-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="408c7-106">Cada operación definida en Q # puede llamar a cualquier número de operaciones, incluidas las operaciones intrínsecas integradas definidas por el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="408c7-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="408c7-107">La manera determinada en la que se definen estas operaciones intrínsecas depende del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="408c7-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="408c7-108">Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="408c7-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="408c7-109">Definir nuevas operaciones</span><span class="sxs-lookup"><span data-stu-id="408c7-109">Defining New Operations</span></span>

<span data-ttu-id="408c7-110">Tal y como se ha descrito anteriormente, el bloque de creación más básico de un programa Quantum escrito en Q # es una *operación*, a la que se puede llamar desde aplicaciones .net clásicas, por ejemplo, mediante un simulador u otras operaciones en Q #.</span><span class="sxs-lookup"><span data-stu-id="408c7-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="408c7-111">Cada operación toma una entrada, genera una salida y especifica la implementación de una o varias especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="408c7-112">Por ejemplo, la siguiente operación solo define una especialización de cuerpo predeterminada y toma un único qubit como entrada y, a continuación, llama a la operación de `X` integrada en esa entrada:</span><span class="sxs-lookup"><span data-stu-id="408c7-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="408c7-113">La palabra clave `operation` comienza la definición de la operación y va seguida del nombre; aquí, `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="408c7-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="408c7-114">Después, el tipo de la entrada se define como `Qubit`, junto con un nombre `target` para hacer referencia a la entrada dentro de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="408c7-115">Del mismo modo, el `Unit` define que la salida de la operación está vacía.</span><span class="sxs-lookup"><span data-stu-id="408c7-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="408c7-116">Se usa de forma similar a `void` C# en y otros lenguajes imperativos, y es F# equivalente a `unit` en y otros lenguajes funcionales.</span><span class="sxs-lookup"><span data-stu-id="408c7-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="408c7-117">Lo exploraremos con más detalle a continuación, pero cada operación en Q # toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="408c7-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="408c7-118">A continuación, se representan varias entradas y salidas mediante *tuplas*, que recopilan varios valores juntos en un solo valor.</span><span class="sxs-lookup"><span data-stu-id="408c7-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="408c7-119">De manera informativa, decimos que Q # es un lenguaje de "tupla de tupla en".</span><span class="sxs-lookup"><span data-stu-id="408c7-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="408c7-120">Después de este concepto, `()` se debe leer como la tupla "vacía", que tiene el tipo `Unit`.</span><span class="sxs-lookup"><span data-stu-id="408c7-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="408c7-121">Dentro de la nueva operación, la implementación se puede especificar directamente dentro de la declaración si solo es necesario especificar explícitamente la implementación de la especialización del cuerpo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="408c7-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="408c7-122">Además, es posible definir las implementaciones de, por ejemplo, una o varias operaciones de `functor`, tal como se ha elaborado a continuación.</span><span class="sxs-lookup"><span data-stu-id="408c7-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="408c7-123">En el ejemplo anterior, la única instrucción es llamar a la operación de Q # integrada <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="408c7-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="408c7-124">Las operaciones también pueden devolver tipos más interesantes que `Unit`.</span><span class="sxs-lookup"><span data-stu-id="408c7-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="408c7-125">Por ejemplo, la operación <xref:microsoft.quantum.intrinsic.m> devuelve una salida de tipo `Result`, que representa la realización de una medición.</span><span class="sxs-lookup"><span data-stu-id="408c7-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="408c7-126">Podemos pasar el resultado de una operación a otra operación, o bien puede usarlo con la palabra clave `let` para definir una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="408c7-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="408c7-127">Esto permite representar el cálculo clásico que interactúa con las operaciones Quantum en un nivel bajo, como en el caso de la codificación superdensa:</span><span class="sxs-lookup"><span data-stu-id="408c7-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="408c7-128">Inactivos, contiguos y controlados</span><span class="sxs-lookup"><span data-stu-id="408c7-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="408c7-129">Si una operación implementa una transformación unitario, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*.</span><span class="sxs-lookup"><span data-stu-id="408c7-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="408c7-130">Una especialización de una operación adyacente especifica cómo actúa cuando se ejecuta en orden inverso, mientras que una especialización controlada especifica cómo actúa una operación cuando se aplica en el estado de un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="408c7-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="408c7-131">La existencia de estas especializaciones se puede declarar como parte de la firma de la operación: `is Adj + Ctl` en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="408c7-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="408c7-132">El compilador genera la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente.</span><span class="sxs-lookup"><span data-stu-id="408c7-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="408c7-133">Muchas operaciones en Q # representan las puertas de la unidad.</span><span class="sxs-lookup"><span data-stu-id="408c7-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="408c7-134">Si $U $ es la puerta de la unitario representada por una operación `U`, `Adjoint U` representa la puerta de $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="408c7-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="408c7-135">En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="408c7-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="408c7-136">Dichas declaraciones de especialización explícita pueden constar de una directiva de generación adecuada o una implementación definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="408c7-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="408c7-137">El código de `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas:</span><span class="sxs-lookup"><span data-stu-id="408c7-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="408c7-138">La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.</span><span class="sxs-lookup"><span data-stu-id="408c7-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="408c7-139">Si el compilador no puede generar la implementación para una determinada especialización automáticamente, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.</span><span class="sxs-lookup"><span data-stu-id="408c7-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="408c7-140">En el ejemplo anterior, `adjoint invert;` indica que la especialización de la instancia contigua se va a generar invirtiendo la implementación del cuerpo y `controlled adjoint invert;` indica que la especialización contigua controlada se generará invirtiendo la implementación dada de la especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="408c7-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="408c7-141">Veremos más ejemplos de esto en el [flujo de control de orden superior](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="408c7-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="408c7-142">Para llamar a una especialización de una operación, utilice las palabras clave `Adjoint` o `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="408c7-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="408c7-143">Por ejemplo, el ejemplo de codificación de superdensas anterior se puede escribir de forma más compacta mediante el uso del valor contiguo de `PrepareEntangledPair` para transformar de nuevo el estado desenredado en un par unentangled de qubits:</span><span class="sxs-lookup"><span data-stu-id="408c7-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="408c7-144">Hay una serie de limitaciones importantes que se deben tener en cuenta al diseñar operaciones para usarlas con los funcdores.</span><span class="sxs-lookup"><span data-stu-id="408c7-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="408c7-145">Lo más importante es que el compilador no puede generar automáticamente especializaciones para una operación que usa el valor de salida de cualquier otra operación, ya que es ambiguo cómo reordenar las instrucciones en dicha operación para obtener el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="408c7-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="408c7-146">Definir nuevas funciones</span><span class="sxs-lookup"><span data-stu-id="408c7-146">Defining New Functions</span></span>

<span data-ttu-id="408c7-147">Q # también permite definir *funciones*, que son distintas de las operaciones en que no se les permite tener ningún efecto más allá del cálculo de un valor de salida.</span><span class="sxs-lookup"><span data-stu-id="408c7-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="408c7-148">En concreto, las funciones no pueden llamar a las operaciones, actuar en qubits, números aleatorios de muestra o, de lo contrario, depender del estado más allá del valor de entrada de una función.</span><span class="sxs-lookup"><span data-stu-id="408c7-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="408c7-149">Como consecuencia, las funciones Q # son *puras*, ya que siempre asignan los mismos valores de entrada a los mismos valores de salida.</span><span class="sxs-lookup"><span data-stu-id="408c7-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="408c7-150">Esto permite que el compilador de preguntas # reordene de forma segura cómo y cuándo se llama a las funciones al generar especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="408c7-151">La definición de una función funciona de forma similar a la definición de una operación, con la excepción de que no se puede definir ninguna especialización contigua o controlada para una función.</span><span class="sxs-lookup"><span data-stu-id="408c7-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="408c7-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="408c7-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="408c7-153">Siempre que sea posible hacerlo, resulta útil escribir una lógica clásica en términos de funciones en lugar de operaciones, de modo que se pueda utilizar más fácilmente desde las operaciones.</span><span class="sxs-lookup"><span data-stu-id="408c7-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="408c7-154">Si hubiéramos escrito `Square` como una operación, por ejemplo, el compilador no habría podido garantizar que la llamada a él con la misma entrada produciría sistemáticamente los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="408c7-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="408c7-155">Para subrayar la diferencia entre las funciones y las operaciones, tenga en cuenta el problema de realizar un muestreo de forma de un número aleatorio en una operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="408c7-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="408c7-156">Cada vez que se llama a `U`, tendrá una acción diferente en `target`.</span><span class="sxs-lookup"><span data-stu-id="408c7-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="408c7-157">En concreto, el compilador no puede garantizar que si se agrega una declaración de especialización `adjoint auto` a `U`, `U(target); Adjoint U(target);` actúa como identidad (es decir, como una operación no operativa).</span><span class="sxs-lookup"><span data-stu-id="408c7-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="408c7-158">Esto infringe la definición del método contiguo que vimos en [vectores y matrices](xref:microsoft.quantum.concepts.vectors), de modo que permitir la generación automática de una especialización de tipo contiguo en una operación en la que se llamó a la operación <xref:microsoft.quantum.math.randomreal> interrumpiría las garantías proporcionadas por el compilador. <xref:microsoft.quantum.math.randomreal> es una operación para la que no existe ninguna versión contigua o controlada.</span><span class="sxs-lookup"><span data-stu-id="408c7-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="408c7-159">Por otro lado, permitir llamadas a funciones como `Square` es seguro, en el que el compilador puede estar seguro de que solo necesita conservar la entrada en `Square` para mantener la salida estable.</span><span class="sxs-lookup"><span data-stu-id="408c7-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="408c7-160">Por lo tanto, el aislamiento de la lógica más clásica posible en las funciones facilita la reutilización de esa lógica en otras funciones y operaciones similares.</span><span class="sxs-lookup"><span data-stu-id="408c7-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="408c7-161">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="408c7-161">Control Flow</span></span>

<span data-ttu-id="408c7-162">Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a la mayoría de los lenguajes imperativos más comunes.</span><span class="sxs-lookup"><span data-stu-id="408c7-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="408c7-163">Este flujo de control se puede modificar, sin embargo, de tres maneras distintas:</span><span class="sxs-lookup"><span data-stu-id="408c7-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="408c7-164">Instrucciones de `if`</span><span class="sxs-lookup"><span data-stu-id="408c7-164">`if` Statements</span></span>
- <span data-ttu-id="408c7-165">`for` bucles</span><span class="sxs-lookup"><span data-stu-id="408c7-165">`for` Loops</span></span>
- <span data-ttu-id="408c7-166">`repeat`-bucles `until`</span><span class="sxs-lookup"><span data-stu-id="408c7-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="408c7-167">Aplazamos la explicación de este último hasta que analicemos los circuitos de [repetición hasta éxitos (RU)](xref:microsoft.quantum.techniques.qubits#measurements) .</span><span class="sxs-lookup"><span data-stu-id="408c7-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="408c7-168">Sin embargo, las construcciones de flujo de control `if` y `for` continúan en un sentido familiar para la mayoría de los lenguajes de programación clásico.</span><span class="sxs-lookup"><span data-stu-id="408c7-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="408c7-169">En concreto, una instrucción `if` puede tomar una condición, puede ir seguida de una o varias instrucciones `elif` y puede acabar con un `else`:</span><span class="sxs-lookup"><span data-stu-id="408c7-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="408c7-170">Del mismo modo, `for` bucles indican la iteración en un intervalo de enteros o en los elementos de una matriz:</span><span class="sxs-lookup"><span data-stu-id="408c7-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="408c7-171">Lo importante es que los bucles de `for` y las instrucciones de `if` se pueden usar incluso en operaciones para las que se generan automáticamente especializaciones.</span><span class="sxs-lookup"><span data-stu-id="408c7-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="408c7-172">En ese caso, el contiguo de un bucle `for` invierte la dirección y toma el contiguo de cada iteración.</span><span class="sxs-lookup"><span data-stu-id="408c7-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="408c7-173">Esto sigue el principio de "zapatos y Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS.</span><span class="sxs-lookup"><span data-stu-id="408c7-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="408c7-174">Funciona a la medida de que sea un poco bien para probar y sacar su Socks mientras sigue usando sus zapatos.</span><span class="sxs-lookup"><span data-stu-id="408c7-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="408c7-175">Operaciones y funciones como valores de primera clase</span><span class="sxs-lookup"><span data-stu-id="408c7-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="408c7-176">Una técnica crítica para el razonamiento sobre el flujo de control y la lógica clásica con funciones en lugar de operaciones es usar las operaciones y las funciones de Q # como *primera clase*.</span><span class="sxs-lookup"><span data-stu-id="408c7-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="408c7-177">Es decir, cada uno de los valores del lenguaje se encuentra en su propio derecho.</span><span class="sxs-lookup"><span data-stu-id="408c7-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="408c7-178">Por ejemplo, lo siguiente es código de Q # perfectamente válido, si un poco indirecto:</span><span class="sxs-lookup"><span data-stu-id="408c7-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="408c7-179">El valor de la variable `ourH` en el fragmento de código anterior es el <xref:microsoft.quantum.intrinsic.h>de la operación, de modo que se pueda llamar a ese valor como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="408c7-180">Esto nos permite escribir operaciones que tomen las operaciones como parte de su entrada, formando conceptos de flujo de control de orden superior.</span><span class="sxs-lookup"><span data-stu-id="408c7-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="408c7-181">Por ejemplo, podríamos imaginar que quiere "cuadrado" una operación aplicándole dos veces en el mismo qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="408c7-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="408c7-182">En este ejemplo, la flecha de `=>` que aparece en el tipo `(Qubit => Unit)` denota que el campo de entrada `op` es una operación que toma como entrada el tipo `Qubit` y genera una tupla vacía como salida.</span><span class="sxs-lookup"><span data-stu-id="408c7-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="408c7-183">Además, se especifican las características de ese tipo de operación, que contienen la información sobre los tipos de datos que se admiten.</span><span class="sxs-lookup"><span data-stu-id="408c7-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="408c7-184">Una operación de tipo `(Qubit => Unit)` no admite la `Adjoint` ni la `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="408c7-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="408c7-185">Si queremos indicar que una operación de ese tipo tiene que admitir, por ejemplo, la `Adjoint` functor, tenemos que declararla como adjointable.</span><span class="sxs-lookup"><span data-stu-id="408c7-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="408c7-186">Esto se hace utilizando la anotación `is Adj` al tipo.</span><span class="sxs-lookup"><span data-stu-id="408c7-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="408c7-187">Del mismo modo, `(Qubit => Unit is Ctl)` denota que una operación de ese tipo admite el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="408c7-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="408c7-188">Lo exploraremos más en general si analizamos los [tipos en Q # más en](xref:microsoft.quantum.language.type-model) general.</span><span class="sxs-lookup"><span data-stu-id="408c7-188">We will explore this further when we discuss [types in Q#](xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="408c7-189">Por ahora, hacemos hincapié en que también se pueden devolver las operaciones como parte de las salidas, de modo que podamos aislar algunos tipos de lógica condicional clásica como una función clásica que devuelve una descripción de un programa Quantum en forma de una operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="408c7-190">Como ejemplo sencillo, considere el ejemplo de teleportabilidad, en el que la entidad que recibe un mensaje clásico de dos bits debe usar el mensaje para descodificar sus qubit en el estado de telepuerto adecuado.</span><span class="sxs-lookup"><span data-stu-id="408c7-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="408c7-191">Podríamos escribir esto en términos de una función que toma esos dos bits clásico y devuelve la operación de descodificación adecuada.</span><span class="sxs-lookup"><span data-stu-id="408c7-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="408c7-192">Esta nueva función es realmente una función, en el caso de que se llame con los mismos valores de `hereBit` y `thereBit`, siempre se devolverá la misma operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="408c7-193">Por lo tanto, el descodificador se puede ejecutar de forma segura dentro de las operaciones sin tener que preocuparse de cómo la lógica de descodificación interactúa con las definiciones de las distintas especializaciones de operación.</span><span class="sxs-lookup"><span data-stu-id="408c7-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="408c7-194">Es decir, hemos aislado la lógica clásica dentro de una función, garantizando al compilador que la llamada a la función se puede reordenar con Impunity, siempre y cuando se conserve la entrada.</span><span class="sxs-lookup"><span data-stu-id="408c7-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="408c7-195">También podemos tratar las funciones como valores de primera clase, ya que veremos con más detalle cuando se analizan [las operaciones y los tipos de función](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="408c7-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="408c7-196">Aplicar operaciones y funciones parcialmente</span><span class="sxs-lookup"><span data-stu-id="408c7-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="408c7-197">Podemos hacer mucho más con funciones que devuelven operaciones mediante el uso de una *aplicación parcial*, en la que podemos proporcionar una o más partes de la entrada a una función u operación sin llamarla realmente.</span><span class="sxs-lookup"><span data-stu-id="408c7-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="408c7-198">Por ejemplo, al volver a llamar al ejemplo `ApplyTwice` anterior, podemos indicar que no queremos especificar, de inmediato, a qué qubit se debe aplicar la operación de entrada:</span><span class="sxs-lookup"><span data-stu-id="408c7-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="408c7-199">En este caso, la variable local `twiceOp` contiene la operación parcialmente aplicada `ApplyTwice(op, _)`, donde las partes de la entrada que todavía no se han especificado se indican mediante `_`.</span><span class="sxs-lookup"><span data-stu-id="408c7-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="408c7-200">Cuando realmente llamamos `twiceOp` en la línea siguiente, pasamos como entrada a la operación parcialmente aplicada todas las partes restantes de la entrada a la operación original.</span><span class="sxs-lookup"><span data-stu-id="408c7-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="408c7-201">Por lo tanto, el fragmento de código anterior es realmente idéntico a haber llamado a `ApplyTwice(op, target)` directamente, y se guarda para que se haya introducido una nueva variable local que nos permita retrasar la llamada mientras se proporcionan algunas partes de la entrada.</span><span class="sxs-lookup"><span data-stu-id="408c7-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="408c7-202">Dado que una operación que se ha aplicado parcialmente no se llama realmente hasta que se ha proporcionado toda la entrada, podemos aplicar de forma segura las operaciones, incluso desde las funciones.</span><span class="sxs-lookup"><span data-stu-id="408c7-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="408c7-203">En principio, la lógica clásica dentro de `SquareOperation` podría haber sido mucho más complicada, pero sigue estando aislada del resto de una operación mediante la garantía de que el compilador puede ofrecer información sobre las funciones.</span><span class="sxs-lookup"><span data-stu-id="408c7-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="408c7-204">Este enfoque se usará en toda la biblioteca de preguntas y respuestas para expresar el flujo de control clásico de manera que se pueda usar fácilmente dentro de los programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="408c7-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
