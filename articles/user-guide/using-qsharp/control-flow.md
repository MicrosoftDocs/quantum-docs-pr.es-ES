---
title: 'Flujo de control en Q #'
description: Bucles, condicionales, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 0cf62a128170bd0c28ff77f00fc23414567b1ea4
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415310"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="64c4a-103">Flujo de control en Q #</span><span class="sxs-lookup"><span data-stu-id="64c4a-103">Control flow in Q#</span></span>

<span data-ttu-id="64c4a-104">Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a otros lenguajes imperativos habituales.</span><span class="sxs-lookup"><span data-stu-id="64c4a-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="64c4a-105">Sin embargo, puede modificar el flujo de control de tres maneras distintas:</span><span class="sxs-lookup"><span data-stu-id="64c4a-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="64c4a-106">`if`afirma</span><span class="sxs-lookup"><span data-stu-id="64c4a-106">`if` statements</span></span>
* <span data-ttu-id="64c4a-107">`for`bucles</span><span class="sxs-lookup"><span data-stu-id="64c4a-107">`for` loops</span></span>
* <span data-ttu-id="64c4a-108">`repeat-until-success`bucles</span><span class="sxs-lookup"><span data-stu-id="64c4a-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="64c4a-109">Las `if` `for` construcciones de flujo de control y continúan en un sentido familiar para la mayoría de los lenguajes de programación clásicas.</span><span class="sxs-lookup"><span data-stu-id="64c4a-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="64c4a-110">[`Repeat-until-success`](#repeat-until-success-loop)los bucles se describen más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="64c4a-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="64c4a-111">Lo importante es `for` que los bucles y `if` las instrucciones se pueden usar en operaciones para las que se generan automáticamente [especializaciones](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="64c4a-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="64c4a-112">En ese escenario, el contiguo de un `for` bucle invierte la dirección y toma el contiguo de cada iteración.</span><span class="sxs-lookup"><span data-stu-id="64c4a-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="64c4a-113">Esta acción sigue el principio "zapatos-y-Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS.</span><span class="sxs-lookup"><span data-stu-id="64c4a-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="64c4a-114">If, else-if, else</span><span class="sxs-lookup"><span data-stu-id="64c4a-114">If, Else-if, Else</span></span>

<span data-ttu-id="64c4a-115">La `if` instrucción admite la ejecución condicional.</span><span class="sxs-lookup"><span data-stu-id="64c4a-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="64c4a-116">Consta de la palabra clave `if` , una expresión booleana entre paréntesis y un bloque de instrucciones (el bloque _then_ ).</span><span class="sxs-lookup"><span data-stu-id="64c4a-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="64c4a-117">Opcionalmente, puede seguir cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif` , una expresión booleana entre paréntesis y un bloque de instrucciones (el bloque _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="64c4a-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="64c4a-118">Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguida de otro bloque de instrucciones (el bloque _else_ ).</span><span class="sxs-lookup"><span data-stu-id="64c4a-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="64c4a-119">La `if` condición se evalúa y, si es *true*, se ejecuta el bloque *then* .</span><span class="sxs-lookup"><span data-stu-id="64c4a-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="64c4a-120">Si la condición es *false*, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque *else-if* .</span><span class="sxs-lookup"><span data-stu-id="64c4a-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="64c4a-121">De lo contrario, el segundo bloque else-if evalúa y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición verdadera o no haya más cláusulas else-if.</span><span class="sxs-lookup"><span data-stu-id="64c4a-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="64c4a-122">Si la condición *If* original y todas las cláusulas else-if se evalúan como *false*, se ejecuta el bloque *else* , si se proporciona.</span><span class="sxs-lookup"><span data-stu-id="64c4a-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="64c4a-123">Tenga en cuenta que cualquier bloque se ejecuta, se ejecuta dentro de su propio ámbito.</span><span class="sxs-lookup"><span data-stu-id="64c4a-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="64c4a-124">Los enlaces realizados dentro de un `if` `elif` bloque, o `else` no están visibles una vez finalizado el bloque.</span><span class="sxs-lookup"><span data-stu-id="64c4a-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="64c4a-125">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="64c4a-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="64c4a-126">or</span><span class="sxs-lookup"><span data-stu-id="64c4a-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="64c4a-127">Bucle For</span><span class="sxs-lookup"><span data-stu-id="64c4a-127">For loop</span></span>

<span data-ttu-id="64c4a-128">La `for` instrucción admite la iteración sobre un intervalo de enteros o una matriz.</span><span class="sxs-lookup"><span data-stu-id="64c4a-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="64c4a-129">La instrucción consta de la palabra clave `for` , seguida de una tupla de símbolos o símbolos, la palabra clave `in` y una expresión de tipo `Range` o matriz, todos entre paréntesis y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="64c4a-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="64c4a-130">El bloque de instrucciones (el cuerpo del bucle) se ejecuta repetidamente, con el símbolo definido (la variable de bucle) enlazado a cada valor del intervalo o de la matriz.</span><span class="sxs-lookup"><span data-stu-id="64c4a-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="64c4a-131">Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecuta en absoluto.</span><span class="sxs-lookup"><span data-stu-id="64c4a-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="64c4a-132">La expresión se evalúa completamente antes de entrar en el bucle y no cambia mientras se ejecuta el bucle.</span><span class="sxs-lookup"><span data-stu-id="64c4a-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="64c4a-133">La variable de bucle se enlaza en cada entrada al cuerpo del bucle y se desenlaza al final del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="64c4a-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="64c4a-134">La variable de bucle no se enlaza una vez completado el bucle for.</span><span class="sxs-lookup"><span data-stu-id="64c4a-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="64c4a-135">El enlace de la variable de bucle es inmutable y sigue las mismas reglas que otros enlaces de variables.</span><span class="sxs-lookup"><span data-stu-id="64c4a-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="64c4a-136">En estos ejemplos, `qubits` es un registro de qubits (es decir, de tipo `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="64c4a-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="64c4a-137">Tenga en cuenta que al final, usamos el operador binario de desplazamiento aritmético a la izquierda, `<<<` .</span><span class="sxs-lookup"><span data-stu-id="64c4a-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="64c4a-138">Para obtener más información, vea [expresiones numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="64c4a-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="64c4a-139">Bucle repeat-Until-Success</span><span class="sxs-lookup"><span data-stu-id="64c4a-139">Repeat-until-success loop</span></span>

<span data-ttu-id="64c4a-140">El lenguaje Q # permite que el flujo de control clásico dependa de los resultados de la medición de qubits.</span><span class="sxs-lookup"><span data-stu-id="64c4a-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="64c4a-141">Esta capacidad, a su vez, habilita la implementación de gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.</span><span class="sxs-lookup"><span data-stu-id="64c4a-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="64c4a-142">Ejemplos de esto son los patrones de *repetición hasta la correcta* (RU) en Q #.</span><span class="sxs-lookup"><span data-stu-id="64c4a-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="64c4a-143">Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales. el costo incurrido depende de la ejecución real y del entrelazado de las distintas ramas posibles.</span><span class="sxs-lookup"><span data-stu-id="64c4a-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="64c4a-144">Para facilitar los patrones de repetición hasta la correcta (RU), Q # admite las construcciones</span><span class="sxs-lookup"><span data-stu-id="64c4a-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="64c4a-145">donde `expression` es cualquier expresión válida que se evalúe como un valor de tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="64c4a-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="64c4a-146">El cuerpo del bucle se ejecuta y, a continuación, se evalúa la condición.</span><span class="sxs-lookup"><span data-stu-id="64c4a-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="64c4a-147">Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se ejecuta de nuevo, comenzando por el cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="64c4a-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="64c4a-148">Las tres partes de un bucle RUS (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito *para cada repetición*, por lo que los símbolos que están enlazados en el cuerpo están disponibles tanto en la prueba como en la corrección.</span><span class="sxs-lookup"><span data-stu-id="64c4a-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="64c4a-149">Sin embargo, al finalizar la ejecución de la corrección finaliza el ámbito de la instrucción, de modo que los enlaces de símbolos realizados durante el cuerpo o la corrección no estén disponibles en las repeticiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="64c4a-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="64c4a-150">Además, la `fixup` instrucción suele ser útil pero no siempre es necesaria.</span><span class="sxs-lookup"><span data-stu-id="64c4a-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="64c4a-151">En los casos en los que no es necesario, la construcción</span><span class="sxs-lookup"><span data-stu-id="64c4a-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="64c4a-152">también es un patrón de RUS válido.</span><span class="sxs-lookup"><span data-stu-id="64c4a-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="64c4a-153">Para obtener más ejemplos y detalles, consulte los [ejemplos de repetición hasta](#repeat-until-success-examples) la finalización correcta de este artículo.</span><span class="sxs-lookup"><span data-stu-id="64c4a-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="64c4a-154">Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="64c4a-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="64c4a-155">Use bucles *While* para proporcionar la funcionalidad correspondiente dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="64c4a-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="64c4a-156">While (bucle)</span><span class="sxs-lookup"><span data-stu-id="64c4a-156">While loop</span></span>

<span data-ttu-id="64c4a-157">Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum.</span><span class="sxs-lookup"><span data-stu-id="64c4a-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="64c4a-158">Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q #.</span><span class="sxs-lookup"><span data-stu-id="64c4a-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="64c4a-159">Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación, se controlan con especial atención en un tiempo de ejecución de Quantum.</span><span class="sxs-lookup"><span data-stu-id="64c4a-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="64c4a-160">Sin embargo, su uso dentro de las funciones es inproblemático, ya que estos bucles solo contienen código que se ejecuta en hardware convencional (no Quantum).</span><span class="sxs-lookup"><span data-stu-id="64c4a-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="64c4a-161">P #, por lo tanto, admite el uso de bucles while solo dentro de funciones.</span><span class="sxs-lookup"><span data-stu-id="64c4a-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="64c4a-162">Una `while` instrucción consta de la palabra clave `while` , una expresión booleana entre paréntesis y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="64c4a-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="64c4a-163">El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true` .</span><span class="sxs-lookup"><span data-stu-id="64c4a-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="64c4a-164">Instrucción Return</span><span class="sxs-lookup"><span data-stu-id="64c4a-164">Return Statement</span></span>

<span data-ttu-id="64c4a-165">La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="64c4a-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="64c4a-166">Consta de la palabra clave `return` , seguida de una expresión del tipo adecuado, y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="64c4a-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="64c4a-167">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="64c4a-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="64c4a-168">or</span><span class="sxs-lookup"><span data-stu-id="64c4a-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="64c4a-169">Un que se puede llamar que devuelve una tupla vacía, `()` , no requiere una instrucción return.</span><span class="sxs-lookup"><span data-stu-id="64c4a-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="64c4a-170">Para especificar una salida temprana de la operación o la función, use `return ();` .</span><span class="sxs-lookup"><span data-stu-id="64c4a-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="64c4a-171">Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.</span><span class="sxs-lookup"><span data-stu-id="64c4a-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="64c4a-172">No hay ningún número máximo de instrucciones Return en una operación.</span><span class="sxs-lookup"><span data-stu-id="64c4a-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="64c4a-173">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="64c4a-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="64c4a-174">FAIL (instrucción)</span><span class="sxs-lookup"><span data-stu-id="64c4a-174">Fail statement</span></span>

<span data-ttu-id="64c4a-175">La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="64c4a-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="64c4a-176">Consta de la palabra clave `fail` , seguida de una cadena y un punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="64c4a-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="64c4a-177">La instrucción devuelve la cadena al controlador clásico como el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="64c4a-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="64c4a-178">No hay ninguna restricción en el número de instrucciones erróneas dentro de una operación.</span><span class="sxs-lookup"><span data-stu-id="64c4a-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="64c4a-179">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción FAIL dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="64c4a-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="64c4a-180">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="64c4a-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="64c4a-181">o bien, mediante [cadenas interpoladas](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="64c4a-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="64c4a-182">Ejemplos de repetir hasta el éxito</span><span class="sxs-lookup"><span data-stu-id="64c4a-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="64c4a-183">Patrón de RU para la rotación de un solo qubit sobre un eje de irracional</span><span class="sxs-lookup"><span data-stu-id="64c4a-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="64c4a-184">En un caso de uso típico, la siguiente operación de Q # implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt {5} $ en la esfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="64c4a-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="64c4a-185">La implementación usa un patrón de RU conocido:</span><span class="sxs-lookup"><span data-stu-id="64c4a-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="64c4a-186">Bucle RUS con una variable mutable en el ámbito</span><span class="sxs-lookup"><span data-stu-id="64c4a-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="64c4a-187">En este ejemplo se muestra el uso de una variable mutable, `finished` , que está dentro del ámbito de todo el bucle repeat-Until-fixup y que se inicializa antes del bucle y se actualiza en el paso de corrección.</span><span class="sxs-lookup"><span data-stu-id="64c4a-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="64c4a-188">RU sin`fixup`</span><span class="sxs-lookup"><span data-stu-id="64c4a-188">RUS without `fixup`</span></span>

<span data-ttu-id="64c4a-189">En este ejemplo se muestra un bucle RUS sin el paso de corrección.</span><span class="sxs-lookup"><span data-stu-id="64c4a-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="64c4a-190">El código es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando las `H` `T` puertas y.</span><span class="sxs-lookup"><span data-stu-id="64c4a-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="64c4a-191">El bucle finaliza en las repeticiones de $ \frac {8} {5} $ en promedio.</span><span class="sxs-lookup"><span data-stu-id="64c4a-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="64c4a-192">Vea [*repetir hasta el éxito: descomposición no determinista de unitaries de un solo qubit*](https://arxiv.org/abs/1311.1074) (Paetznick y Svore, 2014) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="64c4a-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="64c4a-193">RU para preparar un estado de Quantum</span><span class="sxs-lookup"><span data-stu-id="64c4a-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="64c4a-194">Por último, este es un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partir del estado $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="64c4a-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="64c4a-195">Las características de programación más importantes que se muestran en esta operación son:</span><span class="sxs-lookup"><span data-stu-id="64c4a-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="64c4a-196">Una parte más compleja `fixup` del bucle, que implica operaciones Quantum.</span><span class="sxs-lookup"><span data-stu-id="64c4a-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="64c4a-197">El uso de `AssertProb` instrucciones para determinar la probabilidad de medir el estado de Quantum en determinados puntos especificados en el programa.</span><span class="sxs-lookup"><span data-stu-id="64c4a-197">The use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="64c4a-198">Para obtener más información sobre [`Assert`](xref:microsoft.quantum.intrinsic.assert) las [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operaciones y, vea [probar y depurar](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="64c4a-198">For more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

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

<span data-ttu-id="64c4a-199">Para obtener más información, vea [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="64c4a-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="64c4a-200">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="64c4a-200">Next steps</span></span>

<span data-ttu-id="64c4a-201">Obtenga información sobre las [pruebas y la depuración](xref:microsoft.quantum.guide.testingdebugging) en preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="64c4a-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
