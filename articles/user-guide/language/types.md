---
title: Tipos de Q#
description: Obtenga información sobre los diferentes tipos que se usan en el Q# lenguaje de programación.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691610"
---
# <a name="types-in-no-locq"></a>Tipos de Q#

En este artículo se describe el Q# modelo de tipo y la sintaxis para especificar y trabajar con tipos. Para obtener más información sobre cómo crear y operar en expresiones de estos tipos, vea [expresiones de tipo](xref:microsoft.quantum.guide.expressions).

Tenemos en cuenta que Q# es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los Q# programas en tiempo de compilación.
Para proporcionar las garantías más fuertes posibles, las conversiones entre los tipos de Q# deben ser explícitas mediante llamadas a funciones que expresan esa conversión. 
Q# proporciona una gran variedad de funciones como parte del espacio de <xref:Microsoft.Quantum.Convert> nombres.
Las reversiones a tipos compatibles, por otro lado, se producen implícitamente. 

Q# proporciona ambos tipos primitivos, que se utilizan directamente, y diversas maneras de generar nuevos tipos a partir de otros tipos.
En el resto de este artículo se describe cada uno de ellos.

## <a name="primitive-types"></a>Tipos primitivos

El Q# lenguaje proporciona los siguientes *tipos primitivos* , que se pueden usar directamente en los Q# programas. También puede usar estos tipos primitivos para construir nuevos tipos.

- El `Int` tipo representa un entero con signo de 64 bits, por ejemplo, `2` , `107` , `-5` .
- El `BigInt` tipo representa un entero con signo de tamaño arbitrario, por ejemplo, `2L` , `107L` , `-5L` .
   Este tipo se basa en .NET <xref:System.Numerics.BigInteger>
   .

- El `Double` tipo representa un número de punto flotante de precisión doble, por ejemplo, `0.0` , `-1.3` , `4e-7` .
- El `Bool` tipo representa un valor booleano de `true` o `false` .
- El `Range` tipo representa una secuencia de enteros, indicada por `start..step..stop` , donde la indicación del paso es opcional. 
   Por ejemplo, `start .. stop` corresponde a `start..1..stop` y `1..2..7` representa la secuencia $ \{ 1, 3, 5, 7 \} $.
- El `String` tipo es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.
  Use el `string` tipo para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.
- El `Unit` tipo solo puede tener un valor, `()` . 
  Utilice este tipo para indicar que una Q# función u operación no devuelve información. 
- El `Qubit` tipo representa un bit de Quantum o qubit.
   `Qubit`los s son opacos para el usuario. La única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).
   En última instancia, se implementan acciones en `Qubit` s llamando a instrucciones intrínsecas en un procesador Quantum (o un simulador Quantum).
- El `Pauli` tipo representa uno de los cuatro operadores de Pauli de qubit único.
   Utilice este tipo para indicar la operación base para los giros y especificar el objeto observable que se va a medir.
   Es un tipo enumerado que tiene cuatro valores posibles: `PauliI` , `PauliX` , `PauliY` y `PauliZ` , que son constantes de tipo `Pauli` .
- El `Result` tipo representa el resultado de una medida.
   Es un tipo enumerado con dos valores posibles: `One` y `Zero` , que son constantes de tipo `Result` .
   `Zero` indica que se ha medido + 1 eigenvalue; `One` indica que se midió-1 eigenvalue.

Las constantes, `true` , `false` `PauliI` , `PauliX` , `PauliY` , `PauliZ` , `One` y `Zero` son símbolos reservados en Q# .

## <a name="array-types"></a>Tipos de matriz

* Para cualquier Q# tipo válido, existe un tipo que representa una matriz de valores de ese tipo.
    Por ejemplo, `Qubit[]` y `(Bool, Pauli)[]` representan matrices de `Qubit` valores y `(Bool, Pauli)` valores de tupla.

* Una matriz de matrices también es válida. Al expandir el ejemplo anterior, se denota una matriz de `(Bool, Pauli)` matrices `(Bool, Pauli)[][]` .

> [!NOTE] 
> En este ejemplo, `(Bool, Pauli)[][]` , representa una matriz de matrices potencialmente escalonada y no una matriz bidimensional rectangular. Q# no es compatible con matrices multidimensionales rectangulares.

* Un valor de matriz se puede escribir en Q# el código fuente mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]` .
El tipo base común de todos los elementos de la matriz determina el tipo de un literal de matriz. Por lo tanto, la construcción de una matriz con elementos que no tienen un tipo base común produce un error.  
Para obtener un ejemplo, consulte [matrices de llamadas](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Una vez creados, no se pueden cambiar los elementos de una matriz.
    > Para construir una matriz modificada, use [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) o [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Como alternativa, se puede crear una matriz a partir de su tamaño mediante la `new` palabra clave:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Utilice la función Core `Length` para obtener el número de elementos de una matriz como `Int` .
* Las matrices pueden ser de subíndice para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.
Los subíndices de las matrices tienen una base cero y deben ser de tipo `Int` o tipo `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Tipos de tupla

Las tuplas son un concepto eficaz que se usa Q# para recopilar valores en un único valor, lo que facilita su paso.
En concreto, mediante la notación de tupla, puede expresar que cada operación y invocable toma exactamente una entrada y devuelve exactamente una salida.

* Dado cero o más tipos diferentes `T0` , `T1` ,..., `Tn` , puede denotar un nuevo  *tipo de tupla* como `(T0, T1, ..., Tn)` .
Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))` .
Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.

* Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.
Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)` .
Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas y así sucesivamente.

* A partir de Q# 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor* de la tupla vacía.

* Las instancias de tupla son inmutables.
Q# no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.



### <a name="singleton-tuple-equivalence"></a>Equivalencia de tupla singleton

Es posible crear una tupla singleton (elemento único) `('T1)` , como `(5)` o `([1,2,3])` .
Sin embargo, Q# trata una tupla singleton como equivalente a un valor del tipo delimitado.
Es decir, no hay ninguna diferencia entre `5` y `(5)` , o entre `5` y `(((5)))` , o entre `(5, (6))` y `(5, 6)` .
Es como válido escribir `(5)+3` como para escribir `5+3` ; ambas expresiones se evalúan como `8` .

Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.
Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.
Por ejemplo, `(7)` es una expresión de tipo `Int` , `([1,2,3])` es una expresión de tipo `Int[]` y `((1,2))` es una expresión de tipo `(Int, Int)` .

En concreto, esto significa que puede ver una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo que toma un solo argumento o devuelve un valor único.

Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_ .


## <a name="user-defined-types"></a>Tipos definidos por el usuario

Una declaración de tipos definidos por el usuario se compone de la palabra clave `newtype` , seguida del nombre del tipo definido por el usuario, un `=` , una especificación de tipo válida y un punto y coma de finalización.

Por ejemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Cada Q# archivo de código fuente puede declarar cualquier número de tipos definidos por el usuario.
* Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.
* Los tipos definidos por el usuario son distintos, aunque los tipos base sean idénticos.
En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.

### <a name="named-vs-anonymous-items"></a>Elementos con nombre frente a elementos anónimos

Un Q# archivo puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.
Para cualquier tipo `T` de tupla, puede declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la `newtype` instrucción.
En el @"microsoft.quantum.math" espacio de nombres, por ejemplo, los números complejos se definen como un tipo definido por el usuario:

```qsharp
newtype Complex = (Double, Double);
```
Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double` .   

Además de los elementos anónimos, los tipos definidos por el usuario también admiten *elementos con nombre* a partir de la Q# versión 0,7 o posterior. Por ejemplo, podría asignar un nombre a los elementos para `Real` el valor Double que representa la parte real de un número complejo y `Imag` para la parte imaginaria: 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre. Además, los elementos internos también se pueden denominar.
El tipo `Nested` , como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))` , del que solo se denomina el elemento de tipo `Int` , y todos los demás elementos son anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del *operador de acceso* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.
Volviendo al ejemplo de `Complex` , también podría haber definido una representación de coordenadas polares como un tipo definido por el usuario:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Aunque ambos `Complex` `ComplexPolar` tienen un tipo subyacente `(Double, Double)` , los dos tipos son totalmente incompatibles en, lo que Q# minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Obtener acceso a elementos anónimos con el operador Unwrap

Para obtener acceso a los elementos anónimos, extraiga primero el valor ajustado mediante el operador postfijo `!` .
Con el operador "Unwrap", `!` , puede extraer el valor contenido en un tipo definido por el usuario.
El tipo de una expresión "Unwrap" es el tipo subyacente del tipo definido por el usuario. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Un único operador Unwrap desencapsula un nivel de ajuste. Use varios operadores Unwrap para tener acceso a un valor de ajuste de multiplicación.

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

Para obtener más detalles sobre el operador Unwrap, vea [expresiones de Q# tipo en ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Crear valores de tipos definidos por el usuario

Cree valores de un tipo definido por el usuario mediante una llamada al constructor de tipo correspondiente:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Como alternativa, puede crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Del mismo modo que con las matrices, las expresiones de copiar y actualizar copian todos los valores de los elementos de la expresión original, excepto los elementos con nombre especificados. Para estas excepciones, los valores de estos elementos son los valores definidos en el lado derecho de la expresión. Cualquier otra construcción de lenguaje que esté disponible para los elementos de matriz, por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existe también para los elementos con nombre de tipos definidos por el usuario.

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

* Puede usar tipos definidos por el usuario en cualquier lugar en el que use cualquier otro tipo.
En concreto, es posible definir una matriz de un tipo definido por el usuario y incluir un tipo definido por el usuario como elemento de un tipo de tupla.

* No es posible crear estructuras de tipo recursivas.
Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.
En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no es válido:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Tipos de operación y función

Dados los tipos `'Tinput` y `'Tresult` :

* `('Tinput => 'Tresult)` es el tipo básico de cualquier *operación* , por ejemplo `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` es el tipo básico de cualquier *función* , por ejemplo `(Int -> Int)` . 

Estos se denominan la *firma* de que se puede llamar.

* Todas las Q# llamadas a aceptan un valor único como entrada y devuelven un valor único como salida.
* Puede usar tuplas para los valores de entrada y salida.
* Llamadas que no tienen ningún resultado, devuelven `Unit` .
* Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.

### <a name="functors"></a>Funciones

Los tipos de *función* se especifican completamente mediante su firma. Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)` . 

*Las operaciones* tienen ciertas características adicionales que se expresan como parte del tipo de operación. Estas características incluyen información sobre los *inactivos* que admite la operación.
Por ejemplo, si la ejecución de la operación se basa en el estado de otros qubits, debe admitir el `Controlled` functor; si la operación tiene un inverso, debe admitir el `Adjoint` functor.

> [!NOTE]
> En este artículo solo se explica cómo los funcers modifican la firma de la operación. Para obtener más información acerca de los funcrs y las operaciones, vea [operaciones y funciones en Q# ](xref:microsoft.quantum.guide.operationsfunctions). 

Para requerir la compatibilidad con `Controlled` y/o `Adjoint` functor en un tipo de operación, debe agregar una anotación que indique las características correspondientes.
La anotación `is Ctl` (por ejemplo, `(Qubit => Unit is Ctl)` ) indica que la operación es controlable. Es decir, su ejecución se basa en el estado de otro qubit o qubits. Del mismo modo, la anotación `is Adj` indica que la operación tiene un uncontiguo, es decir, se puede "invertir" de modo que la aplicación de una operación sucesivamente y después su contigua a un estado deja el estado sin cambios. 

Si desea exigir que una operación de ese tipo admita `Adjoint` y el `Controlled` functor, puede expresarlo como `(Qubit => Unit is Adj + Ctl)` . Por ejemplo, la operación Pauli integrada <xref:Microsoft.Quantum.Intrinsic.X> tiene el tipo `(Qubit => Unit is Adj + Ctl)` . 

Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.

### <a name="type-parameterized-functions-and-operations"></a>Funciones y operaciones de Type-Parameterized

Los tipos a los que se puede llamar pueden contener *parámetros de tipo* .
Use un símbolo con una comilla simple como prefijo para indicar un parámetro de tipo; por ejemplo, `'A` es un parámetro de tipo válido.
Para obtener más información y detalles sobre cómo definir las llamadas a parámetros de tipo, vea [operaciones y funciones en Q# ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Un parámetro de tipo puede aparecer más de una vez en una sola firma.
Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tiene la firma `(('A[], 'A->'A) -> 'A[])` .
Del mismo modo, una función que devuelve la composición de dos operaciones tiene la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.

Q# no proporciona un mecanismo para restringir los tipos posibles que un usuario puede sustituir para un parámetro de tipo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha visto todos los tipos que componen el Q# lenguaje, vea [expresiones de tipo Q# en](xref:microsoft.quantum.guide.expressions) para obtener información sobre cómo crear y manipular expresiones de estos diversos tipos.
