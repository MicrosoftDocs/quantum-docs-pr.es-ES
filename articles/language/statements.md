---
title: 'Instrucciones Q # | Microsoft Docs'
description: 'Instrucciones Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036498"
---
# <a name="statements-and-other-constructs"></a>Instrucciones y otras construcciones

## <a name="comments"></a>Comentarios

Los comentarios comienzan con dos barras diagonales, `//`y continúan hasta el final de la línea.
Puede aparecer un Comentario en cualquier parte de un archivo de código fuente de preguntas y respuestas.

### <a name="documentation-comments"></a>Comentarios de documentación

Los comentarios que comienzan con tres barras diagonales, `///`, se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.
En ese caso, su contenido se toma como documentación para el tipo definido por el usuario o al que se puede llamar, como en otros lenguajes .NET.

Dentro de `///` comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), con distintas partes de la documentación que se indican mediante encabezados con el nombre especial.
Como extensión de Markdown, se pueden incluir referencias cruzadas a operaciones, funciones y tipos definidos por el usuario en Q # mediante el `@"<ref target>"`, donde `<ref target>` se reemplaza por el nombre completo del objeto de código al que se hace referencia.
Opcionalmente, un motor de documentación también puede admitir extensiones de Markdown adicionales.

Por ejemplo:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Los nombres siguientes se reconocen como encabezados de comentario de documentación.

- **Summary**: un breve resumen del comportamiento de una función u operación, o del propósito de un tipo. El primer párrafo del resumen se usa para la información de desplazamiento. Debe ser texto sin formato.
- **Descripción**: Descripción del comportamiento de una función u operación, o del propósito de un tipo. El Resumen y la descripción se concatenan para formar el archivo de documentación generado para la función, la operación o el tipo.
  La descripción puede contener símbolos y ecuaciones con formato LaTeX en línea.
- **Input**: Descripción de la tupla de entrada para una operación o función.
  Puede contener subsecciones de Markdown adicionales que indican cada elemento individual de la tupla de entrada.
- **Output**: Descripción de la tupla devuelta por una operación o función.
- **Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.
- **Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.
- **Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.
- **Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.
- **Referencias**: una lista de referencias y citas para el elemento que se documenta.

## <a name="namespaces"></a>Espacios de nombres

Cada operación Q #, función y tipo definido por el usuario se definen dentro de un espacio de nombres.
Q # sigue las mismas reglas para asignar nombres a otros lenguajes .NET.
Sin embargo, Q # no admite referencias relativas a espacios de nombres.
Es decir, si se ha abierto el espacio de nombres `a.b`, una referencia a un nombre de operación `c.d` no se resolverá en una operación con el nombre completo `a.b.c.d`.

Dentro de un bloque de espacio de nombres, la Directiva `open` se puede usar para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo. Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido. La Directiva `open` se aplica a todo el bloque de espacio de nombres dentro de un archivo.

Se debe hacer referencia a un tipo o al que se puede llamar en otro espacio de nombres que no esté abierto en el espacio de nombres actual mediante su nombre completo.
Por ejemplo, se debe hacer referencia a una operación denominada `Op` en el espacio de nombres `X.Y` mediante su nombre completo `X.Y.Op`, a menos que el espacio de nombres de `X.Y` se haya abierto anteriormente en el bloque actual. Como se mencionó anteriormente, incluso si se ha abierto el espacio de nombres `X`, no es posible hacer referencia a la operación como `Y.Op`.
Si se ha definido un nombre corto `Z` para `X.Y` en ese espacio de nombres y archivo, se debe hacer referencia a `Op` como `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Normalmente es mejor incluir un espacio de nombres mediante una directiva de `open`.
Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.

## <a name="formatting"></a>Aplicación de formato

La mayoría de las instrucciones y directivas de Q # finalizan con un punto y coma de terminación, `;`.
Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones no requieren un punto y coma de finalización.
La descripción de cada instrucción indica si es necesario el punto y coma de terminación.

Las instrucciones, como las expresiones, las declaraciones y las directivas, pueden dividirse en varias líneas.
Se debe evitar tener varias instrucciones en una sola línea.

## <a name="statement-blocks"></a>Bloques de instrucciones

Las instrucciones Q # se agrupan en bloques de instrucciones.
Un bloque de instrucciones comienza con un `{` de apertura y termina con un `}`de cierre.

Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.

## <a name="symbol-binding-and-assignment"></a>Enlace y asignación de símbolos

Q # distingue entre símbolos mutables e inmutables.
En general, se recomienda el uso de símbolos inmutables porque permite que el compilador realice más optimizaciones.

La parte izquierda del enlace se compone de una tupla de símbolos y del lado derecho de una expresión.

Dado que todos los tipos de Q # son tipos de valor, con el qubits que toma un rol especialmente especial: se crea una "copia" formalmente cuando se enlaza un valor a un símbolo o cuando se reenlaza un símbolo. Es decir, el comportamiento de Q # es el mismo que si se creara una copia en la asignación. Esto, en concreto, también incluye matrices. Por supuesto, en la práctica solo se recrean las piezas relevantes según sea necesario. 

### <a name="tuple-deconstruction"></a>Desconstrucción de tuplas

Si el lado derecho del enlace es una tupla, esa tupla se puede desconstruir en el momento de la asignación.
Estas desconstrucciones pueden implicar tuplas anidadas, y cualquier desconstrucción parcial o completa es válida siempre y cuando la forma de la tupla en el lado derecho sea compatible con la forma de la tupla de símbolos.
La desconstrucción de tuplas se puede usar en concreto también cuando el lado derecho del `=` es una expresión de valor de tupla.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Símbolos inmutables

Los símbolos inmutables se enlazan mediante la instrucción `let`.
Esto es aproximadamente equivalente a la declaración y la inicialización de variables C#en lenguajes como, excepto en que los símbolos de Q #, una vez enlazados, no se pueden cambiar. `let` enlaces son inmutables.

Un enlace inmutable se compone de la palabra clave `let`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión para enlazar los símbolos a y un punto y coma de finalización.
El tipo de los símbolos enlazados se infiere en función de la expresión del lado derecho.

### <a name="mutable-symbols"></a>Símbolos mutables

Los símbolos mutables se definen y se inicializan mediante la instrucción `mutable`.
Los símbolos declarados y enlazados como parte de una instrucción `mutable` se pueden volver a enlazar a un valor diferente más adelante en el código. 

Una instrucción de enlace mutable se compone de la palabra clave `mutable`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión para enlazar los símbolos a y un punto y coma de finalización.
El tipo de los símbolos enlazados se infiere en función de la expresión del lado derecho. Si un símbolo se reenlaza posteriormente en el código, su tipo no cambia y el valor enlazado debe ser compatible con ese tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reenlazar símbolos mutables

Una variable mutable se puede reenlazar mediante una instrucción `set`.
Este tipo de reenlace consta de la palabra clave `set`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión a la que se deben volver a enlazar los símbolos y un punto y coma de finalización.
El valor debe ser compatible con los tipos de los símbolos a los que está enlazado.

#### <a name="apply-and-reassign-statement"></a>Apply-and-resign (instrucción)

Una clase concreta de Set-Statement a la que se hace referencia como una instrucción Apply-and-resign proporciona una forma cómoda de concatenación si el lado derecho está compuesto por la aplicación de un operador binario y el resultado se va a volver a enlazar al argumento izquierdo al operador. Por ejemplo,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa el valor del contador `counter` en cada iteración del bucle de `for`. El código anterior es equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Las instrucciones similares están disponibles para todos los operadores binarios en los que el tipo del lado izquierdo coincide con el tipo de expresión. Esto proporciona, por ejemplo, una manera cómoda de acumular valores:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Update-and-resign (instrucción)

Existe una concatenación similar para las expresiones de copia y actualización en el lado derecho. En consecuencia, las instrucciones Update-and-resign existen para los elementos con nombre de los tipos definidos por el usuario, así como para los elementos de matriz.  

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

En el caso de las matrices, nuestras bibliotecas estándar contienen las herramientas necesarias para muchas necesidades comunes de inicialización y manipulación de matrices y, por tanto, ayudan a evitar tener que actualizar los elementos de la matriz en primer lugar. Las instrucciones Update-and-resign proporcionan una alternativa si es necesario:

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

> [!TIP]   
> Evite el uso innecesario de las instrucciones de actualización y reasignación aprovechando las herramientas proporcionadas en <xref:microsoft.quantum.arrays>.

La función
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
por ejemplo, se puede simplificar simplemente con la función `ConstantArray` en `Microsoft.Quantum.Arrays`y devolver una expresión de copia y actualización:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Ámbitos de enlace

En general, los enlaces de símbolos salen del ámbito y quedan inoperativos al final del bloque de instrucciones en el que se encuentran.
Esta regla tiene dos excepciones:

- El enlace de la variable de bucle de un bucle `for` está en el ámbito del cuerpo del bucle for, pero no después del final del bucle.
- Las tres partes de una `repeat`/bucle `until` (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y en la corrección.

En ambos tipos de bucles, cada paso a través del bucle se ejecuta en su propio ámbito, por lo que los enlaces de un paso anterior no están disponibles en un paso posterior.

Los enlaces de símbolos de los bloques externos los heredan los bloques internos.
Un símbolo solo se puede enlazar una vez por bloque; no es válido definir un símbolo con el mismo nombre que otro símbolo que está dentro del ámbito (sin "sombreado").
Las secuencias siguientes serían válidas:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

y

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
```

Pero esto sería ilegal:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

como sería:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>Flujo de control

### <a name="for-loop"></a>Bucle For

La instrucción `for` admite la iteración en un intervalo de enteros o en una matriz.
La instrucción consta de la palabra clave `for`, un paréntesis de apertura `(`, seguido de una tupla de símbolos o símbolos, la palabra clave `in`, una expresión de tipo `Range` o array, un paréntesis de cierre `)`y un bloque de instrucciones.

El bloque de instrucciones (el cuerpo del bucle) se ejecuta varias veces, con los símbolos definidos (las variables de bucle) enlazados a cada valor del intervalo o de la matriz.
Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecutará en absoluto.
La expresión se evalúa completamente antes de entrar en el bucle y no cambiará mientras se ejecuta el bucle.

El enlace de los símbolos declarados es inmutable y sigue las mismas reglas que otros enlaces de variables. En concreto, es posible desestructurar, por ejemplo, los elementos de matriz de una iteración en una matriz cuando se asignan a las variables de bucle.

Por ejemplo,

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

La variable de bucle se enlaza en cada entrada al cuerpo del bucle y sin enlazar al final del cuerpo.
En concreto, la variable de bucle no se enlaza una vez completado el bucle for.

### <a name="repeat-until-success-loop"></a>Bucle repeat-Until-Success

La instrucción `repeat` admite el patrón "repetir hasta el éxito".
Consta de la palabra clave `repeat`, seguida de un bloque de instrucciones (el cuerpo del _bucle_ ), la palabra clave `until`, una expresión booleana y un punto y coma de terminación o la palabra clave `fixup` seguido de otro bloque de instrucciones (la _corrección_).
El cuerpo, la condición y la corrección del bucle se consideran un solo ámbito, por lo que los símbolos enlazados en el cuerpo están disponibles en la condición y la corrección.

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

Se ejecuta el cuerpo del bucle y, a continuación, se evalúa la condición.
Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se vuelve a ejecutar empezando por el cuerpo del bucle.
Tenga en cuenta que al completar la ejecución de la corrección finaliza el ámbito de la instrucción, de modo que los enlaces de símbolos realizados durante el cuerpo o la corrección no estén disponibles en las repeticiones posteriores.

Por ejemplo, el código siguiente es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando las puertas Hadamard y T.
El bucle finaliza en $ \frac{8}{5}$ repeticiones en promedio.
Vea [*repetir hasta el éxito: descomposición no determinista de unitaries de un solo qubit*](https://arxiv.org/abs/1311.1074) (Paetznick y Svore, 2014) para obtener más información.

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

> [!TIP]   
> Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones. La funcionalidad correspondiente la proporcionan los bucles while en las funciones. 

### <a name="while-loop"></a>While (bucle)

Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum. Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q #. Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación deben controlarse con especial atención en un tiempo de ejecución de Quantum. El uso de las funciones por otro lado no es problemático, ya que solo contienen código que se ejecutará en hardware convencional (no Quantum). 

Por lo tanto, Q # solo admite el uso de bucles while dentro de funciones. Una instrucción `while` consta de la palabra clave `while`, un paréntesis de apertura `(`, una condición (es decir, una expresión booleana), un paréntesis de cierre `)`y un bloque de instrucciones.
El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Instrucción condicional

La instrucción `if` admite la ejecución condicional.
Consta de la palabra clave `if`, un paréntesis de apertura `(`, una expresión booleana, un paréntesis de cierre `)`y un bloque de instrucciones (el bloque _then_ ).
Esto puede ir seguido de cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif`, un `(`de paréntesis de apertura, una expresión booleana, un paréntesis de cierre `)`y un bloque de instrucciones (el bloque _else-if_ ).
Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguido de otro bloque de instrucciones (el bloque _else_ ).
La condición se evalúa y, si es true, se ejecuta el bloque then.
Si la condición es false, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque else-if.
De lo contrario, el segundo bloque else-if se prueba y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición true o no haya más cláusulas else-if.
Si las cláusulas IF original y All else-if se evalúan como false, el bloque else se ejecutará si se proporciona uno.

Tenga en cuenta que el bloque que se ejecuta se ejecuta en su propio ámbito.
Los enlaces realizados dentro de un bloque then, else-if o else no están visibles después del final de la instrucción if.

Por ejemplo,

```qsharp
if (result == One) {
    X(target);
} 
```

or

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Valor devuelto

La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.
Consta de la palabra clave `return`, seguida de una expresión del tipo adecuado y un punto y coma de finalización.

Un que se puede llamar que devuelve una tupla vacía, `()`, no requiere una instrucción return.
Si se desea una salida temprana, se puede usar `return ()` en este caso.
Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.

No hay ningún número máximo de instrucciones Return en una operación.
El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.

Por ejemplo,

```qsharp
return 1;
```

or

```qsharp
return ();
```

or

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Incorrecto

La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.
Consta de la palabra clave `fail`, seguida de una cadena y un punto y coma de terminación.
La cadena se devuelve al controlador clásico como el mensaje de error.

No hay ninguna restricción en el número de instrucciones erróneas dentro de una operación.
El compilador puede emitir una advertencia si las instrucciones siguen una instrucción FAIL dentro de un bloque.

Por ejemplo,

```qsharp
fail $"Impossible state reached";
```

or

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Administración de qubit

Tenga en cuenta que ninguna de estas instrucciones está permitida dentro del cuerpo de una función.
Solo son válidos dentro de las operaciones.

### <a name="clean-qubits"></a>Limpiar qubits

La instrucción `using` se usa para adquirir New qubits para su uso durante un bloque de instrucciones.
Se garantiza que los qubits se inicializan en el estado `Zero` de cálculo.
Qubits debe estar en el estado `Zero` de cálculo al final del bloque de instrucciones; se recomienda que los simuladores apliquen esto.

La instrucción consta de la palabra clave `using`, seguida de un paréntesis de apertura `(`, un enlace, un paréntesis de cierre `)`y el bloque de instrucciones en el que estará disponible el qubits.
El enlace sigue el mismo patrón que `let` instrucciones: un solo símbolo o una tupla de símbolos, seguido de un signo igual `=`y un solo valor o una tupla coincidente de inicializadores.
Los inicializadores están disponibles para un único qubit, indicado como `Qubit()`, o una matriz de qubits, indicada por `Qubit[`, una expresión de `Int` y `]`.

Por ejemplo,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Qubits prestado

La instrucción `borrowing` se usa para obtener qubits para su uso temporal. La instrucción consta de la palabra clave `borrowing`, seguida de un paréntesis de apertura `(`, un enlace, un paréntesis de cierre `)`y el bloque de instrucciones en el que estará disponible el qubits.
El enlace sigue el mismo patrón y las mismas reglas que el de una instrucción `using`.

Por ejemplo,

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Los qubits prestados se encuentran en un estado desconocido y salen del ámbito al final del bloque de instrucciones.
El prestatario se compromete a mantener el qubits en el mismo estado en que se encontraban cuando se prestó, es decir, su estado al principio y al final del bloque de instrucciones se espera que sea el mismo.
En concreto, este estado no es necesariamente un estado clásico, de modo que en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas. 

Consulte [*factorización con 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para obtener un ejemplo de uso de qubit prestado.

Al tomar prestado qubits, el sistema intentará en primer lugar rellenar la solicitud de qubits que están en uso, pero a las que no se tiene acceso durante el cuerpo de la instrucción de `borrowing`.
Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.

## <a name="conjugations"></a>Conjugaciones

A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito. Esto puede evitarse al "deshacer" correctamente los cálculos realizados antes de liberar la memoria. Un patrón común en la informática Quantum es, por lo tanto, lo siguiente: 

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

: nuevo: a partir de la versión 0,9, se admite una instrucción de conjugación que implementa la transformación anterior. Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:

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
Obviamente, este tipo de declaración es mucho más útil si la transformación externa e interna no está disponible como operaciones, pero en su lugar es más conveniente describirla mediante un bloque que consta de varias instrucciones. 

El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply. Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de. 

## <a name="expression-evaluation-statements"></a>Instrucciones de evaluación de expresiones

Cualquier expresión de llamada de tipo `Unit` se puede usar como una instrucción.
Esto se usa principalmente cuando se llama a operaciones en qubits que devuelven `Unit` porque el propósito de la instrucción es modificar el estado de Quantum implícito.
Las instrucciones de evaluación de expresiones requieren un punto y coma de finalización.

Por ejemplo,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
