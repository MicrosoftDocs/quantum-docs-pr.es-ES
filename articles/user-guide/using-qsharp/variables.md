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
# <a name="variables-in-no-locq"></a>Variables en Q#

Q# distingue entre símbolos mutables e inmutables, o *variables*, que se enlazan o asignan a expresiones.
En general, se recomienda el uso de símbolos inmutables porque permite que el compilador realice más optimizaciones.

La parte izquierda de un enlace se compone de una tupla de símbolos y del lado derecho de una expresión.

## <a name="immutable-variables"></a>Variables inmutables

Puede asignar un valor de cualquier tipo en Q# una variable para su reutilización en una operación o función mediante la `let` palabra clave. 

Un enlace inmutable se compone de la palabra clave `let` , seguido de una tupla de símbolos o símbolos, un signo igual `=` , una expresión para enlazar los símbolos a y un punto y coma final.

Por ejemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Esto asigna una matriz determinada de operadores Pauli al nombre de variable (o "Symbol"), `measurementOperator` .

> [!NOTE]
> En el ejemplo anterior, no es necesario especificar explícitamente el tipo de la nueva variable, ya que la expresión del lado derecho de la `let` instrucción no es ambigua y el compilador deduce el tipo correcto. 

Las variables definidas mediante `let` son *inmutables*, lo que significa que una vez que se define, ya no se puede cambiar de ningún modo.
Esto permite varias optimizaciones beneficiosas, incluida la optimización de la lógica clásica que actúa en las variables que se van a reordenar para aplicar la `Adjoint` variante de una operación.

## <a name="mutable-variables"></a>Variables mutables

Como alternativa a la creación de una variable con `let` , la `mutable` palabra clave crea una variable mutable que se *puede* volver a enlazar una vez creada inicialmente mediante la `set` palabra clave.

Puede volver a enlazar los símbolos declarados y enlazados como parte de una `mutable` instrucción a un valor diferente más adelante en el código. Si un símbolo se reenlaza posteriormente en el código, su tipo no cambia y el valor recién enlazado debe ser compatible con ese tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reenlazar símbolos mutables

Puede volver a enlazar una variable mutable mediante una `set` instrucción.
Este tipo de reenlace consta de la palabra clave `set` , seguida de una tupla de símbolos o símbolos, un signo igual `=` , una expresión a la que se van a volver a enlazar los símbolos y un punto y coma final.

A continuación se muestran algunos ejemplos de técnicas de reenlace de instrucciones.

#### <a name="apply-and-reassign-statements"></a>Instrucciones Apply y resign

Una clase determinada de `set` -Statement, la instrucción *Apply-and-resign* , proporciona una forma cómoda de concatenación si el lado derecho está formado por la aplicación de un operador binario y el resultado se va a volver a enlazar al argumento izquierdo para el operador. Por ejemplo,

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa el valor del contador `counter` en cada iteración del `for` bucle. El código anterior es equivalente a 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Las instrucciones similares están disponibles para todos los operadores binarios en los que el tipo del lado izquierdo coincide con el tipo de expresión. Estas instrucciones proporcionan una manera cómoda de acumular valores.

Por ejemplo, suponiendo `qubits` es un registro de qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Instrucciones Update y resign

Existe una concatenación similar para las [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) en el lado derecho.
En consecuencia, las instrucciones *Update-and-resign* existen para *los elementos con nombre* de los tipos definidos por el usuario, así como para *los elementos de matriz*.  

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

En el caso de las matrices, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) en la Q# biblioteca estándar proporciona las herramientas necesarias para muchas necesidades comunes de inicialización y manipulación de matrices y, por tanto, ayuda a evitar tener que actualizar los elementos de la matriz en primer lugar. 

Las instrucciones Update-and-resign proporcionan una alternativa si es necesario:

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

Con las herramientas de biblioteca para las matrices que [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) se proporcionan en, puede, por ejemplo, definir fácilmente una función que devuelve una matriz de `Pauli` tipos donde el elemento en el índice `i` toma un `Pauli` valor determinado y todas las demás entradas son la identidad ( `PauliI` ).

A continuación se muestran dos definiciones de esta función, con el segundo que aprovecha las herramientas de nuestra eliminación.

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

En lugar de recorrer en iteración cada índice de la matriz y establecerlo de forma condicional en `PauliI` o en el determinado `pauli` , puede usar en su lugar `ConstantArray` de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) para crear una matriz de `PauliI` tipos y, a continuación, devolver simplemente una expresión de copia y actualización en la que haya cambiado el valor específico en el índice `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Desconstrucción de tuplas

Además de asignar una sola variable, puede usar las `let` `mutable` palabras clave y, o cualquier otra construcción de enlace, como `set` -para desempaquetar el contenido de un tipo de [tupla](xref:microsoft.quantum.guide.types#tuple-types).
Se dice que una asignación de este formulario *deconstruye* los elementos de esa tupla.

Si el lado derecho del enlace es una tupla, puede deconstruir esa tupla en la asignación.
Estas desconstrucciones pueden implicar tuplas anidadas, y cualquier desconstrucción parcial o completa es válida siempre y cuando la forma de la tupla en el lado derecho sea compatible con la forma de la tupla de símbolos.

Por ejemplo:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Ámbitos de enlace

En general, los enlaces de símbolos salen del ámbito y quedan inoperativos al final del bloque de instrucciones en el que se encuentran.
Esta regla tiene dos excepciones:

- El enlace de la variable de bucle de un `for` bucle está en el ámbito del cuerpo del bucle for, pero no después del final del bucle.
- Las tres partes de un `repeat` / `until` bucle (el cuerpo, la prueba y la corrección) actúan como un solo ámbito, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y la corrección.

En ambos tipos de bucles, cada paso a través del bucle se ejecuta en su propio ámbito, por lo que los enlaces de un paso anterior no están disponibles en un paso posterior.
Para obtener más información sobre estos bucles, consulte [Control Flow](xref:microsoft.quantum.guide.controlflow).

Los bloques internos heredan los enlaces de símbolos de los bloques externos.
Solo puede enlazar un símbolo una vez por bloque; no es válido definir un símbolo con el mismo nombre que otro símbolo que está dentro del ámbito (sin "sombreado").
Las secuencias siguientes son válidas:

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
...                 // n is not bound to a value
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

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre cómo [trabajar con qubits](xref:microsoft.quantum.guide.qubits) en Q# .