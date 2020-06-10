---
title: 'Expresiones de tipo en Q #'
description: 'Aprenda a especificar, hacer referencia y combinar constantes, variables, operadores, operaciones y funciones como expresiones en Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630000"
---
# <a name="type-expressions-in-q"></a>Expresiones de tipo en Q #

## <a name="numeric-expressions"></a>Expresiones numéricas

Las expresiones numéricas son expresiones de tipo `Int` , `BigInt` o `Double` .
Es decir, son números enteros o de punto flotante.

`Int`los literales en Q # se escriben simplemente como una secuencia de dígitos.
Los enteros hexadecimales y binarios se admiten con un `0x` `0b` prefijo y, respectivamente.

`BigInt`los literales en Q # se escriben con un `l` sufijo o final `L` .
Los enteros Big hexadecimales se admiten con un prefijo "0x".
Por lo tanto, los siguientes son usos válidos de los `BigInt` literales:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`los literales de Q # son números de punto flotante escritos con dígitos decimales.
Se pueden escribir con un separador decimal, `.` y/o una parte exponencial indicada con ' e ' o ' e ' (después de los cuales solo hay un posible signo negativo y dígitos decimales válidos).
Los siguientes son `Double` literales válidos: `0.0` , `1.2e5` , `1e-5` .

Dada una expresión de matriz de cualquier tipo de elemento, una `Int` expresión se puede formar utilizando la [`Length`](xref:microsoft.quantum.core.length) función integrada, con la expresión de matriz entre paréntesis, `(` y `)` .
Por ejemplo, si `a` está enlazado a una matriz, `Length(a)` es una expresión de entero.
Si `b` es una matriz de matrices de enteros, `Int[][]` , entonces `Length(b)` es el número de submatrices de y `b` `Length(b[1])` es el número de enteros de la segunda submatriz de `b` .

Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+` ,, `-` `*` y `/` se pueden usar para formar una nueva expresión numérica.
El tipo de la nueva expresión será el mismo que los tipos de las expresiones constituyentes.

Dadas dos expresiones de tipo entero, el operador binario `^` (Power) se puede usar para formar una nueva expresión de tipo entero.
De forma similar, `^` se puede usar con dos expresiones Double para formar una nueva expresión Double.
Por último, `^` se puede usar con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.
En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.

Dadas dos expresiones integer o Big Integer, se puede formar una nueva expresión de tipo entero o Big Integer mediante los `%` operadores (modulus), `&&&` (AND bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).

Dado un entero o una expresión Big Integer a la izquierda, y una expresión de entero a la derecha, `<<<` se pueden usar los operadores (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que la expresión de la izquierda.

El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.
La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.
Si el número que se va a desplazar es un entero, se interpreta la cantidad de desplazamiento, es `mod 64` decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.

En el caso de los valores entero y Big Integer, ShiftS es aritmético.
Si se desplaza un valor negativo a la izquierda o a la derecha, se producirá un número negativo.
Es decir, el desplazamiento de un paso a la izquierda o a la derecha es exactamente el mismo que si se multiplica o se divide por 2, respectivamente.

La división de enteros y los módulos de enteros siguen el mismo comportamiento para los números negativos que en C#.
Es decir, `a % b` siempre tendrá el mismo signo que `a` y `b * (a / b) + a % b` siempre será igual que `a` .
Por ejemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

La división y el módulo Big Integer funcionan de la misma manera.

Dada cualquier expresión numérica, se puede formar una nueva expresión mediante el `-` operador unario.
La nueva expresión será del mismo tipo que la expresión constituyente.

Dado cualquier expresión integer o Big Integer, se puede formar una nueva expresión del mismo tipo mediante el `~~~` operador unario (complemento bit a bit).

## <a name="boolean-expressions"></a>Expresiones booleanas

Los dos `Bool` valores literales son `true` y `false` .

Dadas dos expresiones cualesquiera del mismo tipo primitivo, `==` `!=` se pueden usar los operadores binarios y para construir una `Bool` expresión.
La expresión será true si las dos expresiones son iguales y false en caso contrario.

No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar los valores desencapsulados. Por ejemplo, mediante el operador "Unwrap" `!` (que se explica en detalle en [tipos en Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

La comparación de igualdad para `Qubit` los valores es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.
Esta comparación no compara, tiene acceso, mide o modifica el estado de los dos qubits.

La comparación de igualdad de `Double` los valores puede ser engañosa debido a efectos de redondeo.
Por ejemplo, `49.0 * (1.0/49.0) != 1.0` .

Dadas dos expresiones numéricas, los operadores binarios `>` ,, `<` `>=` y `<=` se pueden usar para crear una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que, o menor o igual que la segunda expresión.

Dadas dos expresiones booleanas, se `and` `or` pueden usar los operadores binarios y para construir una nueva expresión booleana que es true si las dos expresiones son verdaderas (o ambas).

Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.

## <a name="string-expressions"></a>Expresiones de cadena

Q # permite usar cadenas en la `fail` instrucción (explicadas en el [flujo de control](xref:microsoft.quantum.guide.controlflow#fail-statement)) y en la [`Message`](xref:microsoft.quantum.intrinsic.message) función estándar.
El comportamiento específico de este último depende del simulador utilizado, pero normalmente escribe un mensaje en la consola del host cuando se llama durante un programa de preguntas y respuestas.

Las cadenas en Q # son literales o cadenas interpoladas.

Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles, `"` .
Dentro de una cadena, el carácter de barra diagonal inversa `\` se puede usar para escapar un carácter de comillas dobles e insertar una nueva línea como `\n` , un retorno de carro como `\r` y una tabulación como `\t` .
Por ejemplo:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Cadenas interpoladas

La sintaxis de Q # para las interpolaciones de cadenas es un subconjunto de la sintaxis de C#, pero se resumen aquí los puntos clave tal y como se relacionan con preguntas y respuestas.
A continuación se describen las distinciones principales.

Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.
No puede haber ningún espacio en blanco entre `$` y `"` que inicia un literal de cadena.

El siguiente es un ejemplo básico que usa la [`Message`](xref:microsoft.quantum.intrinsic.message) función para escribir el resultado de una medida en la consola, junto con otras expresiones de Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Cualquier expresión Q # válida puede aparecer en una cadena interpolada.

Puede encontrar más información sobre la sintaxis de C# en [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
La diferencia más notable es que Q # no admite cadenas interpoladas textuales (multilínea).
Las expresiones incluidas en una cadena interpolada siguen la sintaxis de Q #, no la sintaxis de C#.

## <a name="range-expressions"></a>Expresiones de rango

Dadas las tres `Int` expresiones `start` , y, `step` `stop` `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start` , el segundo elemento es, el `start+step` tercer elemento es `start+step+step` , etc., hasta que `stop` se pasa.
Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start` .
El último elemento del intervalo será `stop` si la diferencia entre `start` y `stop` es un múltiplo entero de; es `step` decir, el intervalo es inclusivo en ambos extremos.

Dadas dos `Int` expresiones cualesquiera `start` y `stop` , `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop` .
Observe que el implícito `step` es + 1 incluso si `stop` es menor que `start` ; en tal caso, el intervalo está vacío.

Algunos intervalos de ejemplo son:

- `1..3`es el intervalo de 1, 2, 3.
- `2..2..5`es el intervalo de 2 a 4.
- `2..2..6`es el intervalo de 2, 4, 6.
- `6..-2..2`es el rango 6, 4, 2.
- `2..1`es el intervalo vacío.
- `2..6..7`es el intervalo 2.
- `2..2..1`es el intervalo vacío.
- `1..-1..2`es el intervalo vacío.

## <a name="qubit-expressions"></a>Expresiones qubit

Las únicas `Qubit` expresiones son símbolos que se enlazan a `Qubit` valores o elementos de matriz de `Qubit` matrices.
No hay `Qubit` literales.

## <a name="pauli-expressions"></a>Expresiones Pauli

Los cuatro `Pauli` valores,,, `PauliI` `PauliX` `PauliY` y `PauliZ` , son expresiones válidas `Pauli` .

Aparte de eso, las únicas `Pauli` expresiones son símbolos que se enlazan a `Pauli` valores o elementos de matriz de `Pauli` matrices.

## <a name="result-expressions"></a>Expresiones de resultado

Los dos `Result` valores, `One` y `Zero` , son expresiones válidas `Result` .

Aparte de eso, las únicas `Result` expresiones son símbolos que se enlazan a `Result` valores o elementos de matriz de `Result` matrices.
En concreto, tenga en cuenta que `One` no es igual que el entero `1` y no hay ninguna conversión directa entre ellos.
Lo mismo se cumple para `Zero` y `0` .

## <a name="tuple-expressions"></a>Expresiones de tupla

Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, entre `(` y `)` .
Por ejemplo, `(1, One)` es una `(Int, Result)` expresión.

Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.

## <a name="user-defined-type-expressions"></a>Expresiones de tipo definido por el usuario

Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.
Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)` , `IntPair(2, 3)` sería un literal válido de ese tipo.

Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.

## <a name="unwrap-expressions"></a>Desencapsular expresiones

En Q #, el operador Unwrap es un signo de exclamación final `!` .
Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)` y `s` era una variable con el valor `IntPair(2, 3)` , `s!` sería `(2, 3)` .

En el caso de los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario, el operador Unwrap puede repetirse; por ejemplo, `s!!` indica el valor de doble desencapsulado de `s` .
Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair` , y `t` es una variable con el valor `WrappedPair(IntPair(1,2))` , entonces `t!!` sería `(1,2)` .

El `!` operador tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.
`!`y `[]` enlazar positionly; es decir, `a[i]![3]` se debe leer como `((a[i])!)[3]` : tomar el `i` elemento ' th de `a` , desencapsularlo y, a continuación, obtener el tercer elemento del valor desencapsulado (que debe ser una matriz).

La precedencia del `!` operador tiene un impacto que podría no ser obvio.
Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.
Por ejemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expresiones de matriz

Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, entre `[` y `]` .
Todos los elementos deben ser compatibles con el mismo tipo.

Dadas dos matrices del mismo tipo, `+` se puede utilizar el operador binario para formar una nueva matriz que es la concatenación de las dos matrices.
Por ejemplo, `[1,2,3] + [4,5,6]` es `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Creación de matriz

Dado un tipo y una `Int` expresión, el `new` operador se puede utilizar para asignar una nueva matriz del tamaño especificado.
Por ejemplo, `new Int[i + 1]` asignaría una nueva `Int` matriz con `i + 1` elementos.

No se permiten literales de matriz vacíos, `[]` ,.
En lugar `new ★[0]` de usar, donde `★` es un marcador de posición para un tipo adecuado, permite crear la matriz deseada de longitud cero.

Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.
En la mayoría de los casos, se trata de una variación de cero.

Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.
Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede utilizar sin que se produzca un error en tiempo de ejecución.
Esto es similar a una referencia nula en lenguajes como C# o Java.
Las matrices que contienen qubits o llamadas se deben inicializar correctamente con valores no predeterminados antes de que sus elementos se puedan usar de forma segura. Se pueden encontrar rutinas de inicialización adecuadas en <xref:microsoft.quantum.arrays> .

Los valores predeterminados para cada tipo son:

Tipo | Valor predeterminado
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _qubit no válido_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | El intervalo vacío,`1..1..0`
 `Callable` | _no válido_
 `Array['T]` | `'T[0]`

Los tipos de tupla se inicializan elemento a elemento.


### <a name="array-elements"></a>Elementos de matriz

Dada una expresión de matriz y una `Int` expresión, se puede formar una nueva expresión mediante `[` el `]` operador de elemento de matriz y.
La nueva expresión será del mismo tipo que el tipo de elemento de la matriz.
Por ejemplo, si `a` está enlazado a una matriz de `Double` s, `a[4]` es una `Double` expresión.

Si la expresión de matriz no es un identificador simple, se debe incluir entre paréntesis para poder seleccionar un elemento.
Por ejemplo, si `a` y `b` son matrices de `Int` s, un elemento de la concatenación se expresaría como:

```qsharp
(a + b)[13]
```

Todas las matrices en Q # son de base cero.
Es decir, el primer elemento de una matriz `a` siempre es `a[0]` .


### <a name="array-slices"></a>Segmentos de matriz

Dada una expresión de matriz y una `Range` expresión, se puede formar una nueva expresión mediante `[` el `]` operador de segmento de matriz y.
La nueva expresión será del mismo tipo que la matriz y contendrá los elementos de matriz indizados por los elementos de `Range` , en el orden definido por `Range` .
Por ejemplo, si `a` está enlazado a una matriz de `Double` s, `a[3..-1..0]` es una `Double[]` expresión que contiene los cuatro primeros elementos de, `a` pero en el orden inverso en el que aparecen en `a` .

Si `Range` está vacío, el segmento de la matriz resultante tendrá una longitud de cero.

Al igual que con los elementos de la matriz que hacen referencia, si la expresión de matriz no es un identificador simple, se debe incluir entre paréntesis para segmentar.
Si `a` y `b` son matrices de `Int` s, un segmento de la concatenación se expresaría como:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valores de inicio y fin inferidos

A partir de la versión 0,8, se admiten expresiones contextuales para la segmentación de intervalos. En concreto, los valores de inicio y fin de intervalo se pueden omitir en el contexto de una expresión de división de intervalo. En ese caso, el compilador aplicará las siguientes reglas para deducir los delimitadores deseados para el intervalo. 

Por ejemplo, si se omite el valor de inicio de intervalo, el valor de inicio deducido 
- es cero si no se especifica ningún paso o el paso especificado es positivo, y 
- es la longitud de la matriz segmentada menos uno si el paso especificado es negativo. 

Si se omite el valor final del intervalo, el valor final deducido 
- es la longitud de la matriz segmentada menos uno si no se especifica ningún paso o el paso especificado es positivo, y 
- es cero si el paso especificado es negativo. 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Expresiones de copia y actualización

Dado que todos los tipos de Q # son tipos de valor, con el qubits que toma un rol especialmente especial, se crea formalmente una "copia" cuando se enlaza un valor a un símbolo o cuando se reenlaza un símbolo. Es decir, el comportamiento de Q # es el mismo que si se creara una copia en la asignación.
Por supuesto, en la práctica solo se recrean las piezas relevantes según sea necesario. 

Esto, en concreto, también incluye matrices.
En concreto, no es posible actualizar los elementos de la matriz. Para modificar una matriz existente, es necesario aprovechar un mecanismo de *copia y actualización* .

Las nuevas matrices se pueden crear a partir de las existentes a través de expresiones de *copia y actualización* .
Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3` , donde debe `expression1` ser de tipo `T[]` para algún tipo `T` .
La segunda `expression2` define los índices de los elementos que se van a modificar en comparación con la matriz de `expression1` y debe ser de tipo `Int` o de tipo `Range` .
Si `expression2` es de tipo `Int` , debe `expression3` ser de tipo `T` . Si `expression2` es de tipo `Range` , debe `expression3` ser de tipo `T[]` .

Una expresión de copia y actualización `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en el elemento correspondiente de `arr` , excepto los elementos de `idx` , que se establecen en los elementos de, que están establecidos en `value` . Por ejemplo, si `arr` contiene una matriz `[0,1,2,3]` , 
- `arr w/ 0 <- 10`es la matriz `[10,1,2,3]` .
- `arr w/ 2 <- 10`es la matriz `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`es la matriz `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Expresiones de copiar y actualizar para elementos con nombre

Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario. 

Considere, por ejemplo, el tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Si `c` contiene el valor de tipo `Complex(1., -1.)` , `c w/ Re <- 0.` es una expresión de tipo `Complex` que se evalúa como `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Matrices escalonadas

Una matriz escalonada, a veces denominada "matriz de matrices", es una matriz cuyos elementos son matrices.
Los elementos de una matriz escalonada pueden tener distintos tamaños.
En el ejemplo siguiente se muestra cómo declarar e inicializar una matriz escalonada que representa una tabla de multiplicación.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Matrices de llamadas 

Tenga en cuenta que se pueden encontrar más detalles sobre los tipos a los que se puede llamar, así como en la página siguiente, [operaciones y funciones en Q #](xref:microsoft.quantum.guide.operationsfunctions).

Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.
El tipo de elemento de la matriz será compatible con cualquier functor que admitan todos los elementos.
Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[] => Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:

- `[Op1, Op2]`es una matriz de `(Qubit[] => Unit)` operaciones.
- `[Op1, Op3]`es una matriz de `(Qubit[] => Unit is Adj)` operaciones.
- `[Op2, Op3]`es una matriz de `(Qubit[] => Unit is Ctl)` operaciones.

Sin embargo, `(Qubit[] => Unit is Adj)` mientras `(Qubit[] => Unit is Ctl)` que las operaciones y tienen el tipo base común de `(Qubit[] => Unit)` , tenga en cuenta que las matrices *de* estos operadores no comparten un tipo base común. Por ejemplo, `[[Op1], [Op2]]` generaría un error en este momento porque está intentando crear una matriz de los tipos de matriz incompatibles `(Qubit[] => Unit is Adj)[]` y `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Expresiones condicionales

Dadas otras dos expresiones del mismo tipo y una expresión booleana, la expresión condicional se puede formar mediante el signo de interrogación `?` y la barra vertical `|` .
Por ejemplo, `a==b ? c | d` .
En este ejemplo, el valor de la expresión condicional será `c` si `a==b` es true y `d` si es false.

### <a name="conditional-expressions-with-callables"></a>Expresiones condicionales con llamadas

Las dos expresiones pueden evaluarse como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores.
En este caso, el tipo de la expresión condicional es una operación con esas entradas y salidas que admite cualquier functor compatible con ambas expresiones.
Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[]=>Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:

- `flag ? Op1 | Op2`es una `(Qubit[] => Unit)` operación.
- `flag ? Op1 | Op3`es una `(Qubit[] => Unit is Adj)` operación.
- `flag ? Op2 | Op3`es una `(Qubit[] => Unit is Ctl)` operación.

Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tendrá lugar si ese resultado es el que será el valor de la llamada.
Por ejemplo, en caso de que `a==b ? C(qs) | D(qs)` `a==b` sea true, se `C` invocará la operación y, si es false, solo se `D` invocará.
Esto es similar a la cortocircuito en otros lenguajes.

## <a name="callable-expressions"></a>Expresiones Invocables

Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación.
Por ejemplo, `X` es un literal de operación que hace referencia a la operación de la biblioteca estándar `X` y `Message` es un literal de función que hace referencia a la función de la biblioteca estándar `Message` .

Si una operación admite el `Adjoint` functor, `Adjoint op` es una expresión de operación.
Del mismo modo, si la operación admite el `Controlled` functor, `Controlled op` es una expresión de operación.
Los tipos de estas expresiones se especifican en las [especializaciones](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)de la operación de llamada.

Los funcrs ( `Adjoint` y `Controlled` ) se enlazan más estrechamente que todos los demás operadores, salvo el operador Unwrap `!` y la indización de matriz con [] '.
Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expresiones Invocables con parámetros de tipo

Un literal al que se puede llamar se puede usar como un valor, por ejemplo, para asignar a una variable o para pasar a otra que se puede llamar.
En este caso, si el que se puede llamar tiene [parámetros de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), deben proporcionarse como parte del valor al que se puede llamar.
Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado.

Por ejemplo, si `Fun` es una función con firma `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expresiones de invocación Invocables

Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma de la que se puede llamar, se puede formar una expresión de invocación anexando la expresión de tupla a la expresión a la que se puede llamar.
El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.

Por ejemplo, si `Op` es una operación con firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` es una expresión de tipo `Double` .
Del mismo modo, si `Sin` es una función con firma `(Double -> Double)` , `Sin(0.1)` es una expresión de tipo `Double` .
Por último, si `Builder` es una función con firma `(Int -> (Int -> Int))` , `Builder(3)` es una función de into a int.

La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.
Por lo tanto, para invocar el resultado de llamar a `Builder` desde el párrafo anterior, la sintaxis correcta es:

```qsharp
(Builder(3))(2)
```

Al invocar un [parámetro de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) invocable, los parámetros de tipo reales se pueden especificar entre corchetes angulares `<` y `>` después de la expresión que se puede llamar.
Normalmente esto no es necesario, ya que el compilador de preguntas y respuestas inferirá los tipos reales.
Sin embargo, *es* necesario para la [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si no se especifica un argumento con parámetros de tipo.
También es útil a veces cuando se pasan operaciones con un functor diferente para llamar a.

Por ejemplo, si `Func` tiene Signature `('T1, 'T2, 'T1) -> 'T2` , `Op1` y `Op2` tiene Signature, `(Qubit[] => Unit is Adj)` y `Op3` tiene Signature `(Qubit[] => Unit)` , para invocar `Func` con `Op1` como primer argumento, `Op2` como el segundo y `Op3` como el tercero:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.


## <a name="operator-precedence"></a>Prioridad de los operadores

Todos los operadores binarios son asociativos a la derecha, excepto `^` .

Los corchetes y `[` `]` , para la segmentación e indización de matrices, se enlazan antes que cualquier operador.

Los funcrs `Adjoint` y se `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.

Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.

Operadores en orden de prioridad, de mayor a menor:

Operador | Polaridad | Descripción | Tipos de operando
---------|----------|---------|---------------
 finales`!` | Unario | Desencapsulado | Cualquier tipo definido por el usuario
 `-`, `~~~`, `not` | Unario | Negativo numérico, complemento bit a bit, negación lógica | `Int`, `BigInt` o `Double` para `-` , `Int` o `BigInt` para `~~~` , `Bool` para`not`
 `^` | Binary | Potencia de entero | `Int`o `BigInt` para la base, `Int` para el exponente
 `/`, `*`, `%` | Binary | División, multiplicación, módulo de entero | `Int`, `BigInt` o `Double` para `/` y `*` , `Int` o `BigInt` para`%`
 `+`, `-` | Binary | Suma, concatenación de cadenas y matrices, resta | `Int`, `BigInt` o `Double` , además, `String` o cualquier tipo de matriz para`+`
 `<<<`, `>>>` | Binary | Desplazamiento a la izquierda, desplazamiento a la derecha | `Int` o `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Comparaciones menor que, menor o igual que, mayor que, mayor o igual que. | `Int`, `BigInt` o`Double`
 `==`, `!=` | Binary | comparaciones iguales y no iguales | cualquier tipo primitivo
 `&&&` | Binary | AND bit a bit | `Int` o `BigInt`
 `^^^` | Binary | XOR bit a bit | `Int` o `BigInt`
 <code>\|\|\|</code> | Binary | OR bit a bit | `Int` o `BigInt`
 `and` | Binary | Y lógico | `Bool`
 `or` | Binary | O lógico | `Bool`
 `..` | Binario/ternario | Range (operador) | `Int`
 `?` `|` | Ternario | Condicional | `Bool`para el lado izquierdo
`w/` `<-` | Ternario | Copiar y actualizar | vea [expresiones de copia y actualización](#copy-and-update-expressions)

## <a name="next-steps"></a>Pasos siguientes

Ahora que puede trabajar con expresiones en Q #, puede empezar a usar [operaciones y funciones en q #](xref:microsoft.quantum.guide.operationsfunctions) para obtener información sobre cómo definir y llamar a operaciones y funciones.
