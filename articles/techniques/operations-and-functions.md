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
# <a name="q-operations-and-functions"></a>Operaciones y funciones de Q #

Los programas de preguntas y respuestas se componen de una o varias *operaciones* que describen las operaciones de Quantum de efectos secundarios que pueden tener los datos de Quantum y una o varias *funciones* que permiten realizar modificaciones en los datos clásico. A diferencia de las operaciones, las funciones se usan para describir el comportamiento puramente clásico y no tienen ningún efecto además de calcular los valores de salida clásico.

Cada operación definida en Q # puede llamar a cualquier número de operaciones, incluidas las operaciones intrínsecas integradas definidas por el lenguaje. La manera determinada en la que se definen estas operaciones intrínsecas depende del equipo de destino. Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.

## <a name="defining-new-operations"></a>Definir nuevas operaciones

Tal y como se ha descrito anteriormente, el bloque de creación más básico de un programa Quantum escrito en Q # es una *operación*, a la que se puede llamar desde aplicaciones .net clásicas, por ejemplo, mediante un simulador u otras operaciones en Q #.
Cada operación toma una entrada, genera una salida y especifica la implementación de una o varias especializaciones de operación.
Por ejemplo, la siguiente operación solo define una especialización de cuerpo predeterminada y toma un único qubit como entrada y, a continuación, llama a la operación de `X` integrada en esa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

La palabra clave `operation` comienza la definición de la operación y va seguida del nombre; aquí, `BitFlip`.
Después, el tipo de la entrada se define como `Qubit`, junto con un nombre `target` para hacer referencia a la entrada dentro de la nueva operación.
Del mismo modo, el `Unit` define que la salida de la operación está vacía.
Se usa de forma similar a `void` C# en y otros lenguajes imperativos, y es F# equivalente a `unit` en y otros lenguajes funcionales.

> [!NOTE]
> Lo exploraremos con más detalle a continuación, pero cada operación en Q # toma exactamente una entrada y devuelve exactamente una salida.
> A continuación, se representan varias entradas y salidas mediante *tuplas*, que recopilan varios valores juntos en un solo valor.
> De manera informativa, decimos que Q # es un lenguaje de "tupla de tupla en".
> Después de este concepto, `()` se debe leer como la tupla "vacía", que tiene el tipo `Unit`.

Dentro de la nueva operación, la implementación se puede especificar directamente dentro de la declaración si solo es necesario especificar explícitamente la implementación de la especialización del cuerpo predeterminado. Además, es posible definir las implementaciones de, por ejemplo, una o varias operaciones de `functor`, tal como se ha elaborado a continuación. En el ejemplo anterior, la única instrucción es llamar a la operación de Q # integrada <xref:microsoft.quantum.intrinsic.x>.

Las operaciones también pueden devolver tipos más interesantes que `Unit`.
Por ejemplo, la operación <xref:microsoft.quantum.intrinsic.m> devuelve una salida de tipo `Result`, que representa la realización de una medición. Podemos pasar el resultado de una operación a otra operación, o bien puede usarlo con la palabra clave `let` para definir una nueva variable.
<!-- Link to UID for superdense conceptual and example documentation. -->
Esto permite representar el cálculo clásico que interactúa con las operaciones Quantum en un nivel bajo, como en el caso de la codificación superdensa:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Inactivos, contiguos y controlados
Si una operación implementa una transformación unitario, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*. Una especialización de una operación adyacente especifica cómo actúa cuando se ejecuta en orden inverso, mientras que una especialización controlada especifica cómo actúa una operación cuando se aplica en el estado de un registro de Quantum.
La existencia de estas especializaciones se puede declarar como parte de la firma de la operación: `is Adj + Ctl` en el ejemplo siguiente. El compilador genera la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Muchas operaciones en Q # representan las puertas de la unidad.
> Si $U $ es la puerta de la unitario representada por una operación `U`, `Adjoint U` representa la puerta de $U ^ \dagger $.

En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente. Dichas declaraciones de especialización explícita pueden constar de una directiva de generación adecuada o una implementación definida por el usuario. El código de `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas: 

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
La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.
Si el compilador no puede generar la implementación para una determinada especialización automáticamente, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.

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
En el ejemplo anterior, `adjoint invert;` indica que la especialización de la instancia contigua se va a generar invirtiendo la implementación del cuerpo y `controlled adjoint invert;` indica que la especialización contigua controlada se generará invirtiendo la implementación dada de la especialización controlada.

Veremos más ejemplos de esto en el [flujo de control de orden superior](xref:microsoft.quantum.concepts.control-flow).

Para llamar a una especialización de una operación, utilice las palabras clave `Adjoint` o `Controlled`.
Por ejemplo, el ejemplo de codificación de superdensas anterior se puede escribir de forma más compacta mediante el uso del valor contiguo de `PrepareEntangledPair` para transformar de nuevo el estado desenredado en un par unentangled de qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Hay una serie de limitaciones importantes que se deben tener en cuenta al diseñar operaciones para usarlas con los funcdores.
Lo más importante es que el compilador no puede generar automáticamente especializaciones para una operación que usa el valor de salida de cualquier otra operación, ya que es ambiguo cómo reordenar las instrucciones en dicha operación para obtener el mismo efecto.


## <a name="defining-new-functions"></a>Definir nuevas funciones

Q # también permite definir *funciones*, que son distintas de las operaciones en que no se les permite tener ningún efecto más allá del cálculo de un valor de salida.
En concreto, las funciones no pueden llamar a las operaciones, actuar en qubits, números aleatorios de muestra o, de lo contrario, depender del estado más allá del valor de entrada de una función.
Como consecuencia, las funciones Q # son *puras*, ya que siempre asignan los mismos valores de entrada a los mismos valores de salida.
Esto permite que el compilador de preguntas # reordene de forma segura cómo y cuándo se llama a las funciones al generar especializaciones de operación.

La definición de una función funciona de forma similar a la definición de una operación, con la excepción de que no se puede definir ninguna especialización contigua o controlada para una función.
Por ejemplo:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Siempre que sea posible hacerlo, resulta útil escribir una lógica clásica en términos de funciones en lugar de operaciones, de modo que se pueda utilizar más fácilmente desde las operaciones.
Si hubiéramos escrito `Square` como una operación, por ejemplo, el compilador no habría podido garantizar que la llamada a él con la misma entrada produciría sistemáticamente los mismos resultados.

Para subrayar la diferencia entre las funciones y las operaciones, tenga en cuenta el problema de realizar un muestreo de forma de un número aleatorio en una operación de Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que se llama a `U`, tendrá una acción diferente en `target`.
En concreto, el compilador no puede garantizar que si se agrega una declaración de especialización `adjoint auto` a `U`, `U(target); Adjoint U(target);` actúa como identidad (es decir, como una operación no operativa).
Esto infringe la definición del método contiguo que vimos en [vectores y matrices](xref:microsoft.quantum.concepts.vectors), de modo que permitir la generación automática de una especialización de tipo contiguo en una operación en la que se llamó a la operación <xref:microsoft.quantum.math.randomreal> interrumpiría las garantías proporcionadas por el compilador. <xref:microsoft.quantum.math.randomreal> es una operación para la que no existe ninguna versión contigua o controlada.

Por otro lado, permitir llamadas a funciones como `Square` es seguro, en el que el compilador puede estar seguro de que solo necesita conservar la entrada en `Square` para mantener la salida estable.
Por lo tanto, el aislamiento de la lógica más clásica posible en las funciones facilita la reutilización de esa lógica en otras funciones y operaciones similares.

## <a name="control-flow"></a>Flujo de control

Dentro de una operación o función, cada instrucción se ejecuta en orden, de forma similar a la mayoría de los lenguajes imperativos más comunes.
Este flujo de control se puede modificar, sin embargo, de tres maneras distintas:

- Instrucciones de `if`
- `for` bucles
- `repeat`-bucles `until`

Aplazamos la explicación de este último hasta que analicemos los circuitos de [repetición hasta éxitos (RU)](xref:microsoft.quantum.techniques.qubits#measurements) .
Sin embargo, las construcciones de flujo de control `if` y `for` continúan en un sentido familiar para la mayoría de los lenguajes de programación clásico.
En concreto, una instrucción `if` puede tomar una condición, puede ir seguida de una o varias instrucciones `elif` y puede acabar con un `else`:

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

Del mismo modo, `for` bucles indican la iteración en un intervalo de enteros o en los elementos de una matriz:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Lo importante es que los bucles de `for` y las instrucciones de `if` se pueden usar incluso en operaciones para las que se generan automáticamente especializaciones. En ese caso, el contiguo de un bucle `for` invierte la dirección y toma el contiguo de cada iteración.
Esto sigue el principio de "zapatos y Socks": Si desea deshacer la colocación en Socks y después zapatos, debe deshacer los zapatos y, a continuación, deshacer la colocación en SOCKS.
Funciona a la medida de que sea un poco bien para probar y sacar su Socks mientras sigue usando sus zapatos.

## <a name="operations-and-functions-as-first-class-values"></a>Operaciones y funciones como valores de primera clase

Una técnica crítica para el razonamiento sobre el flujo de control y la lógica clásica con funciones en lugar de operaciones es usar las operaciones y las funciones de Q # como *primera clase*.
Es decir, cada uno de los valores del lenguaje se encuentra en su propio derecho.
Por ejemplo, lo siguiente es código de Q # perfectamente válido, si un poco indirecto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

El valor de la variable `ourH` en el fragmento de código anterior es el <xref:microsoft.quantum.intrinsic.h>de la operación, de modo que se pueda llamar a ese valor como cualquier otra operación.
Esto nos permite escribir operaciones que tomen las operaciones como parte de su entrada, formando conceptos de flujo de control de orden superior.
Por ejemplo, podríamos imaginar que quiere "cuadrado" una operación aplicándole dos veces en el mismo qubit de destino.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

En este ejemplo, la flecha de `=>` que aparece en el tipo `(Qubit => Unit)` denota que el campo de entrada `op` es una operación que toma como entrada el tipo `Qubit` y genera una tupla vacía como salida.
Además, se especifican las características de ese tipo de operación, que contienen la información sobre los tipos de datos que se admiten.
Una operación de tipo `(Qubit => Unit)` no admite la `Adjoint` ni la `Controlled` functor. Si queremos indicar que una operación de ese tipo tiene que admitir, por ejemplo, la `Adjoint` functor, tenemos que declararla como adjointable. Esto se hace utilizando la anotación `is Adj` al tipo. Del mismo modo, `(Qubit => Unit is Ctl)` denota que una operación de ese tipo admite el `Controlled` functor. Lo exploraremos más en general si analizamos los [tipos en Q # más en](xref:microsoft.quantum.language.type-model) general.

Por ahora, hacemos hincapié en que también se pueden devolver las operaciones como parte de las salidas, de modo que podamos aislar algunos tipos de lógica condicional clásica como una función clásica que devuelve una descripción de un programa Quantum en forma de una operación.
Como ejemplo sencillo, considere el ejemplo de teleportabilidad, en el que la entidad que recibe un mensaje clásico de dos bits debe usar el mensaje para descodificar sus qubit en el estado de telepuerto adecuado.
Podríamos escribir esto en términos de una función que toma esos dos bits clásico y devuelve la operación de descodificación adecuada.

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

Esta nueva función es realmente una función, en el caso de que se llame con los mismos valores de `hereBit` y `thereBit`, siempre se devolverá la misma operación.
Por lo tanto, el descodificador se puede ejecutar de forma segura dentro de las operaciones sin tener que preocuparse de cómo la lógica de descodificación interactúa con las definiciones de las distintas especializaciones de operación.
Es decir, hemos aislado la lógica clásica dentro de una función, garantizando al compilador que la llamada a la función se puede reordenar con Impunity, siempre y cuando se conserve la entrada.

También podemos tratar las funciones como valores de primera clase, ya que veremos con más detalle cuando se analizan [las operaciones y los tipos de función](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Aplicar operaciones y funciones parcialmente

Podemos hacer mucho más con funciones que devuelven operaciones mediante el uso de una *aplicación parcial*, en la que podemos proporcionar una o más partes de la entrada a una función u operación sin llamarla realmente. Por ejemplo, al volver a llamar al ejemplo `ApplyTwice` anterior, podemos indicar que no queremos especificar, de inmediato, a qué qubit se debe aplicar la operación de entrada:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

En este caso, la variable local `twiceOp` contiene la operación parcialmente aplicada `ApplyTwice(op, _)`, donde las partes de la entrada que todavía no se han especificado se indican mediante `_`.
Cuando realmente llamamos `twiceOp` en la línea siguiente, pasamos como entrada a la operación parcialmente aplicada todas las partes restantes de la entrada a la operación original.
Por lo tanto, el fragmento de código anterior es realmente idéntico a haber llamado a `ApplyTwice(op, target)` directamente, y se guarda para que se haya introducido una nueva variable local que nos permita retrasar la llamada mientras se proporcionan algunas partes de la entrada.

Dado que una operación que se ha aplicado parcialmente no se llama realmente hasta que se ha proporcionado toda la entrada, podemos aplicar de forma segura las operaciones, incluso desde las funciones.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

En principio, la lógica clásica dentro de `SquareOperation` podría haber sido mucho más complicada, pero sigue estando aislada del resto de una operación mediante la garantía de que el compilador puede ofrecer información sobre las funciones.
Este enfoque se usará en toda la biblioteca de preguntas y respuestas para expresar el flujo de control clásico de manera que se pueda usar fácilmente dentro de los programas Quantum.
