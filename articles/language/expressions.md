---
title: Expresiones | Microsoft Docs
description: Expresiones
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185212"
---
# <a name="expressions"></a>Expresiones

## <a name="grouping"></a>Agrupación

Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.
Por ejemplo, `(7)` es una expresión `Int`, `([1,2,3])` es una expresión de tipo array de `Int`s y `((1,2))` es una expresión con el tipo `(Int, Int)`.

La equivalencia entre los valores simples y las tuplas de un solo elemento que se describen en [el modelo de tipo](xref:microsoft.quantum.language.type-model#tuple-types) elimina la ambigüedad entre `(6)` como un grupo y `(6)` como una tupla de un solo elemento.

## <a name="symbols"></a>Euro

El nombre de un símbolo enlazado o asignado a un valor de tipo `'T` es una expresión de tipo `'T`.
Por ejemplo, si el `count` de símbolos se enlaza al valor entero `5`, `count` es una expresión de tipo entero.

## <a name="numeric-expressions"></a>Expresiones numéricas

Las expresiones numéricas son expresiones de tipo `Int`, `BigInt`o `Double`.
Es decir, son números enteros o de punto flotante.

`Int` literales en Q # son idénticos a los literales enteros C#en, excepto en que no se requiere (o se permite) ninguna "l" o "l" final.
Los enteros hexadecimales y binarios se admiten con un prefijo "0x" y "0B", respectivamente.

`BigInt` literales en Q # son idénticos a cadenas de tipo entero Big en .NET, con una "l" o "L" final.
Los enteros Big hexadecimales se admiten con un prefijo "0x".
Por lo tanto, a continuación se muestran todos los usos válidos de `BigInt` literales:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` literales en Q # son idénticos a los literales C#dobles de, salvo que no se requiere (o se permite) ninguna "d" o "d" final.

Dada una expresión de matriz de cualquier tipo de elemento, una expresión `Int` se puede formar utilizando la función integrada `Length`, con la expresión de matriz entre paréntesis, `(` y `)`.
Por ejemplo, si `a` se enlaza a una matriz, `Length(a)` es una expresión de tipo entero.
Si `b` es una matriz de matrices de enteros, `Int[][]`, `Length(b)` es el número de submatrices de `b`y `Length(b[1])` es el número de enteros de la segunda submatriz de `b`...

Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+`, `-`, `*`y `/` se pueden usar para formar una nueva expresión numérica.
El tipo de la nueva expresión será el mismo que los tipos de las expresiones constituyentes.

Dadas dos expresiones de tipo entero, el operador binario `^` (Power) se puede usar para formar una nueva expresión de tipo entero.
Del mismo modo, `^` se pueden utilizar con dos expresiones Double para formar una nueva expresión Double.
Por último, se puede usar `^` con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.
En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.

Dadas dos expresiones integer o Big Integer, se puede formar una nueva expresión de tipo entero o grande con los operadores `%` (módulo), `&&&` (and bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).

Dado un entero o una expresión de tipo entero grande a la izquierda, y una expresión de entero a la derecha, se pueden usar los operadores `<<<` (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que el lado izquierdo. Expresiones.

El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.
La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.
Si el número que se va a desplazar es un entero, la cantidad de desplazamiento se interpreta `mod 64`; es decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.

En el caso de los valores entero y Big Integer, ShiftS es aritmético.
Si se desplaza un valor negativo a la izquierda o a la derecha, se producirá un número negativo.
Es decir, el desplazamiento de un paso a la izquierda o a la derecha es exactamente el mismo que si se multiplica o se divide por 2, respectivamente.

La división de enteros y los módulos de enteros siguen el mismo comportamiento para los C#números negativos que.
Es decir, `a % b` siempre tendrá el mismo signo que `a`y `b * (a / b) + a % b` siempre será igual `a`.
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

Dado cualquier expresión integer o Big Integer, se puede formar una nueva expresión del mismo tipo mediante el operador unario `~~~` (complemento bit a bit).

## <a name="boolean-expressions"></a>Expresiones booleanas

Los dos `Bool` valores literales son `true` y `false`.

Dadas dos expresiones cualesquiera del mismo tipo primitivo, se pueden usar los operadores binarios `==` y `!=` para construir una expresión `Bool`.
La expresión será true si las dos expresiones son iguales (resp. no).

No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar sus valores. Por ejemplo,

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

La comparación de igualdad para los valores `Qubit` es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.
Esta comparación no compara, tiene acceso, mide o modifica el estado de los dos qubits.

La comparación de igualdad para los valores de `Double` puede ser engañosa debido a efectos de redondeo.
Por ejemplo, `49.0 * (1.0/49.0) != 1.0`.

Dadas dos expresiones numéricas, se pueden usar los operadores binarios `>`, `<`, `>=`y `<=` para construir una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que , o menor o igual que la segunda expresión.

Dadas dos expresiones booleanas, se pueden usar los operadores binarios `and` y `or` para construir una nueva expresión booleana que es true si las dos expresiones son verdaderas (o ambas).

Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.

## <a name="string-expressions"></a>Expresiones de cadena

Q # permite usar cadenas en la instrucción `fail` y en la función estándar `Log`.

Las cadenas en Q # son literales o cadenas interpoladas.
Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles, `"`.
Dentro de una cadena, el carácter de barra diagonal inversa `\` se puede usar para escapar un carácter de comilla doble e insertar una nueva línea como `\n`, un retorno de carro como `\r`y una tabulación como `\t`.
Por ejemplo:

```qsharp
"\"Hello world!\", she said.\n"
```

La sintaxis de Q # para las interpolaciones de cadenas es un C# subconjunto de la sintaxis 7,0; Q # no admite cadenas interpoladas textuales (multilínea).
Vea [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para la C# sintaxis.

Las expresiones incluidas en una cadena interpolada siguen la sintaxis de Q C# #, no la sintaxis.
Cualquier expresión Q # válida puede aparecer en una cadena interpolada.

## <a name="qubit-expressions"></a>Expresiones qubit

Las únicas expresiones `Qubit` son símbolos que se enlazan a `Qubit` valores o elementos de matriz de matrices de `Qubit`.
No hay literales de `Qubit`.

## <a name="pauli-expressions"></a>Expresiones Pauli

Los cuatro valores `Pauli`, `PauliI`, `PauliX`, `PauliY`y `PauliZ`son expresiones de `Pauli` válidas.

Aparte de eso, las únicas expresiones `Pauli` son símbolos que están enlazados a `Pauli` valores o elementos de matriz de `Pauli` matrices.

## <a name="result-expressions"></a>Expresiones de resultado

Los dos valores `Result`, `One` y `Zero`, son expresiones de `Result` válidas.

Aparte de eso, las únicas expresiones `Result` son símbolos que están enlazados a `Result` valores o elementos de matriz de `Result` matrices.
En concreto, tenga en cuenta que `One` no es el mismo que el `1`entero y no hay ninguna conversión directa entre ellos.
Lo mismo se aplica a `Zero` y `0`.

## <a name="range-expressions"></a>Expresiones de rango

Dadas las tres expresiones `Int` `start`, `step`y `stop`, `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start`, el segundo elemento es `start+step`, el tercer elemento es `start+step+step`, etc., hasta que se pasa `stop`.
Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start`.
El último elemento del intervalo se `stop` si la diferencia entre `start` y `stop` es un múltiplo entero de `step`; es decir, el intervalo es inclusivo en ambos extremos.

Dado dos expresiones `Int` `start` y `stop`, `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop`.
Tenga en cuenta que el `step` implícito es + 1 incluso si `stop` es menor que `start`; en tal caso, el intervalo está vacío.

Algunos intervalos de ejemplo son:

- `1..3` es el intervalo 1, 2, 3.
- `2..2..5` es el intervalo de 2 a 4.
- `2..2..6` es el intervalo 2, 4, 6.
- `6..-2..2` es el rango 6, 4, 2.
- `2..1` es el intervalo vacío.
- `2..6..7` es el intervalo 2.
- `2..2..1` es el intervalo vacío.
- `1..-1..2` es el intervalo vacío.

## <a name="callable-expressions"></a>Expresiones Invocables

Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación.
Por ejemplo, `X` es un literal de operación que hace referencia a la operación de `X` de la biblioteca estándar y `Message` es un literal de función que hace referencia a la función `Message` de la biblioteca estándar.

Si una operación admite la `Adjoint` functor, `Adjoint op` es una expresión de operación.
Del mismo modo, si la operación admite la `Controlled` functor, `Controlled op` es una expresión de operación.
Los tipos de estas expresiones se especifican en [funcs](xref:microsoft.quantum.language.type-model#functors).

Los funcers (`Adjoint` y `Controlled`) se enlazan más estrechamente que todos los demás operadores, excepto el operador Unwrap `!` y la indexación de matrices con `[]`.
Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Un literal al que se puede llamar se puede usar como un valor, por ejemplo, para asignar a una variable o para pasar a otra que se puede llamar.
En este caso, si el que se puede llamar tiene parámetros de tipo, deben proporcionarse como parte del valor al que se puede llamar.
Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado.

Por ejemplo, si `Fun` es una función con `'T1->Unit`de firma:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expresiones de invocación Invocables

Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma de la que se puede llamar, se puede formar una expresión de invocación anexando la expresión de tupla a la expresión a la que se puede llamar.
El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.

Por ejemplo, si `Op` es una operación con `((Int, Qubit) => Double)`de firma, `Op(3, qubit1)` es una expresión de tipo `Double`.
Del mismo modo, si `Sin` es una función con `(Double -> Double)`de firma, `Sin(0.1)` es una expresión de tipo `Double`.
Por último, si `Builder` es una función con `(Int -> (Int -> Int))`de firma, `Builder(3)` es una función de into a int.

La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.
Por lo tanto, para invocar el resultado de llamar a `Builder` del párrafo anterior, la sintaxis correcta es:

```qsharp
(Builder(3))(2)
```

Al invocar un parámetro de tipo al que se puede llamar, los parámetros de tipo reales se pueden especificar entre corchetes angulares `<` y `>` después de la expresión que se puede llamar.
Normalmente esto no es necesario, ya que el compilador de preguntas y respuestas inferirá los tipos reales.
Es necesario para la aplicación parcial (vea más abajo) si no se especifica un argumento con parámetros de tipo.
También es útil a veces cuando se pasan operaciones con un functor diferente para llamar a.

Por ejemplo, si `Func` tiene `('T1, 'T2, 'T1) -> 'T2`de firma, `Op1` y `Op2` tienen `(Qubit[] => Unit is Adj)`de firma, y `Op3` tiene `(Qubit[] => Unit)`de firma, para invocar `Func` con `Op1` como primer argumento, `Op2` como segundo. y `Op3` como el tercero:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.

### <a name="partial-application"></a>Aplicación parcial

Dada una expresión invocable, se puede crear una nueva a la que se pueda llamar proporcionando un subconjunto de los argumentos al que se puede llamar.
Esto se denomina _aplicación parcial_.

En Q #, una función de llamada parcialmente aplicada se expresa escribiendo una expresión de invocación normal, pero usando un carácter de subrayado, `_`, para los argumentos no especificados.
La operación invocable resultante tiene el mismo tipo de resultado que la base a la que se puede llamar y las mismas especializaciones para las operaciones.
El tipo de entrada de la aplicación parcial es simplemente el tipo original con los argumentos especificados quitados.

Si se pasa una variable mutable como argumento especificado al crear una aplicación parcial, se utiliza el valor actual de la variable.
El cambio del valor de la variable después no afectará a la aplicación parcial.

Por ejemplo, si `Op` tiene el tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` tiene el tipo `(((Qubit,Qubit), Double) => Unit is Adj)`y, por tanto, tiene `Op(5,_)`.
- `Op(_,(_,1.0))` tiene el tipo `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))` tiene el tipo `((Int,Double) => Unit is Adj)`.
   Tenga en cuenta que hemos aplicado aquí la equivalencia de tupla singleton.

Si la llamada aplicada parcialmente tiene parámetros de tipo que el compilador no puede inferir, deben proporcionarse en el sitio de invocación.
La aplicación parcial no puede tener ningún parámetro de tipo no especificado.

Por ejemplo, si `Op` tiene el tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Recursividad

Se permite que las llamadas a Q # sean recursivas directa o indirectamente.
Es decir, una operación o función se puede llamar a sí misma, o puede llamar a otra llamada invocable que llama directa o indirectamente a la operación que se puede llamar.

Sin embargo, hay dos comentarios importantes sobre el uso de la recursividad:

- Es probable que el uso de la recursividad en las operaciones interfiera con ciertas optimizaciones.
  Esto puede tener un impacto considerable en el tiempo de ejecución del algoritmo.
- Cuando se ejecuta en un dispositivo Quantum real, el espacio de pila puede estar limitado y, por tanto, la recursividad profunda puede provocar un error en tiempo de ejecución.
  En concreto, el compilador y el tiempo de ejecución de Q # no identifican y optimizan la recursividad del final.

## <a name="tuple-expressions"></a>Expresiones de tupla

Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, delimitadas por `(` y `)`.
Por ejemplo, `(1, One)` es una expresión de `(Int, Result)`.

Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.

## <a name="user-defined-type-expressions"></a>Expresiones de tipo definido por el usuario

Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.
Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)`, `IntPair(2,3)` sería un literal válido de ese tipo.

Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.

## <a name="unwrap-expressions"></a>Desencapsular expresiones

En Q #, el operador Unwrap es un signo de exclamación final `!`.
Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)`y `s` era una variable con `IntPair(2,3)`de valor, `s!` sería `(2,3)`.

Para los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario. el operador Unwrap puede repetirse; por ejemplo, `s!!` indica el valor doble de desencapsulado de `s`.
Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair`y `t` es una variable con `WrappedPair(IntPair(1,2))`de valor, `t!!` se `(1,2)`.

El operador `!` tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.
`!` y `[]` enlazar de posición; es decir, `a[i]![3]` se debe leer como `((a[i])!)[3]`: tome el `i`elemento de `a`, desajustelo y, a continuación, obtenga el tercer elemento del valor desencapsulado (que debe ser una matriz).

La precedencia del operador `!` tiene un impacto que podría no ser obvio.
Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.
Por ejemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expresiones de matriz

Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, delimitadas por `[` y `]`.
Todos los elementos deben ser compatibles con el mismo tipo.

Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.
El tipo de elemento de la matriz será compatible con cualquier functor que admitan todos los elementos.
Por ejemplo, si se `Qubit[] => Unit``Op1`, `Op2`y `Op3` todos, pero `Op1` admite `Adjoint`, `Op2` admite `Controlled`y `Op3` admite ambos:

- `[Op1, Op2]` es una matriz de operaciones de `(Qubit[] => Unit)`.
- `[Op1, Op3]` es una matriz de operaciones de `(Qubit[] => Unit is Adj)`.
- `[Op2, Op3]` es una matriz de operaciones de `(Qubit[] => Unit is Ctl)`.

No se permiten literales de matriz vacíos, `[]`.
En lugar de usar `new ★[0]`, donde `★` es como marcador de posición para un tipo adecuado, permite crear la matriz deseada de longitud cero.

Dadas dos matrices del mismo tipo, se puede utilizar el operador binario `+` para formar una nueva matriz que es la concatenación de las dos matrices.
Por ejemplo, `[1,2,3] + [4,5,6]` es `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Creación de matriz

Dado un tipo y una expresión de `Int`, el operador de `new` se puede utilizar para asignar una nueva matriz del tamaño especificado.
Por ejemplo, `new Int[i+1]` asignaría una nueva matriz de `Int` con elementos `i+1`.

Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.
En la mayoría de los casos, se trata de una variación de cero.

Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.
Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede utilizar sin que se produzca un error en tiempo de ejecución.
Esto es similar a una referencia nula en lenguajes como C# o Java.
Las matrices que contienen qubits o llamadas se deben inicializar correctamente con valores no predeterminados antes de que sus elementos se puedan usar de forma segura. En <xref:microsoft.quantum.arrays>se pueden encontrar rutinas de inicialización adecuadas.

Los valores predeterminados para cada tipo son:

Type | Valor predeterminado
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _qubit no válido_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Rango vacío, `1..1..0`
 `Callable` | _no válido_
 `Array['T]` | `'T[0]`

Los tipos de tupla se inicializan elemento a elemento.


### <a name="jagged-arrays"></a>Matrices escalonadas

Una matriz escalonada, a veces denominada "matriz de matrices", es una matriz cuyos elementos son matrices. Los elementos de una matriz escalonada pueden tener distintos tamaños. En el ejemplo siguiente se muestra cómo declarar e inicializar una matriz escalonada que representa una tabla de multiplicación.

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


### <a name="array-slices"></a>Segmentos de matriz

Dada una expresión de matriz y una expresión de `Range`, se puede formar una nueva expresión mediante el operador `[` y `]` segmento de la matriz.
La nueva expresión será del mismo tipo que la matriz y contendrá los elementos de matriz indizados por los elementos de la `Range`, en el orden definido por la `Range`.
Por ejemplo, si `a` está enlazado a una matriz de `Double`s, `a[3..-1..0]` es una expresión de `Double[]` que contiene los cuatro primeros elementos de `a`, pero en orden inverso a medida que aparecen en `a`.

Si el `Range` está vacío, el segmento de la matriz resultante tendrá una longitud de cero.

Si la expresión de matriz no es un identificador simple, debe encerrarse entre paréntesis para segmentar.
Por ejemplo, si `a` y `b` son matrices de `Int`s, un segmento de la concatenación se expresaría como:

```qsharp
(a+b)[1..2..7]
```

Todas las matrices en Q # son de base cero.
Es decir, el primer elemento de una matriz `a` siempre se `a[0]`.

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

## <a name="array-element-expressions"></a>Expresiones de elementos de matriz

Dada una expresión de matriz y una expresión de `Int`, se puede formar una nueva expresión mediante el operador de elementos de matriz `[` y `]`.
La nueva expresión será del mismo tipo que el tipo de elemento de la matriz.
Por ejemplo, si `a` está enlazado a una matriz de `Double`s, `a[4]` es una expresión de `Double`.

Si la expresión de matriz no es un identificador simple, debe encerrarse entre paréntesis para poder seleccionar un elemento.
Por ejemplo, si `a` y `b` son matrices de `Int`s, un elemento de la concatenación se expresaría como:

```qsharp
(a+b)[13]
```

Todas las matrices en Q # son de base cero.
Es decir, el primer elemento de una matriz `a` siempre se `a[0]`.


## <a name="copy-and-update-expressions"></a>Expresiones de copia y actualización

Las nuevas matrices se pueden crear a partir de las existentes a través de expresiones de copia y actualización.
Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3`, donde `expression1` debe ser de tipo `T[]` para algún tipo `T`. La segunda `expression2` define los índices de los elementos que se van a modificar en comparación con la matriz de `expression1` y debe ser de tipo `Int` o de `Range`. Si `expression2` es de tipo `Int`, `expression3` debe ser de tipo `T`. Si `expression2` es de tipo `Range`, `expression3` debe ser de tipo `T[]`.

Una expresión de copia y actualización `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en el elemento correspondiente en `arr`, excepto los elementos de `idx`, que se establecen en los elementos de la `value`. Por ejemplo, si `arr` contiene una matriz `[0,1,2,3]`, 
- `arr w/ 0 <- 10` es la matriz `[10,1,2,3]`.
- `arr w/ 2 <- 10` es la matriz `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` es la matriz `[10,1,12,3]`.

Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario. Considere, por ejemplo, el tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Si `c` contiene el valor de tipo `Complex(1.,-1.)`, `c w/ Re <- 0.` es una expresión de tipo `Complex` que se evalúa como `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Expresiones condicionales

Dadas otras dos expresiones del mismo tipo y una expresión booleana, la expresión condicional se puede formar con el signo de interrogación `?` y la barra vertical `|`.
Por ejemplo, `a==b ? c | d`.
En este ejemplo, el valor de la expresión condicional será `c` si `a==b` es true y `d` si es false.

Las dos expresiones pueden evaluarse como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores.
En este caso, el tipo de la expresión condicional es una operación con esas entradas y salidas que admite cualquier functor compatible con ambas expresiones.
Por ejemplo, si se `Qubit[]=>Unit``Op1`, `Op2`y `Op3` todos, pero `Op1` admite `Adjoint`, `Op2` admite `Controlled`y `Op3` admite ambos:

- `flag ? Op1 | Op2` es una operación de `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` es una operación de `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` es una operación de `(Qubit[] => Unit is Ctl)`.

Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tendrá lugar si ese resultado es el que será el valor de la llamada.
Por ejemplo, en el caso `a==b ? C(qs) | D(qs)`, si `a==b` es true, se invocará la operación de `C` y, si es false, solo se invocará `D`.
Esto es similar a la cortocircuito en otros lenguajes.


## <a name="operator-precedence"></a>Precedencia de operadores

Todos los operadores binarios son asociativos a la derecha, excepto en el caso de `^`.

Los corchetes, `[` y `]`para la segmentación e indización de matrices, se enlazan antes que cualquier operador.

Los funcrs `Adjoint` y `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.

Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.

Operadores en orden de prioridad, de mayor a menor:

Operator | Polaridad | description | Tipos de operando
---------|----------|---------|---------------
 `!` finales | Unario | Desencapsulado | Cualquier tipo definido por el usuario
 `-`, `~~~`, `not` | Unario | Negativo numérico, complemento bit a bit, negación lógica | `Int`, `BigInt` o `Double` para `-`, `Int` o `BigInt` para `~~~``Bool` `not`
 `^` | Binary | Potencia de entero | `Int` o `BigInt` para la base `Int` para el exponente
 `/`, `*`, `%` | Binary | División, multiplicación, módulo de entero | `Int`, `BigInt` o `Double` para `/` y `*`, `Int` o `BigInt` para `%`
 `+`, `-` | Binary | Suma, concatenación de cadenas y matrices, resta | `Int`, `BigInt` o `Double`, además `String` o cualquier tipo de matriz para `+`
 `<<<`, `>>>` | Binary | Desplazamiento a la izquierda, desplazamiento a la derecha | `Int` o `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Comparaciones menor que, menor o igual que, mayor que, mayor o igual que. | `Int`, `BigInt` o `Double`
 `==`, `!=` | Binary | comparaciones iguales y no iguales | cualquier tipo primitivo
 `&&&` | Binary | And bit a bit | `Int` o `BigInt`
 `^^^` | Binary | XOR bit a bit | `Int` o `BigInt`
 <code>\|\|\|</code> | Binary | OR bit a bit | `Int` o `BigInt`
 `and` | Binary | AND lógico | `Bool`
 `or` | Binary | OR lógico | `Bool`
 `..` | Binario/ternario | Range (operador) | `Int`
 `?``|` | Ternario | Condicional | `Bool` para el lado izquierdo
`w/``<-` | Ternario | Copiar y actualizar | vea [expresiones de copia y actualización](#copy-and-update-expressions)
