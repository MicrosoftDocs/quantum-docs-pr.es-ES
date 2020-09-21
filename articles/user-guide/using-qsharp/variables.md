---
title: Variables en Q#
description: Obtenga información sobre cómo trabajar con variables diferentes en Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835883"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="ea05f-103">Variables en Q#</span><span class="sxs-lookup"><span data-stu-id="ea05f-103">Variables in Q#</span></span>

<span data-ttu-id="ea05f-104">Q# distingue entre símbolos mutables e inmutables, o *variables*, que se enlazan o asignan a expresiones.</span><span class="sxs-lookup"><span data-stu-id="ea05f-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="ea05f-105">En general, se recomienda el uso de símbolos inmutables porque permite que el compilador realice más optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="ea05f-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="ea05f-106">La parte izquierda de un enlace se compone de una tupla de símbolos y del lado derecho de una expresión.</span><span class="sxs-lookup"><span data-stu-id="ea05f-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="ea05f-107">Variables inmutables</span><span class="sxs-lookup"><span data-stu-id="ea05f-107">Immutable Variables</span></span>

<span data-ttu-id="ea05f-108">Puede asignar un valor de cualquier tipo en Q# una variable para su reutilización en una operación o función mediante la `let` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ea05f-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="ea05f-109">Un enlace inmutable se compone de la palabra clave `let` , seguido de una tupla de símbolos o símbolos, un signo igual `=` , una expresión para enlazar los símbolos a y un punto y coma final.</span><span class="sxs-lookup"><span data-stu-id="ea05f-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="ea05f-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ea05f-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="ea05f-111">Esto asigna una matriz determinada de operadores Pauli al nombre de variable (o "Symbol"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="ea05f-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="ea05f-112">En el ejemplo anterior, no es necesario especificar explícitamente el tipo de la nueva variable, ya que la expresión del lado derecho de la `let` instrucción no es ambigua y el compilador deduce el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="ea05f-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="ea05f-113">Las variables definidas mediante `let` son *inmutables*, lo que significa que una vez que se define, ya no se puede cambiar de ningún modo.</span><span class="sxs-lookup"><span data-stu-id="ea05f-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="ea05f-114">Esto permite varias optimizaciones beneficiosas, incluida la optimización de la lógica clásica que actúa en las variables que se van a reordenar para aplicar la `Adjoint` variante de una operación.</span><span class="sxs-lookup"><span data-stu-id="ea05f-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="ea05f-115">Variables mutables</span><span class="sxs-lookup"><span data-stu-id="ea05f-115">Mutable Variables</span></span>

<span data-ttu-id="ea05f-116">Como alternativa a la creación de una variable con `let` , la `mutable` palabra clave crea una variable mutable que se *puede* volver a enlazar una vez creada inicialmente mediante la `set` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ea05f-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="ea05f-117">Puede volver a enlazar los símbolos declarados y enlazados como parte de una `mutable` instrucción a un valor diferente más adelante en el código.</span><span class="sxs-lookup"><span data-stu-id="ea05f-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="ea05f-118">Si un símbolo se reenlaza posteriormente en el código, su tipo no cambia y el valor recién enlazado debe ser compatible con ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ea05f-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="ea05f-119">Reenlazar símbolos mutables</span><span class="sxs-lookup"><span data-stu-id="ea05f-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="ea05f-120">Puede volver a enlazar una variable mutable mediante una `set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ea05f-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="ea05f-121">Este tipo de reenlace consta de la palabra clave `set` , seguida de una tupla de símbolos o símbolos, un signo igual `=` , una expresión a la que se van a volver a enlazar los símbolos y un punto y coma final.</span><span class="sxs-lookup"><span data-stu-id="ea05f-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="ea05f-122">A continuación se muestran algunos ejemplos de técnicas de reenlace de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ea05f-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="ea05f-123">Instrucciones Apply y resign</span><span class="sxs-lookup"><span data-stu-id="ea05f-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="ea05f-124">Una clase determinada de `set` -Statement, la instrucción *Apply-and-resign* , proporciona una forma cómoda de concatenación si el lado derecho está formado por la aplicación de un operador binario y el resultado se va a volver a enlazar al argumento izquierdo para el operador.</span><span class="sxs-lookup"><span data-stu-id="ea05f-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="ea05f-125">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="ea05f-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="ea05f-126">incrementa el valor del contador `counter` en cada iteración del `for` bucle.</span><span class="sxs-lookup"><span data-stu-id="ea05f-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="ea05f-127">El código anterior es equivalente a</span><span class="sxs-lookup"><span data-stu-id="ea05f-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="ea05f-128">Las instrucciones similares están disponibles para todos los operadores binarios en los que el tipo del lado izquierdo coincide con el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="ea05f-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="ea05f-129">Estas instrucciones proporcionan una manera cómoda de acumular valores.</span><span class="sxs-lookup"><span data-stu-id="ea05f-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="ea05f-130">Por ejemplo, suponiendo `qubits` es un registro de qubits:</span><span class="sxs-lookup"><span data-stu-id="ea05f-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="ea05f-131">Instrucciones Update y resign</span><span class="sxs-lookup"><span data-stu-id="ea05f-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="ea05f-132">Existe una concatenación similar para las [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="ea05f-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="ea05f-133">En consecuencia, las instrucciones *Update-and-resign* existen para *los elementos con nombre* de los tipos definidos por el usuario, así como para *los elementos de matriz*.</span><span class="sxs-lookup"><span data-stu-id="ea05f-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="ea05f-134">En el caso de las matrices, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) en la Q# biblioteca estándar proporciona las herramientas necesarias para muchas necesidades comunes de inicialización y manipulación de matrices y, por tanto, ayuda a evitar tener que actualizar los elementos de la matriz en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="ea05f-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="ea05f-135">Las instrucciones Update-and-resign proporcionan una alternativa si es necesario:</span><span class="sxs-lookup"><span data-stu-id="ea05f-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="ea05f-136">Con las herramientas de biblioteca para las matrices que [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) se proporcionan en, puede, por ejemplo, definir fácilmente una función que devuelve una matriz de `Pauli` tipos donde el elemento en el índice `i` toma un `Pauli` valor determinado y todas las demás entradas son la identidad ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="ea05f-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="ea05f-137">A continuación se muestran dos definiciones de esta función, con el segundo que aprovecha las herramientas de nuestra eliminación.</span><span class="sxs-lookup"><span data-stu-id="ea05f-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="ea05f-138">En lugar de recorrer en iteración cada índice de la matriz y establecerlo de forma condicional en `PauliI` o en el determinado `pauli` , puede usar en su lugar `ConstantArray` de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) para crear una matriz de `PauliI` tipos y, a continuación, devolver simplemente una expresión de copia y actualización en la que haya cambiado el valor específico en el índice `location` :</span><span class="sxs-lookup"><span data-stu-id="ea05f-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="ea05f-139">Desconstrucción de tuplas</span><span class="sxs-lookup"><span data-stu-id="ea05f-139">Tuple Deconstruction</span></span>

<span data-ttu-id="ea05f-140">Además de asignar una sola variable, puede usar las `let` `mutable` palabras clave y, o cualquier otra construcción de enlace, como `set` -para desempaquetar el contenido de un tipo de [tupla](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="ea05f-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="ea05f-141">Se dice que una asignación de este formulario *deconstruye* los elementos de esa tupla.</span><span class="sxs-lookup"><span data-stu-id="ea05f-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="ea05f-142">Si el lado derecho del enlace es una tupla, puede deconstruir esa tupla en la asignación.</span><span class="sxs-lookup"><span data-stu-id="ea05f-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="ea05f-143">Estas desconstrucciones pueden implicar tuplas anidadas, y cualquier desconstrucción parcial o completa es válida siempre y cuando la forma de la tupla en el lado derecho sea compatible con la forma de la tupla de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ea05f-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="ea05f-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ea05f-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="ea05f-145">Ámbitos de enlace</span><span class="sxs-lookup"><span data-stu-id="ea05f-145">Binding Scopes</span></span>

<span data-ttu-id="ea05f-146">En general, los enlaces de símbolos salen del ámbito y quedan inoperativos al final del bloque de instrucciones en el que se encuentran.</span><span class="sxs-lookup"><span data-stu-id="ea05f-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="ea05f-147">Esta regla tiene dos excepciones:</span><span class="sxs-lookup"><span data-stu-id="ea05f-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="ea05f-148">El enlace de la variable de bucle de un `for` bucle está en el ámbito del cuerpo del bucle for, pero no después del final del bucle.</span><span class="sxs-lookup"><span data-stu-id="ea05f-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="ea05f-149">Las tres partes de un `repeat` / `until` bucle (el cuerpo, la prueba y la corrección) actúan como un solo ámbito, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y la corrección.</span><span class="sxs-lookup"><span data-stu-id="ea05f-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="ea05f-150">En ambos tipos de bucles, cada paso a través del bucle se ejecuta en su propio ámbito, por lo que los enlaces de un paso anterior no están disponibles en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="ea05f-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="ea05f-151">Para obtener más información sobre estos bucles, consulte [Control Flow](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="ea05f-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="ea05f-152">Los bloques internos heredan los enlaces de símbolos de los bloques externos.</span><span class="sxs-lookup"><span data-stu-id="ea05f-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="ea05f-153">Solo puede enlazar un símbolo una vez por bloque; no es válido definir un símbolo con el mismo nombre que otro símbolo que está dentro del ámbito (sin "sombreado").</span><span class="sxs-lookup"><span data-stu-id="ea05f-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="ea05f-154">Las secuencias siguientes son válidas:</span><span class="sxs-lookup"><span data-stu-id="ea05f-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="ea05f-155">y</span><span class="sxs-lookup"><span data-stu-id="ea05f-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="ea05f-156">Pero esto sería ilegal:</span><span class="sxs-lookup"><span data-stu-id="ea05f-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="ea05f-157">como sería:</span><span class="sxs-lookup"><span data-stu-id="ea05f-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="ea05f-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ea05f-158">Next steps</span></span>

<span data-ttu-id="ea05f-159">Obtenga información sobre cómo [trabajar con qubits](xref:microsoft.quantum.guide.qubits) en Q# .</span><span class="sxs-lookup"><span data-stu-id="ea05f-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>