---
title: 'Flujo de control en Q #'
description: Bucles, condicionales, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326547"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="6e0de-103">Flujo de control en Q #</span><span class="sxs-lookup"><span data-stu-id="6e0de-103">Control Flow in Q#</span></span>

<span data-ttu-id="6e0de-104">Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a la mayoría de los lenguajes imperativos más comunes.</span><span class="sxs-lookup"><span data-stu-id="6e0de-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="6e0de-105">Este flujo de control se puede modificar, sin embargo, de tres maneras distintas:</span><span class="sxs-lookup"><span data-stu-id="6e0de-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="6e0de-106">`if`afirma</span><span class="sxs-lookup"><span data-stu-id="6e0de-106">`if` statements</span></span>
- <span data-ttu-id="6e0de-107">`for`bucles</span><span class="sxs-lookup"><span data-stu-id="6e0de-107">`for` loops</span></span>
- <span data-ttu-id="6e0de-108">`repeat`-`until`bucles</span><span class="sxs-lookup"><span data-stu-id="6e0de-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="6e0de-109">Aplazamos la explicación de este último para más [adelante](#repeat-until-success-loop).</span><span class="sxs-lookup"><span data-stu-id="6e0de-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="6e0de-110">`if`Sin embargo, las construcciones de flujo de control y `for` continúan en un sentido familiar para la mayoría de los lenguajes de programación clásicas.</span><span class="sxs-lookup"><span data-stu-id="6e0de-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="6e0de-111">Lo importante es `for` que los bucles y `if` las instrucciones se pueden usar incluso en operaciones para las que se generan automáticamente especializaciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="6e0de-112">En ese caso, el contiguo de un `for` bucle invierte la dirección y toma el contiguo de cada iteración.</span><span class="sxs-lookup"><span data-stu-id="6e0de-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="6e0de-113">Esto sigue el principio de "zapatos y Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS.</span><span class="sxs-lookup"><span data-stu-id="6e0de-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="6e0de-114">Funciona a la medida de que sea un poco bien para probar y sacar su Socks mientras sigue usando sus zapatos.</span><span class="sxs-lookup"><span data-stu-id="6e0de-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="6e0de-115">If, else-if, else</span><span class="sxs-lookup"><span data-stu-id="6e0de-115">If, Else-if, Else</span></span>

<span data-ttu-id="6e0de-116">La `if` instrucción admite la ejecución condicional.</span><span class="sxs-lookup"><span data-stu-id="6e0de-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="6e0de-117">Consta de la palabra clave `if` , un paréntesis de apertura `(` , una expresión booleana, un paréntesis de cierre `)` y un bloque de instrucciones (el bloque _then_ ).</span><span class="sxs-lookup"><span data-stu-id="6e0de-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="6e0de-118">Esto puede ir seguido de cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif` , un paréntesis de apertura `(` , una expresión booleana, un paréntesis de cierre `)` y un bloque de instrucciones (el bloque _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="6e0de-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="6e0de-119">Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguida de otro bloque de instrucciones (el bloque _else_ ).</span><span class="sxs-lookup"><span data-stu-id="6e0de-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="6e0de-120">La `if` condición se evalúa y, si es true, se ejecuta el bloque then.</span><span class="sxs-lookup"><span data-stu-id="6e0de-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="6e0de-121">Si la condición es false, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque else-if.</span><span class="sxs-lookup"><span data-stu-id="6e0de-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="6e0de-122">De lo contrario, el segundo bloque else-if se prueba y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición true o no haya más cláusulas else-if.</span><span class="sxs-lookup"><span data-stu-id="6e0de-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="6e0de-123">Si las cláusulas IF original y All else-if se evalúan como false, el bloque else se ejecutará si se proporciona uno.</span><span class="sxs-lookup"><span data-stu-id="6e0de-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="6e0de-124">Tenga en cuenta que el bloque que se ejecuta se ejecuta en su propio ámbito.</span><span class="sxs-lookup"><span data-stu-id="6e0de-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="6e0de-125">Los enlaces realizados dentro de un `if` `elif` bloque, o `else` no son visibles después del final.</span><span class="sxs-lookup"><span data-stu-id="6e0de-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="6e0de-126">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="6e0de-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="6e0de-127">or</span><span class="sxs-lookup"><span data-stu-id="6e0de-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="6e0de-128">Bucle For</span><span class="sxs-lookup"><span data-stu-id="6e0de-128">For Loop</span></span>

<span data-ttu-id="6e0de-129">La `for` instrucción admite la iteración en un intervalo de enteros o en una matriz.</span><span class="sxs-lookup"><span data-stu-id="6e0de-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="6e0de-130">La instrucción consta de la palabra clave `for` , un paréntesis `(` de apertura, seguido de una tupla de símbolos o símbolos, la palabra clave `in` , una expresión de tipo `Range` o matriz, un paréntesis de cierre `)` y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="6e0de-131">El bloque de instrucciones (el cuerpo del bucle) se ejecuta varias veces, con los símbolos definidos (las variables de bucle) enlazados a cada valor del intervalo o de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6e0de-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="6e0de-132">Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecutará en absoluto.</span><span class="sxs-lookup"><span data-stu-id="6e0de-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="6e0de-133">La expresión se evalúa completamente antes de entrar en el bucle y no cambiará mientras se ejecuta el bucle.</span><span class="sxs-lookup"><span data-stu-id="6e0de-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="6e0de-134">La variable de bucle se enlaza en cada entrada al cuerpo del bucle y sin enlazar al final del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="6e0de-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="6e0de-135">En concreto, la variable de bucle no se enlaza una vez completado el bucle for.</span><span class="sxs-lookup"><span data-stu-id="6e0de-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="6e0de-136">El enlace de los símbolos declarados es inmutable y sigue las mismas reglas que otros enlaces de variables.</span><span class="sxs-lookup"><span data-stu-id="6e0de-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="6e0de-137">En algunos ejemplos, suponiendo `qubits` es un registro de qubits (es decir, de tipo `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="6e0de-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="6e0de-138">Tenga en cuenta que al final usamos el operador binario de desplazamiento aritmético a la izquierda, `<<<` , detalles de los que se pueden encontrar en [expresiones numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions) .</span><span class="sxs-lookup"><span data-stu-id="6e0de-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="6e0de-139">Bucle repeat-Until-Success</span><span class="sxs-lookup"><span data-stu-id="6e0de-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="6e0de-140">El lenguaje Q # permite que el flujo de control clásico dependa de los resultados de la medición de qubits.</span><span class="sxs-lookup"><span data-stu-id="6e0de-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="6e0de-141">Esta funcionalidad, a su vez, permite implementar gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.</span><span class="sxs-lookup"><span data-stu-id="6e0de-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="6e0de-142">Por ejemplo, es fácil implementar los modelos de *repetición-hasta el éxito* (RU) que se conocen en Q #.</span><span class="sxs-lookup"><span data-stu-id="6e0de-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="6e0de-143">Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales, pero para los que el costo real depende de una ejecución real y una intercalación real de varias ramas posibles.</span><span class="sxs-lookup"><span data-stu-id="6e0de-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="6e0de-144">Para facilitar los patrones de repetición hasta la correcta (RU), Q # admite las construcciones</span><span class="sxs-lookup"><span data-stu-id="6e0de-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="6e0de-145">donde `expression` es cualquier expresión válida que se evalúe como un valor de tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="6e0de-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="6e0de-146">Se ejecuta el cuerpo del bucle y, a continuación, se evalúa la condición.</span><span class="sxs-lookup"><span data-stu-id="6e0de-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="6e0de-147">Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se vuelve a ejecutar empezando por el cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="6e0de-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="6e0de-148">Las tres partes de un bucle repeat/Until (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito *para cada repetición*, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y en la corrección.</span><span class="sxs-lookup"><span data-stu-id="6e0de-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="6e0de-149">Sin embargo, al finalizar la ejecución de la corrección finaliza el ámbito de la instrucción, de modo que los enlaces de símbolos realizados durante el cuerpo o la corrección no estén disponibles en las repeticiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6e0de-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="6e0de-150">Además, la `fixup` instrucción suele ser útil pero no siempre es necesaria.</span><span class="sxs-lookup"><span data-stu-id="6e0de-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="6e0de-151">En los casos en los que no es necesario, la construcción</span><span class="sxs-lookup"><span data-stu-id="6e0de-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="6e0de-152">también es un patrón de RUS válido.</span><span class="sxs-lookup"><span data-stu-id="6e0de-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="6e0de-153">En la parte inferior de esta página, presentamos algunos [ejemplos de bucles Rus](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="6e0de-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="6e0de-154">Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="6e0de-155">La funcionalidad correspondiente la proporcionan los bucles while en las funciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="6e0de-156">While (bucle)</span><span class="sxs-lookup"><span data-stu-id="6e0de-156">While Loop</span></span>

<span data-ttu-id="6e0de-157">Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6e0de-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="6e0de-158">Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q #.</span><span class="sxs-lookup"><span data-stu-id="6e0de-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="6e0de-159">Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación deben controlarse con especial atención en un tiempo de ejecución de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6e0de-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="6e0de-160">El uso de las funciones por otro lado no es problemático, ya que solo contienen código que se ejecutará en hardware convencional (no Quantum).</span><span class="sxs-lookup"><span data-stu-id="6e0de-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="6e0de-161">Por lo tanto, Q # solo admite el uso de bucles while dentro de funciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="6e0de-162">Una `while` instrucción consta de la palabra clave `while` , un paréntesis de apertura `(` , una condición (es decir, una expresión booleana), un paréntesis de cierre `)` y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6e0de-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="6e0de-163">El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true` .</span><span class="sxs-lookup"><span data-stu-id="6e0de-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="6e0de-164">Instrucción Return</span><span class="sxs-lookup"><span data-stu-id="6e0de-164">Return Statement</span></span>

<span data-ttu-id="6e0de-165">La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6e0de-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="6e0de-166">Consta de la palabra clave `return` , seguida de una expresión del tipo adecuado, y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="6e0de-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="6e0de-167">Un que se puede llamar que devuelve una tupla vacía, `()` , no requiere una instrucción return.</span><span class="sxs-lookup"><span data-stu-id="6e0de-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="6e0de-168">Si se desea una salida temprana, `return ()` se puede usar en este caso.</span><span class="sxs-lookup"><span data-stu-id="6e0de-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="6e0de-169">Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.</span><span class="sxs-lookup"><span data-stu-id="6e0de-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="6e0de-170">No hay ningún número máximo de instrucciones Return en una operación.</span><span class="sxs-lookup"><span data-stu-id="6e0de-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="6e0de-171">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="6e0de-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="6e0de-172">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="6e0de-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="6e0de-173">or</span><span class="sxs-lookup"><span data-stu-id="6e0de-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="6e0de-174">or</span><span class="sxs-lookup"><span data-stu-id="6e0de-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="6e0de-175">FAIL (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6e0de-175">Fail Statement</span></span>

<span data-ttu-id="6e0de-176">La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6e0de-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="6e0de-177">Consta de la palabra clave `fail` , seguida de una cadena y un punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="6e0de-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="6e0de-178">La cadena se devuelve al controlador clásico como el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6e0de-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="6e0de-179">No hay ninguna restricción en el número de instrucciones erróneas dentro de una operación.</span><span class="sxs-lookup"><span data-stu-id="6e0de-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="6e0de-180">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción FAIL dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="6e0de-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="6e0de-181">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="6e0de-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="6e0de-182">o bien, mediante [cadenas interpoladas](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="6e0de-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="6e0de-183">Ejemplos de repetir hasta el éxito</span><span class="sxs-lookup"><span data-stu-id="6e0de-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="6e0de-184">Patrón de RU para la rotación qubit única sobre un eje irracional</span><span class="sxs-lookup"><span data-stu-id="6e0de-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="6e0de-185">En un caso de uso típico, la siguiente operación de Q # implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt {5} $ en la esfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="6e0de-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="6e0de-186">Esto se logra mediante el uso de un patrón de RU conocido:</span><span class="sxs-lookup"><span data-stu-id="6e0de-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="6e0de-187">Bucle RUS con variable mutable en el ámbito</span><span class="sxs-lookup"><span data-stu-id="6e0de-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="6e0de-188">En este ejemplo se muestra el uso de una variable mutable `finished` que está en el ámbito de todo el bucle repeat-Until-fixup y que se inicializa antes del bucle y se actualiza en el paso de corrección.</span><span class="sxs-lookup"><span data-stu-id="6e0de-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="6e0de-189">RU sin`fixup`</span><span class="sxs-lookup"><span data-stu-id="6e0de-189">RUS without `fixup`</span></span>

<span data-ttu-id="6e0de-190">Por ejemplo, el código siguiente es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando las `H` `T` puertas y.</span><span class="sxs-lookup"><span data-stu-id="6e0de-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="6e0de-191">El bucle finaliza en las repeticiones de $ \frac {8} {5} $ en promedio.</span><span class="sxs-lookup"><span data-stu-id="6e0de-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="6e0de-192">Vea [*repetir hasta el éxito: descomposición no determinista de unitaries de un solo qubit*](https://arxiv.org/abs/1311.1074) (Paetznick y Svore, 2014) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="6e0de-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="6e0de-193">RU para preparar un estado de Quantum</span><span class="sxs-lookup"><span data-stu-id="6e0de-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="6e0de-194">Por último, se muestra un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partir del estado $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="6e0de-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="6e0de-195">Vea también el [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="6e0de-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

<span data-ttu-id="6e0de-196">Las características de programación más importantes que se muestran en esta operación son una parte más compleja `fixup` del bucle, que implica operaciones Quantum y el uso de `AssertProb` instrucciones para determinar la probabilidad de medir el estado de Quantum en determinados puntos especificados en el programa.</span><span class="sxs-lookup"><span data-stu-id="6e0de-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="6e0de-197">Vea también [pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging) para obtener más información sobre las [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operaciones y.</span><span class="sxs-lookup"><span data-stu-id="6e0de-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6e0de-198">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6e0de-198">Next steps</span></span>

<span data-ttu-id="6e0de-199">Obtenga información sobre las [pruebas y la depuración](xref:microsoft.quantum.guide.testingdebugging) en preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="6e0de-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>