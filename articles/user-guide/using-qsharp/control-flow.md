---
title: 'Flujo de control en Q #'
description: Bucles, condicionales, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430958"
---
# <a name="control-flow-in-q"></a>Flujo de control en Q #

Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a la mayoría de los lenguajes imperativos más comunes.
Este flujo de control se puede modificar, sin embargo, de tres maneras distintas:

- `if`afirma
- `for`bucles
- `repeat`-`until`bucles

Aplazamos la explicación de este último para más [adelante](#repeat-until-success-loop).
`if`Sin embargo, las construcciones de flujo de control y `for` continúan en un sentido familiar para la mayoría de los lenguajes de programación clásicas.

Lo importante es `for` que los bucles y `if` las instrucciones se pueden usar incluso en operaciones para las que se generan automáticamente especializaciones. En ese caso, el contiguo de un `for` bucle invierte la dirección y toma el contiguo de cada iteración.
Esto sigue el principio de "zapatos y Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS.
Funciona a la medida de que sea un poco bien para probar y sacar su Socks mientras sigue usando sus zapatos.

## <a name="if-else-if-else"></a>If, else-if, else

La `if` instrucción admite la ejecución condicional.
Consta de la palabra clave `if` , un paréntesis de apertura `(` , una expresión booleana, un paréntesis de cierre `)` y un bloque de instrucciones (el bloque _then_ ).
Esto puede ir seguido de cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif` , un paréntesis de apertura `(` , una expresión booleana, un paréntesis de cierre `)` y un bloque de instrucciones (el bloque _else-if_ ).
Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguida de otro bloque de instrucciones (el bloque _else_ ).

La `if` condición se evalúa y, si es true, se ejecuta el bloque then.
Si la condición es false, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque else-if.
De lo contrario, el segundo bloque else-if se prueba y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición true o no haya más cláusulas else-if.
Si las cláusulas IF original y All else-if se evalúan como false, el bloque else se ejecutará si se proporciona uno.

Tenga en cuenta que el bloque que se ejecuta se ejecuta en su propio ámbito.
Los enlaces realizados dentro de un `if` `elif` bloque, o `else` no son visibles después del final.

Por ejemplo,

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
o
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

## <a name="for-loop"></a>Bucle For

La `for` instrucción admite la iteración en un intervalo de enteros o en una matriz.
La instrucción consta de la palabra clave `for` , un paréntesis `(` de apertura, seguido de una tupla de símbolos o símbolos, la palabra clave `in` , una expresión de tipo `Range` o matriz, un paréntesis de cierre `)` y un bloque de instrucciones.

El bloque de instrucciones (el cuerpo del bucle) se ejecuta varias veces, con los símbolos definidos (las variables de bucle) enlazados a cada valor del intervalo o de la matriz.
Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecutará en absoluto.
La expresión se evalúa completamente antes de entrar en el bucle y no cambiará mientras se ejecuta el bucle.

La variable de bucle se enlaza en cada entrada al cuerpo del bucle y sin enlazar al final del cuerpo.
En concreto, la variable de bucle no se enlaza una vez completado el bucle for.
El enlace de los símbolos declarados es inmutable y sigue las mismas reglas que otros enlaces de variables. 

En algunos ejemplos, suponiendo `qubits` es un registro de qubits (es decir, de tipo `Qubit[]` ). 

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
Tenga en cuenta que al final usamos el operador binario de desplazamiento aritmético a la izquierda, `<<<` , detalles de los que se pueden encontrar en [expresiones numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions) .


## <a name="repeat-until-success-loop"></a>Bucle repeat-Until-Success

El lenguaje Q # permite que el flujo de control clásico dependa de los resultados de la medición de qubits.
Esta funcionalidad, a su vez, permite implementar gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.
Por ejemplo, es fácil implementar los modelos de *repetición-hasta el éxito* (RU) que se conocen en Q #.
Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales, pero para los que el costo real depende de una ejecución real y una intercalación real de varias ramas posibles.

Para facilitar los patrones de repetición hasta la correcta (RU), Q # admite las construcciones

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

donde `expression` es cualquier expresión válida que se evalúe como un valor de tipo `Bool` .
Se ejecuta el cuerpo del bucle y, a continuación, se evalúa la condición.
Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se vuelve a ejecutar empezando por el cuerpo del bucle.

Las tres partes de un bucle repeat/Until (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito *para cada repetición*, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y en la corrección.
Sin embargo, al finalizar la ejecución de la corrección finaliza el ámbito de la instrucción, de modo que los enlaces de símbolos realizados durante el cuerpo o la corrección no estén disponibles en las repeticiones posteriores.

Además, la `fixup` instrucción suele ser útil pero no siempre es necesaria.
En los casos en los que no es necesario, la construcción
```qsharp
repeat {
    // do stuff
}
until (expression);
```
también es un patrón de RUS válido.

En la parte inferior de esta página, presentamos algunos [ejemplos de bucles Rus](#repeat-until-success-examples).

> [!TIP]   
> Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones. La funcionalidad correspondiente la proporcionan los bucles while en las funciones. 

## <a name="while-loop"></a>While (bucle)

Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum. Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q #. Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación deben controlarse con especial atención en un tiempo de ejecución de Quantum. El uso de las funciones por otro lado no es problemático, ya que solo contienen código que se ejecutará en hardware convencional (no Quantum). 

Por lo tanto, Q # solo admite el uso de bucles while dentro de funciones. Una `while` instrucción consta de la palabra clave `while` , un paréntesis de apertura `(` , una condición (es decir, una expresión booleana), un paréntesis de cierre `)` y un bloque de instrucciones.
El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Instrucción Return

La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.
Consta de la palabra clave `return` , seguida de una expresión del tipo adecuado, y un punto y coma de finalización.

Un que se puede llamar que devuelve una tupla vacía, `()` , no requiere una instrucción return.
Si se desea una salida temprana, `return ()` se puede usar en este caso.
Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.

No hay ningún número máximo de instrucciones Return en una operación.
El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.

Por ejemplo,
```qsharp
return 1;
```
o
```qsharp
return ();
```
o
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>FAIL (instrucción)

La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.
Consta de la palabra clave `fail` , seguida de una cadena y un punto y coma de terminación.
La cadena se devuelve al controlador clásico como el mensaje de error.

No hay ninguna restricción en el número de instrucciones erróneas dentro de una operación.
El compilador puede emitir una advertencia si las instrucciones siguen una instrucción FAIL dentro de un bloque.

Por ejemplo,
```qsharp
fail $"Impossible state reached";
```
o bien, mediante [cadenas interpoladas](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Ejemplos de repetir hasta el éxito

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Patrón de RU para la rotación qubit única sobre un eje irracional 

En un caso de uso típico, la siguiente operación de Q # implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt {5} $ en la esfera Bloch. Esto se logra mediante el uso de un patrón de RU conocido:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Bucle RUS con variable mutable en el ámbito

En este ejemplo se muestra el uso de una variable mutable `finished` que está en el ámbito de todo el bucle repeat-Until-fixup y que se inicializa antes del bucle y se actualiza en el paso de corrección.

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

### <a name="rus-without-fixup"></a>RU sin`fixup`

Por ejemplo, el código siguiente es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando las `H` `T` puertas y.
El bucle finaliza en las repeticiones de $ \frac {8} {5} $ en promedio.
Vea [*repetir hasta el éxito: descomposición no determinista de unitaries de un solo qubit*](https://arxiv.org/abs/1311.1074) (Paetznick y Svore, 2014) para obtener más detalles.

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

### <a name="rus-to-prepare-a-quantum-state"></a>RU para preparar un estado de Quantum

Por último, se muestra un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partir del estado $ \ket{+} $.
Vea también el [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

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

Las características de programación más importantes que se muestran en esta operación son una parte más compleja `fixup` del bucle, que implica operaciones Quantum y el uso de `AssertProb` instrucciones para determinar la probabilidad de medir el estado de Quantum en determinados puntos especificados en el programa.
Vea también [pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging) para obtener más información sobre las [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operaciones y.


## <a name="whats-next"></a>¿Qué debe hacer a continuación?
Obtenga información sobre las [pruebas y la depuración](xref:microsoft.quantum.guide.testingdebugging) en preguntas y respuestas.