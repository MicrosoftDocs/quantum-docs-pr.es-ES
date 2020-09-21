---
title: Flujo de control en Q#
description: Bucles, condicionales, etc.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833512"
---
# <a name="control-flow-in-no-locq"></a>Flujo de control en Q#

Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a otros lenguajes imperativos habituales.
Sin embargo, puede modificar el flujo de control de tres maneras distintas:

* `if` afirma
* `for` bucles
* `repeat-until-success` bucles
* conjugados ( `apply-within` instrucciones)

Las `if` `for` construcciones de flujo de control y continúan en un sentido familiar para la mayoría de los lenguajes de programación clásicas. [`Repeat-until-success`](#repeat-until-success-loop) los bucles y [conjugaciones](#conjugations) se describen más adelante en este artículo.

Lo importante es `for` que los bucles y `if` las instrucciones se pueden usar en operaciones para las que se generan automáticamente [especializaciones](xref:microsoft.quantum.guide.operationsfunctions) . En ese escenario, el contiguo de un `for` bucle invierte la dirección y toma el contiguo de cada iteración.
Esta acción sigue el principio "zapatos-y-Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS. 

## <a name="if-else-if-else"></a>If, else-if, else

La `if` instrucción admite el procesamiento condicional.
Consta de la palabra clave `if` , una expresión booleana entre paréntesis y un bloque de instrucciones (el bloque _then_ ).
Opcionalmente, puede seguir cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif` , una expresión booleana entre paréntesis y un bloque de instrucciones (el bloque _else-if_ ).
Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguida de otro bloque de instrucciones (el bloque _else_ ).

La `if` condición se evalúa y, si es *true*, se ejecuta el bloque *then* .
Si la condición es *false*, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque *else-if* .
De lo contrario, el segundo bloque else-if evalúa y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición verdadera o no haya más cláusulas else-if.
Si la condición *If* original y todas las cláusulas else-if se evalúan como *false*, se ejecuta el bloque *else* , si se proporciona.

Tenga en cuenta que cualquier bloque se ejecuta, se ejecuta dentro de su propio ámbito.
Los enlaces realizados dentro de un `if` `elif` bloque, o `else` no están visibles una vez finalizado el bloque.

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

La `for` instrucción admite la iteración sobre un intervalo de enteros o una matriz.
La instrucción consta de la palabra clave `for` , seguida de una tupla de símbolos o símbolos, la palabra clave `in` y una expresión de tipo `Range` o matriz, todos entre paréntesis y un bloque de instrucciones.

El bloque de instrucciones (el cuerpo del bucle) se ejecuta repetidamente, con el símbolo definido (la variable de bucle) enlazado a cada valor del intervalo o de la matriz.
Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecuta en absoluto.
La expresión se evalúa completamente antes de entrar en el bucle y no cambia mientras se ejecuta el bucle.

La variable de bucle se enlaza en cada entrada al cuerpo del bucle y se desenlaza al final del cuerpo.
La variable de bucle no se enlaza una vez completado el bucle for.
El enlace de la variable de bucle es inmutable y sigue las mismas reglas que otros enlaces de variables. 

En estos ejemplos, `qubits` es un registro de qubits (es decir, de tipo `Qubit[]` ). 

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

Tenga en cuenta que al final, usamos el operador binario de desplazamiento aritmético a la izquierda, `<<<` . Para obtener más información, vea [expresiones numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Bucle repeat-Until-Success

El Q# lenguaje permite que el flujo de control clásico dependa de los resultados de la medición de qubits.
Esta capacidad, a su vez, habilita la implementación de gadgets de probabilística eficaces que pueden reducir el costo computacional de la implementación de unitaries.
Ejemplos de esto son los patrones de *repetición hasta la correcta* (RU) en Q# .
Estos patrones de RUS son programas probabilística que tienen un costo bajo *previsto* en cuanto a las puertas elementales. el costo incurrido depende de la ejecución real y del entrelazado de las distintas ramas posibles.

Para facilitar los patrones de repetición hasta éxito (RU), Q# admite las construcciones

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
El cuerpo del bucle se ejecuta y, a continuación, se evalúa la condición.
Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se ejecuta de nuevo, comenzando por el cuerpo del bucle.

Las tres partes de un bucle RUS (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito *para cada repetición*, por lo que los símbolos que están enlazados en el cuerpo están disponibles tanto en la prueba como en la corrección.
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

Para obtener más ejemplos y detalles, consulte los [ejemplos de repetición hasta](#repeat-until-success-examples) la finalización correcta de este artículo.

> [!TIP]   
> Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones. Use bucles *While* para proporcionar la funcionalidad correspondiente dentro de las funciones. 

## <a name="while-loop"></a>Bucle while

Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum. Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q# . Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación, se controlan con especial atención en un tiempo de ejecución de Quantum. Sin embargo, su uso dentro de las funciones es inproblemático, ya que estos bucles solo contienen código que se ejecuta en hardware convencional (no Quantum). 

Q#, por lo tanto, admite el uso de bucles while solo dentro de funciones.
Una `while` instrucción consta de la palabra clave `while` , una expresión booleana entre paréntesis y un bloque de instrucciones.
El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>Conjugaciones

A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito. Estos efectos se pueden evitar al "deshacer" correctamente los cálculos realizados antes de liberar la memoria. Un patrón común en la informática Quantum es, por lo tanto, lo siguiente: 

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

Q# admite una instrucción de conjugación que implementa la transformación anterior. Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:

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
Esta instrucción de conjugación resulta útil si las transformaciones externas e internas no están disponibles como operaciones, sino que son más convenientes de describir en un bloque que consta de varias instrucciones. 

El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply.
Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de. 

## <a name="return-statement"></a>Instrucción Return

La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.
Consta de la palabra clave `return` , seguida de una expresión del tipo adecuado, y un punto y coma de finalización.

Por ejemplo,
```qsharp
return 1;
```
o
```qsharp
return (results, qubits);
```

* Un que se puede llamar que devuelve una tupla vacía, `()` , no requiere una instrucción return.
* Para especificar una salida temprana de la operación o la función, use `return ();` .
Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.
* No hay ningún número máximo de instrucciones Return en una operación.
El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.

   
## <a name="fail-statement"></a>FAIL (instrucción)

La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.
Consta de la palabra clave `fail` , seguida de una cadena y un punto y coma de terminación.
La instrucción devuelve la cadena al controlador clásico como el mensaje de error.

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

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Patrón de RU para la rotación de un solo qubit sobre un eje de irracional 

En un caso de uso típico, la Q# operación siguiente implementa una rotación alrededor de un eje irracional de $ (I + 2i Z)/\sqrt {5} $ en la esfera Bloch. La implementación usa un patrón de RU conocido:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Bucle RUS con una variable mutable en el ámbito

En este ejemplo se muestra el uso de una variable mutable, `finished` , que está dentro del ámbito de todo el bucle repeat-Until-fixup y que se inicializa antes del bucle y se actualiza en el paso de corrección.

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

### <a name="rus-without-fixup"></a>RU sin `fixup`

En este ejemplo se muestra un bucle RUS sin el paso de corrección. El código es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando las `H` `T` puertas y.
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

Por último, este es un ejemplo de un patrón de RU para preparar un estado de Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partir del estado $ \ket{+} $.

Las características de programación más importantes que se muestran en esta operación son:

* Una parte más compleja `fixup` del bucle, que implica operaciones Quantum. 
* El uso de `AssertMeasurementProbability` instrucciones para determinar la probabilidad de medir el estado de Quantum en determinados puntos especificados en el programa.

Para obtener más información sobre [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) las [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operaciones y, vea [probar y depurar](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

Para obtener más información, vea [ejemplo de pruebas unitarias que se proporciona con la biblioteca estándar](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre las [pruebas y la depuración](xref:microsoft.quantum.guide.testingdebugging) en Q# .
