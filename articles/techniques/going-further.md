---
title: Continuar con las técnicas de preguntas y respuestas
description: 'Explore los temas avanzados en Q #, como la creación de funciones genéricas y la toma de qubits.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 46ebf544c1d6e56f152a06d06151305fa972011a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906906"
---
# <a name="going-further"></a>Más información #

Ahora que ha visto cómo escribir programas Quantum interesantes en p #, en esta sección se explica con más detalle mediante la introducción de algunos temas más avanzados que deberían resultar útiles en el futuro.


## <a name="generic-operations-and-functions"></a>Operaciones y funciones genéricas ##

> [!TIP]
> En esta sección se da por supuesto que está familiarizado con los [genéricos de C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [genéricos en F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ plantillas](https://docs.microsoft.com/cpp/cpp/templates-cpp)o enfoques similares a la Metaprogramación en otros lenguajes.

Muchas funciones y operaciones que podríamos querer definir no se basan en gran medida en los tipos de sus entradas, sino que solo usan implícitamente sus tipos a través de otra función u operación.
Por ejemplo, considere el concepto de *mapa* común a muchos idiomas funcionales; dada una función $f (x) $ y una colección de valores $\{x_1, x_2, \dots, x_n\}$, Map devuelve una nueva colección $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
Para implementar esto en Q #, podemos aprovechar las ventajas de que las funciones son de primera clase.
Vamos a escribir un ejemplo rápido de `Map`, mediante el uso de ★ como un marcador de posición mientras averiguamos qué tipos necesitamos.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tenga en cuenta que esta función tiene un aspecto muy similar al de los tipos reales que se sustituyen en.
Una asignación de enteros a Paulis, por ejemplo, se parece mucho a una asignación de números de punto flotante a cadenas:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

En principio, podríamos escribir una versión de `Map` para cada par de tipos que encontramos, pero esto presenta una serie de dificultades.
Por ejemplo, si encontramos un error en `Map`, debemos asegurarnos de que la corrección se aplique uniformemente en todas las versiones de `Map`.
Además, si creamos una nueva tupla o UDT, ahora debemos crear también una nueva `Map` para ir junto con el nuevo tipo.
Aunque esto es tractable para un número pequeño de estas funciones, a medida que recopilamos más funciones de la misma forma que `Map`, el costo de introducir nuevos tipos se vuelve injustificable en un orden bastante corto.

Sin embargo, gran parte de este problema se debe a que no se ha proporcionado al compilador la información necesaria para reconocer cómo se relacionan las diferentes versiones de `Map`.
En efecto, queremos que el compilador trate `Map` como algún tipo de función matemática de *tipos* q # a funciones q #.
Esta noción se formaliza permitiendo que las funciones y las operaciones tengan *parámetros de tipo*, así como sus parámetros de tupla normales.
En los ejemplos anteriores, deseamos pensar en `Map` como tener parámetros de tipo `Int, Pauli` en el primer caso y `Double, String` en el segundo caso.
En su mayor parte, estos parámetros de tipo se pueden usar como si fueran tipos normales: usamos valores de parámetros de tipo para crear matrices y tuplas, llamar a funciones y operaciones, y asignar a variables ordinarias o mutables.

> [!NOTE]
> El caso más extremo de dependencia indirecta es el de qubits, donde un programa de Q # no puede confiar directamente en la estructura del tipo de `Qubit`, sino que **debe** pasar estos tipos a otras operaciones y funciones.

Volviendo al ejemplo anterior, podemos ver que necesitamos `Map` tener parámetros de tipo, uno para representar la entrada a `fn` y otro para representar la salida de `fn`.
En Q #, esto se escribe agregando corchetes angulares (es decir `<>`, no frenos $ \braket{}$!) después del nombre de una función u operación en su declaración, y enumerando cada parámetro de tipo.
El nombre de cada parámetro de tipo debe comenzar con una marca de paso `'`, lo que indica que se trata de un parámetro de tipo y no de un tipo ordinario (también conocido como tipo *concreto* ).
Por lo tanto, para `Map`, escribimos:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tenga en cuenta que la definición de `Map<'Input, 'Output>` tiene un aspecto muy similar al de las versiones que escribimos antes.
La única diferencia es que hemos informado explícitamente al compilador de que `Map` no depende directamente de qué `'Input` y `'Output` son, pero funciona para dos tipos mediante el uso indirecto de los `fn`.
Una vez que hemos definido `Map<'Input, 'Output>` de este modo, podemos llamarlo como si fuera una función ordinaria:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> La escritura de funciones y operaciones genéricas es un lugar donde "tupla en tupla" es una forma muy útil de pensar en las funciones y operaciones de Q #.
> Dado que cada función toma exactamente una entrada y devuelve exactamente una salida, una entrada de tipo `'T -> 'U` coincide con *cualquier* función de Q #.
> Del mismo modo, cualquier operación se puede pasar a una entrada de tipo `'T => 'U`.

Como segundo ejemplo, considere el reto de escribir una función que devuelva la composición de otras dos funciones:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aquí, debemos especificar exactamente qué `A`, `B`y `C` son, por lo que limitan gravemente la utilidad de la nueva función de `Compose`.
Después de todo, solo `Compose` depende de `A`, `B`y `C` *a través* de `innerFn` y `outerFn`.
Como alternativa, se pueden agregar parámetros de tipo a `Compose` que indiquen que funciona con *cualquier* `A`, `B`y `C`, siempre y cuando estos parámetros coincidan con los esperados por `innerFn` y `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Las bibliotecas de preguntas # estándar proporcionan una gama de funciones y operaciones parametrizadas de tipo para facilitar la rápida creación de un flujo de control de orden superior.
Estos se describen con más detalle en la guía de la [biblioteca estándar de preguntas y respuestas](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Préstamos qubits ##

El mecanismo de préstamos permite la asignación de qubits que se puede usar como espacio de desecho durante un cálculo. Por lo general, estos qubitss no están en un estado limpio, es decir, no se inicializan necesariamente en un estado conocido como $ \ket{0}$. También habla de qubits "sucio", ya que su estado es desconocido e incluso puede estar inactivado con otras partes de la memoria del equipo Quantum. Entre los casos de uso conocidos de qubits sucios se encuentran las implementaciones de las puertas de CNOT de varios controlados que solo requieren muy pocas qubits e implementaciones de incrementos.

En Canon hay ejemplos que usan la palabra clave `borrowing`, por ejemplo, la función `MultiControlledXBorrow` define a continuación.
Si `controls` denota el control qubits que debe agregarse a una operación de `X`, esta implementación agregará un total de `Length(controls)-2` muchos ancillas modificados.

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

Tenga en cuenta que el uso extensivo del `With` combinador---en su forma que es aplicable a las operaciones que admiten el operador de cojoin, es decir, `WithA`---se realizó en este ejemplo, que es un estilo de programación adecuado, ya que agregar el control a las estructuras que implican `With` solo propaga el control a la operación interna. Tenga en cuenta que aquí, además de la `body` de la operación, se proporcionó explícitamente una implementación del cuerpo `controlled` de la operación, en lugar de recurrir a una instrucción `controlled auto`. La razón es que sabemos de la estructura del circuito cómo agregar fácilmente más controles, lo que es beneficioso en comparación con la adición de control a cada una de las puertas individuales del `body`. 

Es instructivo comparar este código con otra función de Canon `MultiControlledXClean` que logra el mismo objetivo de implementar una operación de `X` controlada multiplicada, sin embargo, que usa varios qubits limpios con el mecanismo de `using`. 
