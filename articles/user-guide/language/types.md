---
title: 'Tipos en Q #'
description: Obtenga información sobre los diferentes tipos que se usan en el lenguaje de programación de preguntas y respuestas.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431145"
---
# <a name="types-in-q"></a>Tipos en Q #

Esta página dispone del modelo de tipo Q # y describe la sintaxis para especificar y trabajar con tipos.
La página siguiente, [expresiones de tipo](xref:microsoft.quantum.guide.expressions), detalla cómo crear y operar en expresiones de estos tipos.

Tenemos en cuenta que Q # es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los programas de Q # en tiempo de compilación.
Con el fin de proporcionar las garantías más fuertes posibles, las conversiones entre los tipos en Q # deben ser explícitas mediante llamadas a funciones que expresan esa conversión. Se proporcionan varias funciones como parte del <xref:microsoft.quantum.convert> espacio de nombres.
Las conversiones de tipos compatibles por otro lado se producen implícitamente. 

Q # proporciona ambos tipos primitivos, que se pueden usar directamente, y varias maneras de generar nuevos tipos a partir de otros tipos.
En el resto de esta sección se describe cada uno de ellos.

## <a name="primitive-types"></a>Tipos primitivos

El lenguaje Q # proporciona varios *tipos primitivos*, de los que se pueden construir otros tipos:

- El `Int` tipo representa un entero con signo de 64 bits, por ejemplo: `2` , `107` , `-5` .
- El `BigInt` tipo representa un entero con signo de tamaño arbitrario, por ejemplo `2L` , `107L` , `-5L` .
   Este tipo se basa en .NET<xref:System.Numerics.BigInteger>
   automáticamente.
- El `Double` tipo representa un número de punto flotante de precisión doble, por ejemplo: `0.0` , `-1.3` , `4e-7` .
- El `Bool` tipo representa un valor booleano que puede ser `true` o `false` .
- El `Range` tipo representa una secuencia de enteros, indicada por `start..step..stop` , donde denota que el paso es opciones. 
   Esto se `start .. stop` corresponde con `start..1..stop` y, por ejemplo, `1..2..7` representa la secuencia $ \{ 1, 3, 5, 7 \} $.
- El `String` tipo es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.
  Este tipo se utiliza para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.
- El `Unit` tipo es el tipo que solo permite un valor `()` . 
  Este tipo se usa para indicar que la operación o la función Q # no devuelve ninguna información. 
- El `Qubit` tipo representa un bit de Quantum o qubit.
   `Qubit`s son opacos para el usuario; la única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).
   En última instancia, las acciones en `Qubit` s se implementan llamando a instrucciones intrínsecas en un procesador Quantum (o en una simulación de la misma).
- El `Pauli` tipo representa uno de los cuatro operadores de Pauli de qubit único.
   Este tipo se utiliza para denotar la operación base para los giros y para especificar el objeto observable que se va a medir.
   Se trata de un tipo enumerado que tiene cuatro valores posibles: `PauliI` , `PauliX` , `PauliY` y `PauliZ` , que son constantes de tipo `Pauli` .
- El `Result` tipo representa el resultado de una medida.
   Se trata de un tipo enumerado con dos valores posibles: `One` y `Zero` , que son constantes de tipo `Result` .
   `Zero`indica que se ha medido + 1 eigenvalue; `One`indica-1 eigenvalue.

Las constantes, `true` `false` , `PauliI` , `PauliX` , `PauliY` , `PauliZ` , `One` y `Zero` son símbolos reservados en Q #.

## <a name="array-types"></a>Tipos de matriz

Dado cualquier tipo de Q # válido `'T` , existe un tipo que representa una matriz de valores de tipo `'T` .
Este tipo de matriz se representa como `'T[]` ; por ejemplo, `Qubit[]` o `Int[][]` .
Por ejemplo, se denota una colección de enteros `Int[]` , mientras que se denota una matriz de `(Bool, Pauli)` valores `(Bool, Pauli)[][]` .

En el segundo ejemplo, tenga en cuenta que esto representa una matriz potencialmente escalonada de matrices, y no una matriz bidimensional rectangular.
Q # no proporciona compatibilidad con matrices multidimensionales rectangulares.

Un valor de matriz se puede escribir en el código fuente de Q # mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]` .
El tipo de un literal de matriz viene determinado por el tipo base común de todos los elementos de la matriz. 

> [!WARNING]
> Los elementos de una matriz no se pueden cambiar una vez creada la matriz.
> Las [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) y/o las [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) se pueden usar para construir una matriz modificada.

Como alternativa, se puede crear una matriz a partir de su tamaño mediante la `new` palabra clave:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

En cualquier caso, una vez construida una matriz, `Length` se puede utilizar la función principal para obtener el número de elementos como `Int` .
Las matrices se pueden incluir entre corchetes, con los subíndices de tipo `Int` o tipo `Range` , para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.
Los subíndices de las matrices son de base cero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos de tupla

Dado cero o más tipos diferentes `T0` , `T1` ,..., `Tn` , podemos denotar un nuevo *tipo de tupla* como `(T0, T1, ..., Tn)` .
Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))` .
Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.

Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.
Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)` .
Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas, etc.

A partir de Q # 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor*de tupla vacío.

Las instancias de tupla son inmutables.
Q # no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.

Las tuplas son un concepto eficaz que se usa en Q # para recopilar valores en un único valor, lo que facilita su paso.
En concreto, mediante la notación de tupla, podemos expresar que cada operación y a la que se puede llamar toma exactamente una entrada y devuelve exactamente una salida.

### <a name="singleton-tuple-equivalence"></a>Equivalencia de tupla singleton

Es posible crear una tupla singleton (elemento único), `('T1)` , como `(5)` o `([1,2,3])` .
Sin embargo, Q # trata una tupla singleton como totalmente equivalente a un valor del tipo delimitado.
Es decir, no hay ninguna diferencia entre `5` y `(5)` , o entre `5` y `(((5)))` , o entre `(5, (6))` y `(5, 6)` .
Es como válido escribir `(5)+3` como para escribir `5+3` y ambas expresiones se evaluarán como `8` .

Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.
Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.
Por ejemplo, `(7)` es una expresión `Int` , `([1,2,3])` es una expresión de tipo matriz de `Int` s y `((1,2))` es una expresión con tipo `(Int, Int)` .

En concreto, esto significa que una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo se puede considerar como tomar un único argumento o devolver un valor único.

Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_.


## <a name="user-defined-types"></a>Tipos definidos por el usuario

Una declaración de tipos definidos por el usuario se compone de la palabra clave `newtype` , seguida del nombre del tipo definido por el usuario, un `=` , una especificación de tipo válida y un punto y coma de finalización.

Por ejemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada archivo de código fuente de Q # puede declarar cualquier número de tipos definidos por el usuario.
Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.

Los tipos definidos por el usuario son distintos aunque los tipos base sean idénticos.
En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.

### <a name="named-vs-anonymous-items"></a>Elementos con nombre frente a elementos anónimos

Un archivo de preguntas # puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.
Para cualquier tipo `T` de tupla, se puede declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la `newtype` instrucción.
En el @"microsoft.quantum.math" espacio de nombres, por ejemplo, los números complejos se definen como un tipo definido por el usuario:

```qsharp
newtype Complex = (Double, Double);
```
Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double` .   

Además de los elementos anónimos, los tipos definidos por el usuario también admiten *elementos con nombre* a partir de la versión 0,7 o posterior. Por ejemplo, podríamos haber llamado a items `Re` para el Double que representa la parte real de un número complejo y `Im` para la parte imaginaria: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre. Además, los elementos internos también se pueden denominar.
El tipo `Nested` tal y como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))` , del que solo se denomina el elemento de tipo `Int` y todos los demás elementos son anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del *operador de acceso* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.
Volviendo al ejemplo de `Complex` , también podría haber definido coordenadas polares 2D como un tipo definido por el usuario:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Aunque ambos `Complex` `Polar` tienen un tipo subyacente `(Double, Double)` , los dos tipos son totalmente incompatibles en Q #, lo que minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.
De esta manera, los tipos definidos por el usuario tienen un rol similar como registros en F #, por ejemplo. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Obtener acceso a elementos anónimos con el operador Unwrap

Para tener acceso a los elementos anónimos por otro lado, el valor ajustado primero debe extraerse mediante el operador postfijo `!` .
El operador "Unwrap", `!` , permite extraer el valor contenido en un tipo definido por el usuario.
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

Puede encontrar más detalles sobre el operador Unwrap en [expresiones de tipo en Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Crear valores de tipos definidos por el usuario

Los valores de un tipo definido por el usuario se pueden crear llamando al constructor de tipo correspondiente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Como alternativa, se pueden crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Al igual que en el caso de las matrices, estas expresiones copian todos los valores de los elementos de la expresión original, con la excepción de los elementos con nombre especificados. Estos valores se establecen en los que se definen en el lado derecho de la expresión. Cualquier otra construcción de lenguaje, como por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), que están disponibles para los elementos de matriz existen también para los elementos con nombre en los tipos definidos por el usuario.

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

Nota no es posible crear estructuras de tipo recursivas.
Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.
En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no sería válido:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Tipos de operación y función

El tipo básico de cualquier que se pueda llamar se escribe como `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)` , donde `'Tinput` y `'Tresult` son tipos.
Estos se denominan la *firma* de que se puede llamar.

Todas las llamadas a Q # pueden tomar un valor único como entrada y devolver un valor único como salida.
Los valores de entrada y salida pueden ser tuplas.
Se puede llamar a que no se devuelve ningún resultado `Unit` .
Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.

> [!NOTE]
> El primer formulario, con `=>` , se utiliza para las operaciones; el segundo formulario, con `->` , para las funciones.
> Por ejemplo, `((Qubit, Pauli) => Result)` representa la firma de una posible operación de medición de un solo qubit.
Los tipos de *función* se especifican completamente mediante su firma.
Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)` .

*Las operaciones*---pero no las funciones---tienen ciertas características adicionales que se expresan como parte del tipo de operación. Estas características incluyen información *sobre los elementos que admite* la operación.
Por ejemplo, si la ejecución de la operación se puede condicionar en el estado de otros qubits, debe admitir el `Controlled` functor; si la operación tiene un inverso, debe admitir el `Adjoint` functor. Los funcdores y las operaciones se describen en detalle en [operaciones y funciones en Q #](xref:microsoft.quantum.guide.operationsfunctions), pero aquí simplemente se describe cómo modifica la firma de la operación.

Para requerir la compatibilidad con `Controlled` y/o `Adjoint` functor en un tipo de operación, es necesario agregar una anotación que indique las características correspondientes.
Una anotación `is Ctl` (por ejemplo `(Qubit => Unit is Ctl)` ,) indica que la operación es controlable---es decir, su ejecución se condiciona en el estado de otro qubit o qubits. Del mismo modo, `is Adj` indica que la operación tiene un tipo contiguo, o simplemente, se puede "invertir" de modo que la aplicación sucesiva de una operación y, a continuación, su unjoin a un estado deja el estado sin cambios. 

Si queremos requerir que una operación de ese tipo admita el `Adjoint` y el `Controlled` functor, podemos expresar esto como `(Qubit => Unit is Adj + Ctl)` . Por ejemplo, la operación Pauli integrada <xref:microsoft.quantum.intrinsic.x> tiene el tipo `(Qubit => Unit is Adj + Ctl)` . 

Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.

### <a name="type-parameterized-functions-and-operations"></a>Operaciones y funciones con parámetros de tipo

Los tipos a los que se puede llamar pueden contener parámetros de tipo.
Los parámetros de tipo se indican mediante un símbolo precedido por una comilla simple; por ejemplo, `'A` es un parámetro de tipo válido.
En las [operaciones y funciones de la página de preguntas y respuestas](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , se proporcionan detalles sobre cómo definir llamadas parametrizadas con parámetros de tipo.

Un parámetro de tipo puede aparecer más de una vez en una sola firma.
Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tendría la firma `(('A[], 'A->'A) -> 'A[])` .
Del mismo modo, una función que devuelve la composición de dos operaciones podría tener la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.

Q # no proporciona un mecanismo para restringir los tipos posibles que se pueden sustituir por un parámetro de tipo.

## <a name="whats-next"></a>¿Qué debe hacer a continuación?
Ahora que ha visto todos los tipos que componen el lenguaje de preguntas y respuestas, puede ver las [expresiones de tipo en q #](xref:microsoft.quantum.guide.expressions) para ver cómo crear y manipular expresiones de estos diversos tipos.


