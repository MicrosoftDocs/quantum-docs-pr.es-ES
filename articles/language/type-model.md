---
title: 'Tipos de datos de Q #'
description: Obtenga información sobre los diferentes tipos que se usan en el lenguaje de programación de preguntas y respuestas, incluidos tipos integrados, matrices, tuplas, operaciones, funciones y tipos definidos por el usuario.
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904662"
---
# <a name="the-type-model"></a>Modelo de tipo

En esta sección se presenta el modelo de tipo Q # y se describe la sintaxis para especificar y trabajar con tipos.
Tenemos en cuenta que Q # es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los programas de Q # en tiempo de compilación.

Con el fin de proporcionar las garantías más fuertes posibles, las conversiones entre los tipos en Q # deben ser explícitas mediante llamadas a funciones que expresan esa conversión. Se proporcionan varias funciones como parte del espacio de nombres <xref:microsoft.quantum.convert>.
Las conversiones de tipos compatibles por otro lado se producen implícitamente. 

Q # proporciona ambos tipos primitivos, que se pueden usar directamente, y varias maneras de generar nuevos tipos a partir de otros tipos.
En el resto de esta sección se describe cada uno de ellos.

## <a name="primitive-types"></a>Tipos primitivos

El lenguaje Q # proporciona varios *tipos primitivos*, de los que se pueden construir otros tipos:

- El tipo de `Int` representa un entero con signo de 64 bits, por ejemplo: `2`, `107``-5`.
- El tipo de `BigInt` representa un entero con signo de tamaño arbitrario, por ejemplo, `2L`, `107L``-5L`.
   Este tipo se basa en .NET <xref:System.Numerics.BigInteger>
   automáticamente.
- El tipo de `Double` representa un número de punto flotante de precisión doble, por ejemplo: `0.0`, `-1.3``4e-7`.
- El tipo de `Bool` representa un valor booleano que puede ser `true` o `false`.
- El tipo de `Qubit` representa un bit de Quantum o qubit.
   `Qubit`s son opacas para el usuario; la única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).
   En última instancia, las acciones en `Qubit`s se implementan llamando a instrucciones intrínsecas en un procesador Quantum (o en una simulación de la misma).
- El tipo de `Pauli` representa uno de los cuatro operadores de Pauli de qubit único.
   Este tipo se utiliza para denotar la operación base para los giros y para especificar el objeto observable que se va a medir.
   Se trata de un tipo enumerado que tiene cuatro valores posibles: `PauliI`, `PauliX`, `PauliY`y `PauliZ`, que son constantes de tipo `Pauli`.
- El tipo de `Result` representa el resultado de una medida.
   Se trata de un tipo enumerado con dos valores posibles: `One` y `Zero`, que son constantes de tipo `Result`.
   `Zero` indica que se midió + 1 eigenvalue; `One` indica-1 eigenvalue.
- El tipo de `Range` representa una secuencia de enteros, indicada por `start..step..stop`, donde la indicación del paso es opciones. 
   Es decir, `start .. stop` corresponde a `start..1..stop`y, por ejemplo, `1..2..7` representa la secuencia $\{1, 3, 5, 7\}$.
- El tipo de `String` es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.
  Este tipo se utiliza para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.
- El tipo de `Unit` es el tipo que solo permite un `()`de valor. 
  Este tipo se usa para indicar que la operación o la función Q # no devuelve ninguna información. 

Las constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`y `Zero` son símbolos reservados en Q #.

## <a name="array-types"></a>Tipos de matriz

Dado cualquier `'T`válido de Q # type, existe un tipo que representa una matriz de valores de tipo `'T`.
Este tipo de matriz se representa como `'T[]`; por ejemplo, `Qubit[]` o `Int[][]`.
Por ejemplo, una colección de enteros se denota `Int[]`, mientras que una matriz de matrices de valores de `(Bool, Pauli)` se indica `(Bool, Pauli)[][]`.

En el segundo ejemplo, tenga en cuenta que esto representa una matriz potencialmente escalonada de matrices, y no una matriz bidimensional rectangular.
Q # no proporciona compatibilidad con matrices multidimensionales rectangulares.

Un valor de matriz se puede escribir en el código fuente de Q # mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]`.
El tipo de un literal de matriz viene determinado por el tipo base común de todos los elementos de la matriz. 

> [!WARNING]
> Los elementos de una matriz no se pueden cambiar una vez creada la matriz.
> Las instrucciones Update-and-resign y/o las expresiones de copia y actualización se pueden usar para construir una matriz modificada.

Como alternativa, se puede crear una matriz a partir de su tamaño mediante la palabra clave `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

En cualquier caso, una vez construida una matriz, se puede utilizar la función principal `Length` para obtener el número de elementos como `Int`.
Las matrices se pueden incluir en un subíndice con corchetes, con subíndices que tienen el tipo `Int` o el tipo `Range`, para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.
Los subíndices de las matrices son de base cero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos de tupla

Dado cero o más tipos diferentes `T0`, `T1`,... `Tn`, podemos denotar un nuevo *tipo de tupla* como `(T0, T1, ..., Tn)`.
Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))`.
Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.

Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.
Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)`.
Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas, etc.

A partir de Q # 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor*de tupla vacío.

Las instancias de tupla son inmutables.
Q # no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.

Las tuplas son un concepto eficaz que se usa en Q # para recopilar valores en un único valor, lo que facilita su paso.
En concreto, mediante la notación de tupla, podemos expresar que cada operación y a la que se puede llamar toma exactamente una entrada y devuelve exactamente una salida.

### <a name="singleton-tuple-equivalence"></a>Equivalencia de tupla singleton

Es posible crear una tupla singleton (elemento único), `('T1)`, como `(5)` o `([1,2,3])`.
Sin embargo, Q # trata una tupla singleton como totalmente equivalente a un valor del tipo delimitado.
Es decir, no hay ninguna diferencia entre `5` y `(5)`, o entre `5` y `(((5)))`, o entre `(5, (6))` y `(5, 6)`.

Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.
Solo es válido escribir `(5)+3` como para escribir `5+3`y ambas expresiones se evaluarán como `8`.
En concreto, esto significa que una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo se puede considerar como tomar un único argumento o devolver un valor único.

Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_.

## <a name="user-defined-types"></a>Tipos definidos por el usuario

Un archivo de preguntas # puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.
Para cualquier tipo de tupla `T`, podemos declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la instrucción `newtype`.
En el espacio de nombres @"microsoft.quantum.math", por ejemplo, los números complejos se definen como un tipo definido por el usuario:

```qsharp
newtype Complex = (Double, Double);
```

Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double`.   
Además de los elementos anónimos, los tipos definidos por el usuario también admiten elementos con nombre a partir de la versión 0,7 o posterior. Por ejemplo, podríamos haber llamado a items `Re` para el Double que representa la parte real de un número complejo y `Im` para la parte imaginaria: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre. Además, también se pueden asignar nombres a los elementos internos.
El tipo `Nested` tal y como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))`, de la que solo se asigna un nombre al elemento de tipo `Int` y todos los demás elementos son anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del operador de acceso `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Para tener acceso a los elementos anónimos por otro lado, el valor ajustado primero debe extraerse mediante el operador postfijo `!`.
El operador "Unwrap", `!`, permite extraer el valor contenido en un tipo definido por el usuario.
El tipo de una expresión "Unwrap" es el tipo subyacente del tipo definido por el usuario. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

El operador Unwrap desencapsula exactamente una capa de ajuste.
Se pueden usar varios operadores Unwrap para tener acceso a un valor de ajuste de multiplicación.

Por ejemplo:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Eche un vistazo a la sección sobre cómo [desencapsular las expresiones](xref:microsoft.quantum.language.expressions#unwrap-expressions) y la precedencia de los [operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para obtener más detalles.

Los valores de un tipo definido por el usuario se pueden crear llamando al constructor de tipo correspondiente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Como alternativa, se pueden crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Al igual que en el caso de las matrices, estas expresiones copian todos los valores de los elementos de la expresión original, con la excepción de los elementos con nombre especificados. Estos valores se establecen en los que se definen en el lado derecho de la expresión. Cualquier otra construcción de lenguaje, como por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), que están disponibles para los elementos de matriz existen también para los elementos con nombre en los tipos definidos por el usuario.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Los tipos definidos por el usuario se pueden usar en cualquier otro tipo que se pueda usar.
En concreto, es posible definir una matriz de un tipo definido por el usuario y incluir un tipo definido por el usuario como elemento de un tipo de tupla.

No es posible crear estructuras de tipo recursivas.
Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.
En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no sería válido:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.
Volviendo al ejemplo de `Complex`, puede haber definido también coordenadas polares 2D como un tipo definido por el usuario:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Aunque tanto `Complex` como `Polar` tienen un tipo subyacente `(Double, Double)`, los dos tipos son totalmente incompatibles en Q #, lo que minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.
De esta manera, los tipos definidos por el usuario tienen un rol similar como F# registros en, por ejemplo. 


## <a name="operation-and-function-types"></a>Tipos de operación y función

Una _operación_ Q # es una subrutina Quantum.
Es decir, es una rutina invocable que contiene operaciones cuánticas.

Una _función_ Q # es una subrutina clásica utilizada en un algoritmo Quantum.
Puede contener código clásico pero sin operaciones Quantum.
En concreto, las funciones no pueden asignar o tomar prestado qubits ni llamar a las operaciones.
Sin embargo, es posible pasar operaciones o qubits para su procesamiento.
Por lo tanto, las funciones son completamente deterministas en el sentido de que si se llama con los mismos argumentos, siempre se producirá el mismo resultado. 

Juntas, las operaciones y las funciones _se llaman llamadas_.  Puede ver algunos [ejemplos](#examples) de estos siguientes.

Todas las llamadas a Q # pueden tomar un valor único como entrada y devolver un valor único como salida.
Los valores de entrada y salida pueden ser tuplas.
Se puede llamar a que no se devuelve ningún resultado `Unit`.
Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.

El tipo básico de cualquier que se pueda llamar se escribe como `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)`, donde tanto `'Tinput` como `'Tresult` son tipos.
El primer formulario, con `=>`, se utiliza para las operaciones; la segunda forma, con `->`, para las funciones.
Por ejemplo, `((Qubit, Pauli) => Result)` representa la firma de una posible operación de medición de un solo qubit.

Los tipos de función se especifican completamente mediante su firma.
Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)`.

Las operaciones, pero no las funciones, tienen ciertas _características_ adicionales que se expresan como parte del tipo de operación. Estas características incluyen información sobre los elementos que admite la operación.
Los funcdores son metaoperaciones que generan una especialización de una operación base; Vea los [funcers](#functors)más abajo.

Los tipos de operación se especifican mediante su tipo de entrada, tipo de salida y sus características.    
Para requerir la compatibilidad con la `Controlled` y/o el functor `Adjoint` en un tipo de operación, es necesario agregar una anotación que indique las características correspondientes.
Un `is Ctl` de anotación, por ejemplo, indica que la operación es controlable. Si queremos requerir que una operación de ese tipo admita los `Adjoint` y `Controlled` functor, podemos expresar esto como `(Qubit => Unit is Adj + Ctl)`. Las características de la operación utilizadas `Adj` y `Ctl` de forma rigurosa son dos conjuntos predefinidos de etiquetas, donde cada etiqueta indica una operación determinada, como por ejemplo, la compatibilidad con un functor determinado.
Por lo tanto, `+` se usa para indicar la Unión de estos dos conjuntos y `*` se usa para indicar la intersección, es decir, las etiquetas que son comunes a ambos conjuntos.  

Por ejemplo, la operación Pauli `X` tiene el tipo `(Qubit => Unit is Adj + Ctl)`.
Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.


### <a name="type-parameterized-functions-and-operations"></a>Operaciones y funciones con parámetros de tipo

Los tipos a los que se puede llamar pueden contener parámetros de tipo.
Los parámetros de tipo se indican mediante un símbolo precedido por una comilla simple; por ejemplo, `'A` es un parámetro de tipo válido.

Un parámetro de tipo puede aparecer más de una vez en una sola firma.
Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tendría `(('A[], 'A->'A) -> 'A[])`de firma.
Del mismo modo, una función que devuelve la composición de dos operaciones puede tener `((('A=>'B), ('B=>'C)) -> ('A=>'C))`de firma.

Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.

Q # no proporciona un mecanismo para restringir los tipos posibles que se pueden sustituir por un parámetro de tipo.

### <a name="type-compatibility"></a>Compatibilidad de tipos

Se puede usar una operación con funciones de compatibilidad adicionales que admitan en cualquier lugar una operación con menos inactivos, pero se espera la misma firma.
Por ejemplo, se puede usar una operación de tipo `(Qubit => Unit is Adj)` en cualquier lugar en el que se espere una operación de tipo `(Qubit => Unit)`.

Q # es covariante con respecto a los tipos de valor devueltos a los que se puede llamar: una invocable que devuelve un tipo `'A` es compatible con una que se puede llamar con el mismo tipo de entrada y un tipo de resultado que `'A` es compatible con.

Q # es contravariante con respecto a los tipos de entrada: una invocable que toma un tipo `'A` como entrada es compatible con una operación invocable con el mismo tipo de resultado y un tipo de entrada que es compatible con `'A`.

Es decir, dadas las siguientes definiciones:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

lo siguiente es cierto:

- La función `ConjugateInvertWith` se puede invocar con un argumento `inner` de `Invert` o `ApplyUnitary`.
- La función `ConjugateUnitaryWith` se puede invocar con un argumento `inner` de `ApplyUnitary`, pero no `Invert`.
- Un valor de tipo `(Qubit[] => Unit is Adj + Ctl)` puede devolverse desde `ConjugateInvertWith`.

> [!IMPORTANT]
> Q # 0,3 presenta una diferencia significativa en el comportamiento de los tipos definidos por el usuario.

Los tipos definidos por el usuario se tratan como una versión ajustada del tipo subyacente, en lugar de como un subtipo.
Esto significa que un valor de un tipo definido por el usuario no se puede usar cuando se espera un valor del tipo subyacente.

### <a name="functors"></a>Funciones

Un functor en Q # es un generador que define una nueva operación desde otra operación.
Los funcers tienen acceso a la implementación de la operación base al definir la implementación de la nueva operación.
Por lo tanto, los funcdores pueden realizar funciones más complejas que las funciones de nivel superior tradicionales.

Los inactivos no tienen una representación en el sistema de tipos de preguntas y respuestas. Por lo tanto, actualmente no es posible enlazarlas a una variable o pasarlas como argumentos. 

Se usa un functor si se aplica a una operación y se devuelve una nueva operación.
Por ejemplo, la operación que resulta de aplicar el `Adjoint` functor a la operación de `Y` se escribe como `Adjoint Y`.
La nueva operación se puede invocar después como cualquier otra operación.
Por lo tanto, `Adjoint Y(q1)` aplica el functor injoin a la operación de `Y` para generar una nueva operación y aplica esa nueva operación a `q1`.

Del mismo modo, `Controlled X(controls, target)` aplica el functor controlado a la operación de `X` para generar una nueva operación y aplica esa nueva operación a `controls` y `target`.

Los dos funcdores estándar en Q # son `Adjoint` y `Controlled`.

#### <a name="adjoint"></a>Contiguo

En Quantum Computing, el contiguo de una operación es la transposición de conjugada compleja de la operación.
En el caso de las operaciones que implementan un operador unitario, el contiguo es el inverso de la operación.
En el caso de una operación simple que simplemente invoca una secuencia de otras operaciones unitarios en un conjunto de qubits, el elemento contiguo puede calcularse aplicando los elementos contiguos de las suboperaciones en el mismo qubits, en la secuencia inversa.

Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Adjoint` functor.
Por ejemplo, `Adjoint QFT` designa el contiguo de la operación de `QFT`.
La nueva operación tiene la misma signatura y el mismo tipo que la operación base.
En concreto, la nueva operación también permite `Adjoint`y permitirá `Controlled` solo si la operación base lo hizo.

El inverso inmediato es su propio inverso; es decir, `Adjoint Adjoint Op` siempre es igual que `Op`.

#### <a name="controlled"></a>Regula

La versión controlada de una operación es una operación nueva que aplica eficazmente la operación base solo si todos los qubits de control están en un estado especificado.
Si el control qubits se encuentra en la superposición, la operación base se aplica de forma coherente a la parte adecuada de la superposición.
Por lo tanto, las operaciones controladas suelen usarse para generar el inenredo.

En Q #, las versiones controladas siempre toman una matriz de qubits de control, y el estado especificado siempre es para que todo el qubits de control esté en el estado de `One` de cálculo (`PauliZ`), $ \ket{1}$.
El control basado en otros Estados puede lograrse aplicando la operación unitario adecuada al control qubits antes de la operación controlada y aplicando después los inversos de la operación unitario después de la operación controlada.
Por ejemplo, la aplicación de una operación de `X` a un qubit de control antes y después de una operación controlada hará que la operación se controle en el estado `Zero` ($ \ket{0}$) para ese qubit; al aplicar una operación de `H` antes y después de que se controle el estado de la `PauliX` `One`, es decir,-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ en lugar de `PauliZ` estado `One`.

Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Controlled` functor.
La firma de la nueva operación se basa en la firma de la operación original.
El tipo de resultado es el mismo, pero el tipo de entrada es una tupla de dos tuplas con una matriz qubit que contiene el control qubit (s) como primer elemento y los argumentos de la operación original como el segundo elemento.
La nueva operación admite `Controlled`y admitirá `Adjoint` si y solo si la operación original lo hizo.

Si la operación original solo tomó un argumento, la equivalencia de la tupla singleton entrará en juego aquí.
Por ejemplo, `Controlled X` es la versión controlada de la operación de `X`.
`X` tiene el tipo `(Qubit => Unit is Adj + Ctl)`, por lo que `Controlled X` tiene el tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; debido a la equivalencia de la tupla singleton, es igual que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Si la operación base tomó varios argumentos, Recuerde incluir los argumentos correspondientes de la versión controlada de la operación entre paréntesis para convertirlos en una tupla.
Por ejemplo, `Controlled Rz` es la versión controlada de la operación de `Rz`.
`Rz` tiene el tipo `((Double, Qubit) => Unit is Adj + Ctl)`, por lo que `Controlled Rz` tiene `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`de tipo.
Por lo tanto, `Controlled Rz(controls, (0.1, target))` sería una invocación válida de `Controlled Rz` (observe los paréntesis alrededor de `0.1, target`).

Como otro ejemplo, `CNOT(control, target)` se puede implementar como `Controlled X([control], target)`. Si un destino debe controlarse mediante 2 control qubits (CCNOT), se puede usar `Controlled X([control1, control2], target)` instrucción.

### <a name="examples"></a>Ejemplos

Este ejemplo de una operación de Q # procede del ejemplo de [medición](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . Dentro de las operaciones, podemos asignar qubits y usar las operaciones Quantum en esos qubits, como `H` y `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Este ejemplo de una función proviene del ejemplo [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Contiene código puramente clásico. Puede ver que, a diferencia del ejemplo anterior, no se asigna ningún qubits y no se usa ninguna operación Quantum.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

También es posible que una función se pase qubits para su procesamiento, como en este ejemplo del ejemplo [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Los qubits se pasan a la función y se usan para el procesamiento, aunque en ningún momento se modifican los Estados de qubit.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
