---
title: Expresiones enQ#
description: Aprenda a especificar, hacer referencia y combinar constantes, variables, operadores, operaciones y funciones como expresiones en Q# .
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869620"
---
# <a name="expressions-in-no-locq"></a>Expresiones enQ#

## <a name="numeric-expressions"></a>Expresiones numéricas

Las expresiones numéricas son expresiones de tipo `Int` , `BigInt` o `Double` .
Es decir, son números enteros o de punto flotante.

`Int`los literales de Q# se escriben como una secuencia de dígitos.
Los enteros hexadecimales y binarios se admiten y se escriben con un `0x` `0b` prefijo y, respectivamente.

`BigInt`los literales de Q# tienen un `l` sufijo o final `L` .
Los enteros Big hexadecimales se admiten y se escriben con un prefijo "0x".
Por lo tanto, los siguientes son usos válidos de los `BigInt` literales:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`los literales de Q# son números de punto flotante escritos con dígitos decimales.
Se pueden escribir con o sin un separador decimal, `.` o una parte exponencial indicada con ' e ' o ' e ' (después de los cuales solo hay un posible signo negativo y dígitos decimales válidos).
Los siguientes son `Double` literales válidos: `0.0` , `1.2e5` , `1e-5` .

Dada una expresión de matriz de cualquier tipo de elemento, puede formar una `Int` expresión mediante la [`Length`](xref:microsoft.quantum.core.length) función integrada, con la expresión de matriz entre paréntesis.
Por ejemplo, si `a` está enlazado a una matriz, `Length(a)` es una expresión de entero.
Si `b` es una matriz de matrices de enteros, `Int[][]` , entonces `Length(b)` es el número de submatrices de y `b` `Length(b[1])` es el número de enteros de la segunda submatriz de `b` .

Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+` ,, `-` `*` y `/` se pueden usar para formar una nueva expresión numérica.
El tipo de la nueva expresión es igual que los tipos de las expresiones constituyentes.

Dadas dos expresiones de entero, utilice el operador binario `^` (Power) para formar una nueva expresión de tipo entero.
Del mismo modo, también puede utilizar `^` con dos expresiones dobles para formar una nueva expresión Double.
Por último, puede usar `^` con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.
En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se genera un error en tiempo de ejecución.

Dado dos expresiones integer o Big Integer, forman un nuevo entero o una expresión Big Integer mediante los `%` operadores (modulus), `&&&` (AND bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).

Dado un entero o una expresión Big Integer a la izquierda, y una expresión de entero a la derecha, use los `<<<` operadores (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que la expresión de la izquierda.

El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.
La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se genera un error en tiempo de ejecución.
Si el número que se desplaza es un entero, se interpreta la cantidad de desplazamiento, es `mod 64` decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.

En el caso de los valores entero y Big Integer, ShiftS es aritmético.
Al desplazar un valor negativo a la izquierda o a la derecha, se obtiene un número negativo.
Es decir, el desplazamiento de un paso a la izquierda o a la derecha equivale a multiplicar u dividir por 2, respectivamente.

La división de enteros y los módulos de enteros siguen el mismo comportamiento para los números negativos que en C#.
Es decir, `a % b` siempre tiene el mismo signo que `a` y `b * (a / b) + a % b` siempre es igual a `a` .
Por ejemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Las operaciones de división y módulo Big Integer funcionan de la misma manera.

Dado cualquier expresión numérica, puede formar una nueva expresión mediante el `-` operador unario.
La nueva expresión es del mismo tipo que la expresión constituyente.

Dado cualquier expresión integer o Big Integer, puede formar una nueva expresión del mismo tipo mediante el `~~~` operador unario (complemento bit a bit).

## <a name="boolean-expressions"></a>Expresiones booleanas

Los dos `Bool` valores literales son `true` y `false` .

Dadas dos expresiones cualesquiera del mismo tipo primitivo, `==` `!=` se pueden usar los operadores binarios y para construir una `Bool` expresión.
La expresión es true si las dos expresiones son iguales y false en caso contrario.

No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar los valores desencapsulados. Por ejemplo, mediante el operador "desencapsular" (que se `!` explica en detalle en los [tipos de Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

La comparación de igualdad para `Qubit` los valores es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.
Esta comparación no compara, tiene acceso, mide o modifica los Estados de los dos qubits.

La comparación de igualdad de `Double` los valores puede ser engañosa debido a efectos de redondeo.
Por ejemplo: `49.0 * (1.0/49.0) != 1.0`.

Dadas dos expresiones numéricas, los operadores binarios `>` ,, `<` `>=` y `<=` se pueden usar para crear una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que, o menor o igual que la segunda expresión.

Dado dos expresiones booleanas cualesquiera, utilice el `and` operador binario para construir una nueva expresión booleana que sea true si ambas expresiones son verdaderas. Del mismo modo, el uso del `or` operador crea una expresión que es true si cualquiera de las dos expresiones es true.

Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.

## <a name="string-expressions"></a>Expresiones de cadena

Q#permite usar cadenas en la `fail` instrucción (explicada en el [flujo de control](xref:microsoft.quantum.guide.controlflow#fail-statement)) y en la [`Message`](xref:microsoft.quantum.intrinsic.message) función estándar. El comportamiento específico de este último depende del simulador utilizado, pero normalmente escribe un mensaje en la consola del host cuando se llama durante un Q# programa.

Las cadenas de Q# son literales o cadenas interpoladas.

Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles `" "` .
Dentro de una cadena, use el carácter de barra diagonal inversa `\` para escapar un carácter de comilla doble ( `\"` ) o para insertar una nueva línea ( `\n` ), un retorno de carro ( `\r` ) o una tabulación ( `\t` ).
Por ejemplo:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Cadenas interpoladas

La Q# Sintaxis de las interpolaciones de cadenas es un subconjunto de la sintaxis de C#. A continuación se enumeran los puntos clave en los que se relacionan Q# :

* Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`. No puede haber ningún espacio en blanco entre `$` y `"` que inicia un literal de cadena.

* El siguiente es un ejemplo básico que usa la [`Message`](xref:microsoft.quantum.intrinsic.message) función para escribir el resultado de una medida en la consola, junto con otras Q# expresiones.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Cualquier Q# expresión válida puede aparecer en una cadena interpolada.

* Las expresiones dentro de una cadena interpolada siguen la Q# sintaxis, no la sintaxis de C#. La diferencia más notable es que no Q# admite cadenas interpoladas textuales (multilínea).

Para obtener más información sobre la sintaxis de C#, vea [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Expresiones de rango

Dadas las tres `Int` expresiones `start` , y, `step` `stop` la expresión `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start` , el segundo elemento es, el `start+step` tercer elemento es `start+step+step` , y así sucesivamente, hasta que se pasa `stop` .
Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start` .

El intervalo es inclusivo en ambos extremos. Es decir, si la diferencia entre `start` y `stop` es un entero múltiplo de `step` , el último elemento del intervalo será `stop` .

Dadas dos `Int` expresiones cualesquiera `start` y `stop` , la expresión `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop` .
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

Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, entre paréntesis.
Por ejemplo, `(1, One)` es una `(Int, Result)` expresión.

Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.

## <a name="user-defined-type-expressions"></a>Expresiones de tipo definido por el usuario

Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.
Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)` , `IntPair(2, 3)` es un literal válido de ese tipo.

Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.

## <a name="unwrap-expressions"></a>Desencapsular expresiones

En Q# , el operador Unwrap es un signo de exclamación final `!` .
Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)` y `s` es una variable con el valor `IntPair(2, 3)` , entonces `s!` es `(2, 3)` .

En el caso de los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario, puede repetir el operador Unwrap. Por ejemplo, `s!!` indica el valor de doble desencapsulado de `s` .
Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair` , y `t` es una variable con el valor `WrappedPair(IntPair(1,2))` , entonces `t!!` es `(1,2)` .

El `!` operador tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.
`!`y `[]` enlazar positionly; es decir, `a[i]![3]` se lee como `((a[i])!)[3]` : tomar el `i` ésimo elemento de `a` , desencapsularlo y, a continuación, obtener el tercer elemento del valor desencapsulado (que debe ser una matriz).

La precedencia del `!` operador tiene un impacto que podría no ser obvio.
Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.
Por ejemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expresiones de matriz

Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, entre corchetes `[]` .
Todos los elementos deben ser compatibles con el mismo tipo.

Dadas dos matrices del mismo tipo, utilice el operador binario `+` para formar una nueva matriz que es la concatenación de las dos matrices.
Por ejemplo, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Creación de matriz

Dado un tipo y una `Int` expresión, utilice el `new` operador para asignar una nueva matriz del tamaño especificado.
Por ejemplo, `new Int[i + 1]` asigna una nueva `Int` matriz con `i + 1` elementos.

No se permiten literales de matriz vacíos, como `[]` .
En su lugar, puede crear una matriz de longitud cero mediante `new T[0]` , donde `T` es un marcador de posición para un tipo adecuado.

Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.
En la mayoría de los casos, se trata de una variación de cero.

Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.
Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede usar sin producir un error en tiempo de ejecución, similar a una referencia nula en lenguajes como C# o Java.
Las matrices que contienen qubits o Invocables se deben inicializar con valores no predeterminados antes de poder usar sus elementos de forma segura. Para ver las rutinas de inicialización adecuadas, vea <xref:microsoft.quantum.arrays> .

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

Los tipos de tupla inicializan elemento a elemento.


### <a name="array-elements"></a>Elementos de matriz

Dada una expresión de matriz y una `Int` expresión, forme una nueva expresión mediante el operador del elemento de matriz `[]` .
La nueva expresión es del mismo tipo que el tipo de elemento de la matriz.
Por ejemplo, si `a` está enlazado a una matriz de tipo `Double` , entonces `a[4]` es una `Double` expresión.

Si la expresión de matriz no es un identificador simple, debe encerrarla entre paréntesis para seleccionar un elemento.
Por ejemplo, si `a` y `b` son matrices de tipo `Int` , un elemento de la concatenación se expresa como:

```qsharp
(a + b)[13]
```

Todas las matrices de Q# están basadas en cero.
Es decir, el primer elemento de una matriz `a` siempre es `a[0]` .


### <a name="array-slices"></a>Segmentos de matriz

Dada una expresión de matriz y una `Range` expresión, forme una expresión nueva mediante el operador de segmento de matriz `[ ]` .
La nueva expresión es del mismo tipo que la matriz y contiene los elementos de matriz indizados por los elementos de `Range` , en el orden definido por `Range` .
Por ejemplo, si `a` está enlazado a una matriz de tipo `Double` , entonces `a[3..-1..0]` es una `Double[]` expresión que contiene los cuatro primeros elementos de `a` pero en el orden inverso en el que aparecen en `a` .

Si `Range` está vacío, el segmento de la matriz resultante tiene una longitud de cero.

Al igual que con los elementos de la matriz que hacen referencia, si la expresión de matriz no es un identificador simple, debe encerrarla entre paréntesis para segmentarla.
Por ejemplo, si `a` y `b` son matrices de tipo `Int` , un segmento de la concatenación se expresa como:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valores de inicio y fin inferidos

A partir de la [versión 0,8](xref:microsoft.quantum.relnotes), se admiten expresiones contextuales para la segmentación de intervalos. En concreto, puede omitir los valores de inicio y fin de intervalo en el contexto de una expresión de división de intervalo. En ese caso, el compilador aplica las siguientes reglas para deducir los delimitadores deseados para el intervalo:

* Si se omite el valor de *Inicio* del intervalo, el valor de inicio deducido
  * es cero si no se especifica ningún paso o el paso especificado es positivo.  
  * es la longitud de la matriz segmentada menos uno si el paso especificado es negativo.

* Si se omite el valor *final* del intervalo, el valor final deducido
  * es la longitud de la matriz segmentada menos uno si no se especifica ningún paso o el paso especificado es positivo.
  * es cero si el paso especificado es negativo.

Ejemplos:

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

Dado que todos los Q# tipos son tipos de valor (con el qubits que toma un rol en cierto modo especial), se crea formalmente una "copia" cuando un valor se enlaza a un símbolo o cuando se reenlaza un símbolo. Es decir, el comportamiento de Q# es el mismo que si se creara una copia mediante un operador de asignación. 

Por supuesto, en la práctica, solo se recrean las piezas relevantes según sea necesario. Esto afecta al modo en que se copian las matrices, ya que no es posible actualizar los elementos de la matriz. Para modificar una matriz existente, es necesario aprovechar un mecanismo de *copia y actualización* .

Puede crear una nueva matriz a partir de una matriz existente a través de expresiones de *copia y actualización* , que utilizan los operadores `w/` y `<-` .
Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3` , donde

* `expression1`debe ser `T[]` de tipo para algún tipo `T` .
* `expression2`define los índices de la matriz especificada en `expression1` que se van a modificar. `expression2`debe ser de tipo `Int` o de tipo `Range` .
* `expression3`es el valor o los valores utilizados para actualizar los elementos de `expression1` , en función de los índices especificados en `expression2` . Si `expression2` es `Int` de tipo, `expression3` debe ser de tipo `T` . Si `expression2` es `Range` de tipo, `expression3` debe ser de tipo `T[]` .

Por ejemplo, la expresión de copiar y actualizar `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en los elementos correspondientes en `arr` , excepto los elementos especificados por `idx` , que se establecen en los valores de `value` . 

Dado `arr` contiene la matriz `[0,1,2,3]` , 

- `arr w/ 0 <- 10`es la matriz `[10,1,2,3]` .
- `arr w/ 2 <- 10`es la matriz `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`es la matriz `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Expresiones de copiar y actualizar para elementos con nombre

Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario. 

Por ejemplo, considere el tipo. 

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

También puede crear una matriz de llamadas Invocables.

* Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.
* El tipo de elemento de la matriz admite cualquier [funcón](xref:microsoft.quantum.guide.operationsfunctions) que admitan todos los elementos.
Por ejemplo, si `Op1` , `Op2` y `Op3` todas son `Qubit[] => Unit` operaciones, pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:
  * `[Op1, Op2]`es una matriz de `(Qubit[] => Unit)` operaciones.
  * `[Op1, Op3]`es una matriz de `(Qubit[] => Unit is Adj)` operaciones.
  * `[Op2, Op3]`es una matriz de `(Qubit[] => Unit is Ctl)` operaciones.

Sin embargo, mientras que las operaciones `(Qubit[] => Unit is Adj)` y `(Qubit[] => Unit is Ctl)` tienen el tipo base común de `(Qubit[] => Unit)` , las *matrices* de estas operaciones no comparten un tipo base común.

Por ejemplo, `[[Op1], [Op2]]` generaría un error en este momento porque intenta crear una matriz de los dos tipos de matriz incompatibles `(Qubit[] => Unit is Adj)[]` y `(Qubit[] => Unit is Ctl)[]` .

Para obtener más información sobre las llamadas Invocables, vea [expresiones Invocables](#callable-expressions) en esta página u [ Q# operaciones y funciones en ](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Expresiones condicionales

Dadas dos expresiones del mismo tipo y una expresión booleana, forman una expresión condicional mediante el signo de interrogación, `?` y la barra vertical `|` . Dado `a==b ? c | d` , el valor de la expresión condicional es `c` si `a==b` es true y `d` si es false.

### <a name="conditional-expressions-with-callables"></a>Expresiones condicionales con llamadas

Las expresiones condicionales se pueden evaluar como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores. En este caso, el tipo de la expresión condicional es una operación con entradas y salidas que admiten los inactivos admitidos por ambas expresiones.
Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[]=>Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:

- `flag ? Op1 | Op2`es una `(Qubit[] => Unit)` operación.
- `flag ? Op1 | Op3`es una `(Qubit[] => Unit is Adj)` operación.
- `flag ? Op2 | Op3`es una `(Qubit[] => Unit is Ctl)` operación.

Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tiene lugar si el resultado es el que es el valor de la llamada. Por ejemplo, en el caso de que `a==b ? C(qs) | D(qs)` `a==b` sea true, `C` se invoca la operación y, si es false, solo `D` se invoca la operación. Este enfoque es *similar a la cortocircuito* en otros lenguajes.

## <a name="callable-expressions"></a>Expresiones Invocables

Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación. Por ejemplo, `X` es un literal de operación que hace referencia a la operación de la biblioteca estándar `X` y `Message` es un literal de función que hace referencia a la función de la biblioteca estándar `Message` .

Si una operación admite el `Adjoint` functor, `Adjoint op` es una expresión de operación.
Del mismo modo, si la operación admite el `Controlled` functor, `Controlled op` es una expresión de operación.
Para obtener más información sobre los tipos de estas expresiones, vea [llamar a las especializaciones](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)de la operación.

Los funcrs ( `Adjoint` y `Controlled` ) se enlazan más estrechamente que todos los demás operadores, salvo el operador Unwrap `!` y la indización de matriz con `[ ]` .
Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expresiones Invocables con parámetros de tipo

Puede usar un literal invocable como un valor, por ejemplo, para asignarlo a una variable o pasarlo a otro que se pueda llamar. En este caso, si el que se puede llamar tiene [parámetros de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), debe proporcionar los parámetros como parte del valor al que se puede llamar.

Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado. Por ejemplo, si `Fun` es una función con la firma `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expresiones de invocación Invocables

Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma del que se puede llamar, puede formar una *expresión de invocación* anexando la expresión de tupla a la expresión que se puede llamar.
El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.

Por ejemplo, si `Op` es una operación con la firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` es una expresión de tipo `Double` .
Del mismo modo, si `Sin` es una función con la firma `(Double -> Double)` , `Sin(0.1)` es una expresión de tipo `Double` .
Por último, si `Builder` es una función con la firma `(Int -> (Int -> Int))` , `Builder(3)` es una función de `Int` a `Int` .

La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.
Por lo tanto, para invocar el resultado de llamar a `Builder` desde el párrafo anterior, la sintaxis correcta es:

```qsharp
(Builder(3))(2)
```

Al invocar un [parámetro de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) al que se puede llamar, se pueden especificar los parámetros de tipo reales entre corchetes angulares `< >` después de la expresión que se puede llamar.
Normalmente, esta acción no es necesaria, ya que el Q# compilador deduce los tipos reales.
Sin embargo, *es* necesario para la [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si no se especifica un argumento con parámetros de tipo.
También resulta útil cuando se pasan operaciones con un funcr diferente a una que se puede llamar.

Por ejemplo, si `Func` tiene Signature `('T1, 'T2, 'T1) -> 'T2` , `Op1` y `Op2` tiene Signature, `(Qubit[] => Unit is Adj)` y `Op3` tiene Signature `(Qubit[] => Unit)` , para invocar `Func` con `Op1` como primer argumento, `Op2` como el segundo, y `Op3` como el tercero:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.


## <a name="operator-precedence"></a>Prioridad de los operadores

* Todos los operadores binarios son asociativos a la derecha, excepto `^` .

* Los corchetes, `[ ]` , para la segmentación e indización de matrices, se enlazan antes que cualquier operador.

* Los funcrs `Adjoint` y se `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.

* Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.

Q#operadores en orden de prioridad, de mayor a menor:

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
`w/` `<-` | Ternario | Copiar y actualizar | Vea [expresiones de copia y actualización](#copy-and-update-expressions)

## <a name="next-steps"></a>Pasos siguientes

Ahora que puede trabajar con expresiones en Q# , vaya a [operaciones y funciones en Q# ](xref:microsoft.quantum.guide.operationsfunctions) para obtener información sobre cómo definir y llamar a operaciones y funciones.
