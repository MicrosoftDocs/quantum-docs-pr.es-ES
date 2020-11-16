---
title: 'Expresiones en Q#'
description: 'Aprenda a especificar, hacer referencia y combinar constantes, variables, operadores, operaciones y funciones como expresiones en Q# .'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691602"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="41fda-103">Expresiones en Q#</span><span class="sxs-lookup"><span data-stu-id="41fda-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="41fda-104">Expresiones numéricas</span><span class="sxs-lookup"><span data-stu-id="41fda-104">Numeric Expressions</span></span>

<span data-ttu-id="41fda-105">Las expresiones numéricas son expresiones de tipo `Int` , `BigInt` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="41fda-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="41fda-106">Es decir, son números enteros o de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="41fda-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="41fda-107">`Int` los literales de Q# se escriben como una secuencia de dígitos.</span><span class="sxs-lookup"><span data-stu-id="41fda-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="41fda-108">Los enteros hexadecimales y binarios se admiten y se escriben con un `0x` `0b` prefijo y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="41fda-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="41fda-109">`BigInt` los literales de Q# tienen un `l` sufijo o final `L` .</span><span class="sxs-lookup"><span data-stu-id="41fda-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="41fda-110">Los enteros Big hexadecimales se admiten y se escriben con un prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="41fda-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="41fda-111">Por lo tanto, los siguientes son usos válidos de los `BigInt` literales:</span><span class="sxs-lookup"><span data-stu-id="41fda-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="41fda-112">`Double` los literales de Q# son números de punto flotante escritos con dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="41fda-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="41fda-113">Se pueden escribir con o sin un separador decimal, `.` o una parte exponencial indicada con ' e ' o ' e ' (después de los cuales solo hay un posible signo negativo y dígitos decimales válidos).</span><span class="sxs-lookup"><span data-stu-id="41fda-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="41fda-114">Los siguientes son `Double` literales válidos: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="41fda-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="41fda-115">Dada una expresión de matriz de cualquier tipo de elemento, puede formar una `Int` expresión mediante la [`Length`](xref:Microsoft.Quantum.Core.Length) función integrada, con la expresión de matriz entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="41fda-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:Microsoft.Quantum.Core.Length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="41fda-116">Por ejemplo, si `a` está enlazado a una matriz, `Length(a)` es una expresión de entero.</span><span class="sxs-lookup"><span data-stu-id="41fda-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="41fda-117">Si `b` es una matriz de matrices de enteros, `Int[][]` , entonces `Length(b)` es el número de submatrices de y `b` `Length(b[1])` es el número de enteros de la segunda submatriz de `b` .</span><span class="sxs-lookup"><span data-stu-id="41fda-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="41fda-118">Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+` ,, `-` `*` y `/` se pueden usar para formar una nueva expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="41fda-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="41fda-119">El tipo de la nueva expresión es igual que los tipos de las expresiones constituyentes.</span><span class="sxs-lookup"><span data-stu-id="41fda-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="41fda-120">Dadas dos expresiones de entero, utilice el operador binario `^` (Power) para formar una nueva expresión de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="41fda-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="41fda-121">Del mismo modo, también puede utilizar `^` con dos expresiones dobles para formar una nueva expresión Double.</span><span class="sxs-lookup"><span data-stu-id="41fda-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="41fda-122">Por último, puede usar `^` con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.</span><span class="sxs-lookup"><span data-stu-id="41fda-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="41fda-123">En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se genera un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="41fda-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="41fda-124">Dado dos expresiones integer o Big Integer, forman un nuevo entero o una expresión Big Integer mediante los `%` operadores (modulus), `&&&` (AND bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).</span><span class="sxs-lookup"><span data-stu-id="41fda-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="41fda-125">Dado un entero o una expresión Big Integer a la izquierda, y una expresión de entero a la derecha, use los `<<<` operadores (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que la expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="41fda-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="41fda-126">El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.</span><span class="sxs-lookup"><span data-stu-id="41fda-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="41fda-127">La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se genera un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="41fda-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="41fda-128">Si el número que se desplaza es un entero, se interpreta la cantidad de desplazamiento, es `mod 64` decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="41fda-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="41fda-129">En el caso de los valores entero y Big Integer, ShiftS es aritmético.</span><span class="sxs-lookup"><span data-stu-id="41fda-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="41fda-130">Al desplazar un valor negativo a la izquierda o a la derecha, se obtiene un número negativo.</span><span class="sxs-lookup"><span data-stu-id="41fda-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="41fda-131">Es decir, el desplazamiento de un paso a la izquierda o a la derecha equivale a multiplicar u dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="41fda-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="41fda-132">La división de enteros y los módulos de enteros siguen el mismo comportamiento para los números negativos que en C#.</span><span class="sxs-lookup"><span data-stu-id="41fda-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="41fda-133">Es decir, `a % b` siempre tiene el mismo signo que `a` y `b * (a / b) + a % b` siempre es igual a `a` .</span><span class="sxs-lookup"><span data-stu-id="41fda-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="41fda-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="41fda-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="41fda-135">5</span><span class="sxs-lookup"><span data-stu-id="41fda-135">5</span></span> | <span data-ttu-id="41fda-136">2</span><span class="sxs-lookup"><span data-stu-id="41fda-136">2</span></span> | <span data-ttu-id="41fda-137">2</span><span class="sxs-lookup"><span data-stu-id="41fda-137">2</span></span> | <span data-ttu-id="41fda-138">1</span><span class="sxs-lookup"><span data-stu-id="41fda-138">1</span></span> |
| <span data-ttu-id="41fda-139">5</span><span class="sxs-lookup"><span data-stu-id="41fda-139">5</span></span> | <span data-ttu-id="41fda-140">-2</span><span class="sxs-lookup"><span data-stu-id="41fda-140">-2</span></span> | <span data-ttu-id="41fda-141">-2</span><span class="sxs-lookup"><span data-stu-id="41fda-141">-2</span></span> | <span data-ttu-id="41fda-142">1</span><span class="sxs-lookup"><span data-stu-id="41fda-142">1</span></span> |
| <span data-ttu-id="41fda-143">-5</span><span class="sxs-lookup"><span data-stu-id="41fda-143">-5</span></span> | <span data-ttu-id="41fda-144">2</span><span class="sxs-lookup"><span data-stu-id="41fda-144">2</span></span> | <span data-ttu-id="41fda-145">-2</span><span class="sxs-lookup"><span data-stu-id="41fda-145">-2</span></span> | <span data-ttu-id="41fda-146">-1</span><span class="sxs-lookup"><span data-stu-id="41fda-146">-1</span></span> |
| <span data-ttu-id="41fda-147">-5</span><span class="sxs-lookup"><span data-stu-id="41fda-147">-5</span></span> | <span data-ttu-id="41fda-148">-2</span><span class="sxs-lookup"><span data-stu-id="41fda-148">-2</span></span> | <span data-ttu-id="41fda-149">2</span><span class="sxs-lookup"><span data-stu-id="41fda-149">2</span></span> | <span data-ttu-id="41fda-150">-1</span><span class="sxs-lookup"><span data-stu-id="41fda-150">-1</span></span> |

<span data-ttu-id="41fda-151">Las operaciones de división y módulo Big Integer funcionan de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="41fda-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="41fda-152">Dado cualquier expresión numérica, puede formar una nueva expresión mediante el `-` operador unario.</span><span class="sxs-lookup"><span data-stu-id="41fda-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="41fda-153">La nueva expresión es del mismo tipo que la expresión constituyente.</span><span class="sxs-lookup"><span data-stu-id="41fda-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="41fda-154">Dado cualquier expresión integer o Big Integer, puede formar una nueva expresión del mismo tipo mediante el `~~~` operador unario (complemento bit a bit).</span><span class="sxs-lookup"><span data-stu-id="41fda-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="41fda-155">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="41fda-155">Boolean Expressions</span></span>

<span data-ttu-id="41fda-156">Los dos `Bool` valores literales son `true` y `false` .</span><span class="sxs-lookup"><span data-stu-id="41fda-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="41fda-157">Dadas dos expresiones cualesquiera del mismo tipo primitivo, `==` `!=` se pueden usar los operadores binarios y para construir una `Bool` expresión.</span><span class="sxs-lookup"><span data-stu-id="41fda-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="41fda-158">La expresión es true si las dos expresiones son iguales y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="41fda-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="41fda-159">No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar los valores desencapsulados.</span><span class="sxs-lookup"><span data-stu-id="41fda-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="41fda-160">Por ejemplo, mediante el operador "desencapsular" (que se `!` explica en detalle en los [tipos de Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="41fda-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="41fda-161">La comparación de igualdad para `Qubit` los valores es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.</span><span class="sxs-lookup"><span data-stu-id="41fda-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="41fda-162">Esta comparación no compara, tiene acceso, mide o modifica los Estados de los dos qubits.</span><span class="sxs-lookup"><span data-stu-id="41fda-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="41fda-163">La comparación de igualdad de `Double` los valores puede ser engañosa debido a efectos de redondeo.</span><span class="sxs-lookup"><span data-stu-id="41fda-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="41fda-164">Por ejemplo, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="41fda-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="41fda-165">Dadas dos expresiones numéricas, los operadores binarios `>` ,, `<` `>=` y `<=` se pueden usar para crear una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que, o menor o igual que la segunda expresión.</span><span class="sxs-lookup"><span data-stu-id="41fda-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="41fda-166">Dado dos expresiones booleanas cualesquiera, utilice el `and` operador binario para construir una nueva expresión booleana que sea true si ambas expresiones son verdaderas.</span><span class="sxs-lookup"><span data-stu-id="41fda-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="41fda-167">Del mismo modo, el uso del `or` operador crea una expresión que es true si cualquiera de las dos expresiones es true.</span><span class="sxs-lookup"><span data-stu-id="41fda-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="41fda-168">Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.</span><span class="sxs-lookup"><span data-stu-id="41fda-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="41fda-169">Expresiones de cadena</span><span class="sxs-lookup"><span data-stu-id="41fda-169">String expressions</span></span>

<span data-ttu-id="41fda-170">Q# permite usar cadenas en la `fail` instrucción (explicada en el [flujo de control](xref:microsoft.quantum.guide.controlflow#fail-statement)) y en la [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) función estándar.</span><span class="sxs-lookup"><span data-stu-id="41fda-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) standard function.</span></span> <span data-ttu-id="41fda-171">El comportamiento específico de este último depende del simulador utilizado, pero normalmente escribe un mensaje en la consola del host cuando se llama durante un Q# programa.</span><span class="sxs-lookup"><span data-stu-id="41fda-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="41fda-172">Las cadenas de Q# son literales o cadenas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="41fda-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="41fda-173">Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles `" "` .</span><span class="sxs-lookup"><span data-stu-id="41fda-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="41fda-174">Dentro de una cadena, use el carácter de barra diagonal inversa `\` para escapar un carácter de comilla doble ( `\"` ) o para insertar una nueva línea ( `\n` ), un retorno de carro ( `\r` ) o una tabulación ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="41fda-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="41fda-175">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="41fda-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="41fda-176">Cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="41fda-176">Interpolated strings</span></span>

<span data-ttu-id="41fda-177">La Q# Sintaxis de las interpolaciones de cadenas es un subconjunto de la sintaxis de C#.</span><span class="sxs-lookup"><span data-stu-id="41fda-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="41fda-178">A continuación se enumeran los puntos clave en los que se relacionan Q# :</span><span class="sxs-lookup"><span data-stu-id="41fda-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="41fda-179">Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="41fda-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="41fda-180">No puede haber ningún espacio en blanco entre `$` y `"` que inicia un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="41fda-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="41fda-181">El siguiente es un ejemplo básico que usa la [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) función para escribir el resultado de una medida en la consola, junto con otras Q# expresiones.</span><span class="sxs-lookup"><span data-stu-id="41fda-181">The following is a basic example using the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="41fda-182">Cualquier Q# expresión válida puede aparecer en una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="41fda-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="41fda-183">Las expresiones dentro de una cadena interpolada siguen la Q# sintaxis, no la sintaxis de C#.</span><span class="sxs-lookup"><span data-stu-id="41fda-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="41fda-184">La diferencia más notable es que no Q# admite cadenas interpoladas textuales (multilínea).</span><span class="sxs-lookup"><span data-stu-id="41fda-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="41fda-185">Para obtener más información sobre la sintaxis de C#, vea [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="41fda-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="41fda-186">Expresiones de rango</span><span class="sxs-lookup"><span data-stu-id="41fda-186">Range Expressions</span></span>

<span data-ttu-id="41fda-187">Dadas las tres `Int` expresiones `start` , y, `step` `stop` la expresión `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start` , el segundo elemento es, el `start+step` tercer elemento es `start+step+step` , y así sucesivamente, hasta que se pasa `stop` .</span><span class="sxs-lookup"><span data-stu-id="41fda-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="41fda-188">Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="41fda-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="41fda-189">El intervalo es inclusivo en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="41fda-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="41fda-190">Es decir, si la diferencia entre `start` y `stop` es un entero múltiplo de `step` , el último elemento del intervalo será `stop` .</span><span class="sxs-lookup"><span data-stu-id="41fda-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="41fda-191">Dadas dos `Int` expresiones cualesquiera `start` y `stop` , la expresión `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="41fda-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="41fda-192">Observe que el implícito `step` es + 1 incluso si `stop` es menor que `start` ; en tal caso, el intervalo está vacío.</span><span class="sxs-lookup"><span data-stu-id="41fda-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="41fda-193">Algunos intervalos de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="41fda-193">Some example ranges are:</span></span>

- <span data-ttu-id="41fda-194">`1..3` es el intervalo de 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="41fda-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="41fda-195">`2..2..5` es el intervalo de 2 a 4.</span><span class="sxs-lookup"><span data-stu-id="41fda-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="41fda-196">`2..2..6` es el intervalo de 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="41fda-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="41fda-197">`6..-2..2` es el rango 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="41fda-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="41fda-198">`2..1` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="41fda-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="41fda-199">`2..6..7` es el intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="41fda-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="41fda-200">`2..2..1` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="41fda-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="41fda-201">`1..-1..2` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="41fda-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="41fda-202">Expresiones qubit</span><span class="sxs-lookup"><span data-stu-id="41fda-202">Qubit Expressions</span></span>

<span data-ttu-id="41fda-203">Las únicas `Qubit` expresiones son símbolos que se enlazan a `Qubit` valores o elementos de matriz de `Qubit` matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="41fda-204">No hay `Qubit` literales.</span><span class="sxs-lookup"><span data-stu-id="41fda-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="41fda-205">Expresiones Pauli</span><span class="sxs-lookup"><span data-stu-id="41fda-205">Pauli Expressions</span></span>

<span data-ttu-id="41fda-206">Los cuatro `Pauli` valores,,, `PauliI` `PauliX` `PauliY` y `PauliZ` , son expresiones válidas `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="41fda-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="41fda-207">Aparte de eso, las únicas `Pauli` expresiones son símbolos que se enlazan a `Pauli` valores o elementos de matriz de `Pauli` matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="41fda-208">Expresiones de resultado</span><span class="sxs-lookup"><span data-stu-id="41fda-208">Result Expressions</span></span>

<span data-ttu-id="41fda-209">Los dos `Result` valores, `One` y `Zero` , son expresiones válidas `Result` .</span><span class="sxs-lookup"><span data-stu-id="41fda-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="41fda-210">Aparte de eso, las únicas `Result` expresiones son símbolos que se enlazan a `Result` valores o elementos de matriz de `Result` matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="41fda-211">En concreto, tenga en cuenta que `One` no es igual que el entero `1` y no hay ninguna conversión directa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="41fda-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="41fda-212">Lo mismo se cumple para `Zero` y `0` .</span><span class="sxs-lookup"><span data-stu-id="41fda-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="41fda-213">Expresiones de tupla</span><span class="sxs-lookup"><span data-stu-id="41fda-213">Tuple Expressions</span></span>

<span data-ttu-id="41fda-214">Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="41fda-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="41fda-215">Por ejemplo, `(1, One)` es una `(Int, Result)` expresión.</span><span class="sxs-lookup"><span data-stu-id="41fda-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="41fda-216">Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.</span><span class="sxs-lookup"><span data-stu-id="41fda-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="41fda-217">User-Defined expresiones de tipo</span><span class="sxs-lookup"><span data-stu-id="41fda-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="41fda-218">Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="41fda-219">Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)` , `IntPair(2, 3)` es un literal válido de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="41fda-220">Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="41fda-221">Desencapsular expresiones</span><span class="sxs-lookup"><span data-stu-id="41fda-221">Unwrap Expressions</span></span>

<span data-ttu-id="41fda-222">En Q# , el operador Unwrap es un signo de exclamación final `!` .</span><span class="sxs-lookup"><span data-stu-id="41fda-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="41fda-223">Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)` y `s` es una variable con el valor `IntPair(2, 3)` , entonces `s!` es `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="41fda-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="41fda-224">En el caso de los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario, puede repetir el operador Unwrap.</span><span class="sxs-lookup"><span data-stu-id="41fda-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="41fda-225">Por ejemplo, `s!!` indica el valor de doble desencapsulado de `s` .</span><span class="sxs-lookup"><span data-stu-id="41fda-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="41fda-226">Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair` , y `t` es una variable con el valor `WrappedPair(IntPair(1,2))` , entonces `t!!` es `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="41fda-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="41fda-227">El `!` operador tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="41fda-228">`!` y `[]` enlazar positionly; es decir, `a[i]![3]` se lee como `((a[i])!)[3]` : tomar el `i` ésimo elemento de `a` , desencapsularlo y, a continuación, obtener el tercer elemento del valor desencapsulado (que debe ser una matriz).</span><span class="sxs-lookup"><span data-stu-id="41fda-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="41fda-229">La precedencia del `!` operador tiene un impacto que podría no ser obvio.</span><span class="sxs-lookup"><span data-stu-id="41fda-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="41fda-230">Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.</span><span class="sxs-lookup"><span data-stu-id="41fda-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="41fda-231">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="41fda-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="41fda-232">Expresiones de matriz</span><span class="sxs-lookup"><span data-stu-id="41fda-232">Array Expressions</span></span>

<span data-ttu-id="41fda-233">Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, entre corchetes `[]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="41fda-234">Todos los elementos deben ser compatibles con el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="41fda-235">Dadas dos matrices del mismo tipo, utilice el operador binario `+` para formar una nueva matriz que es la concatenación de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="41fda-236">Por ejemplo, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="41fda-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="41fda-237">Creación de matriz</span><span class="sxs-lookup"><span data-stu-id="41fda-237">Array Creation</span></span>

<span data-ttu-id="41fda-238">Dado un tipo y una `Int` expresión, utilice el `new` operador para asignar una nueva matriz del tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="41fda-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="41fda-239">Por ejemplo, `new Int[i + 1]` asigna una nueva `Int` matriz con `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="41fda-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="41fda-240">No se permiten literales de matriz vacíos, como `[]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="41fda-241">En su lugar, puede crear una matriz de longitud cero mediante `new T[0]` , donde `T` es un marcador de posición para un tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="41fda-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="41fda-242">Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="41fda-243">En la mayoría de los casos, se trata de una variación de cero.</span><span class="sxs-lookup"><span data-stu-id="41fda-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="41fda-244">Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.</span><span class="sxs-lookup"><span data-stu-id="41fda-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="41fda-245">Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede usar sin producir un error en tiempo de ejecución, similar a una referencia nula en lenguajes como C# o Java.</span><span class="sxs-lookup"><span data-stu-id="41fda-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="41fda-246">Las matrices que contienen qubits o Invocables se deben inicializar con valores no predeterminados antes de poder usar sus elementos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="41fda-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="41fda-247">Para ver las rutinas de inicialización adecuadas, vea <xref:Microsoft.Quantum.Arrays> .</span><span class="sxs-lookup"><span data-stu-id="41fda-247">For suitable initialization routines, see <xref:Microsoft.Quantum.Arrays>.</span></span>

<span data-ttu-id="41fda-248">Los valores predeterminados para cada tipo son:</span><span class="sxs-lookup"><span data-stu-id="41fda-248">The default values for each type are:</span></span>

<span data-ttu-id="41fda-249">Tipo</span><span class="sxs-lookup"><span data-stu-id="41fda-249">Type</span></span> | <span data-ttu-id="41fda-250">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="41fda-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="41fda-251">_qubit no válido_</span><span class="sxs-lookup"><span data-stu-id="41fda-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="41fda-252">El intervalo vacío, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="41fda-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="41fda-253">_no válido_</span><span class="sxs-lookup"><span data-stu-id="41fda-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="41fda-254">Los tipos de tupla inicializan elemento a elemento.</span><span class="sxs-lookup"><span data-stu-id="41fda-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="41fda-255">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="41fda-255">Array Elements</span></span>

<span data-ttu-id="41fda-256">Dada una expresión de matriz y una `Int` expresión, forme una nueva expresión mediante el operador del elemento de matriz `[]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="41fda-257">La nueva expresión es del mismo tipo que el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="41fda-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="41fda-258">Por ejemplo, si `a` está enlazado a una matriz de tipo `Double` , entonces `a[4]` es una `Double` expresión.</span><span class="sxs-lookup"><span data-stu-id="41fda-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="41fda-259">Si la expresión de matriz no es un identificador simple, debe encerrarla entre paréntesis para seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="41fda-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="41fda-260">Por ejemplo, si `a` y `b` son matrices de tipo `Int` , un elemento de la concatenación se expresa como:</span><span class="sxs-lookup"><span data-stu-id="41fda-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="41fda-261">Todas las matrices de Q# están basadas en cero.</span><span class="sxs-lookup"><span data-stu-id="41fda-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="41fda-262">Es decir, el primer elemento de una matriz `a` siempre es `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="41fda-263">Segmentos de matriz</span><span class="sxs-lookup"><span data-stu-id="41fda-263">Array Slices</span></span>

<span data-ttu-id="41fda-264">Dada una expresión de matriz y una `Range` expresión, forme una expresión nueva mediante el operador de segmento de matriz `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="41fda-265">La nueva expresión es del mismo tipo que la matriz y contiene los elementos de matriz indizados por los elementos de `Range` , en el orden definido por `Range` .</span><span class="sxs-lookup"><span data-stu-id="41fda-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="41fda-266">Por ejemplo, si `a` está enlazado a una matriz de tipo `Double` , entonces `a[3..-1..0]` es una `Double[]` expresión que contiene los cuatro primeros elementos de `a` pero en el orden inverso en el que aparecen en `a` .</span><span class="sxs-lookup"><span data-stu-id="41fda-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="41fda-267">Si `Range` está vacío, el segmento de la matriz resultante tiene una longitud de cero.</span><span class="sxs-lookup"><span data-stu-id="41fda-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="41fda-268">Al igual que con los elementos de la matriz que hacen referencia, si la expresión de matriz no es un identificador simple, debe encerrarla entre paréntesis para segmentarla.</span><span class="sxs-lookup"><span data-stu-id="41fda-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="41fda-269">Por ejemplo, si `a` y `b` son matrices de tipo `Int` , un segmento de la concatenación se expresa como:</span><span class="sxs-lookup"><span data-stu-id="41fda-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="41fda-270">Valores de inicio y fin inferidos</span><span class="sxs-lookup"><span data-stu-id="41fda-270">Inferred start/end values</span></span>

<span data-ttu-id="41fda-271">A partir de la [versión 0,8](xref:microsoft.quantum.relnotes), se admiten expresiones contextuales para la segmentación de intervalos.</span><span class="sxs-lookup"><span data-stu-id="41fda-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="41fda-272">En concreto, puede omitir los valores de inicio y fin de intervalo en el contexto de una expresión de división de intervalo.</span><span class="sxs-lookup"><span data-stu-id="41fda-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="41fda-273">En ese caso, el compilador aplica las siguientes reglas para deducir los delimitadores deseados para el intervalo:</span><span class="sxs-lookup"><span data-stu-id="41fda-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="41fda-274">Si se omite el valor de *Inicio* del intervalo, el valor de inicio deducido</span><span class="sxs-lookup"><span data-stu-id="41fda-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="41fda-275">es cero si no se especifica ningún paso o el paso especificado es positivo.</span><span class="sxs-lookup"><span data-stu-id="41fda-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="41fda-276">es la longitud de la matriz segmentada menos uno si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="41fda-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="41fda-277">Si se omite el valor *final* del intervalo, el valor final deducido</span><span class="sxs-lookup"><span data-stu-id="41fda-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="41fda-278">es la longitud de la matriz segmentada menos uno si no se especifica ningún paso o el paso especificado es positivo.</span><span class="sxs-lookup"><span data-stu-id="41fda-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="41fda-279">es cero si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="41fda-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="41fda-280">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="41fda-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="41fda-281">Expresiones de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="41fda-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="41fda-282">Dado que todos los Q# tipos son tipos de valor (con el qubits que toma un rol en cierto modo especial), se crea formalmente una "copia" cuando un valor se enlaza a un símbolo o cuando se reenlaza un símbolo.</span><span class="sxs-lookup"><span data-stu-id="41fda-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="41fda-283">Es decir, el comportamiento de Q# es el mismo que si se creara una copia mediante un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="41fda-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="41fda-284">Por supuesto, en la práctica, solo se recrean las piezas relevantes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="41fda-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="41fda-285">Esto afecta al modo en que se copian las matrices, ya que no es posible actualizar los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="41fda-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="41fda-286">Para modificar una matriz existente, es necesario aprovechar un mecanismo de *copia y actualización* .</span><span class="sxs-lookup"><span data-stu-id="41fda-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="41fda-287">Puede crear una nueva matriz a partir de una matriz existente a través de expresiones de *copia y actualización* , que utilizan los operadores `w/` y `<-` .</span><span class="sxs-lookup"><span data-stu-id="41fda-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="41fda-288">Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3` , donde</span><span class="sxs-lookup"><span data-stu-id="41fda-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="41fda-289">`expression1` debe ser `T[]` de tipo para algún tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="41fda-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="41fda-290">`expression2` define los índices de la matriz especificada en `expression1` que se van a modificar.</span><span class="sxs-lookup"><span data-stu-id="41fda-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="41fda-291">`expression2` debe ser de tipo `Int` o de tipo `Range` .</span><span class="sxs-lookup"><span data-stu-id="41fda-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="41fda-292">`expression3` es el valor o los valores utilizados para actualizar los elementos de `expression1` , en función de los índices especificados en `expression2` .</span><span class="sxs-lookup"><span data-stu-id="41fda-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="41fda-293">Si `expression2` es `Int` de tipo, `expression3` debe ser de tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="41fda-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="41fda-294">Si `expression2` es `Range` de tipo, `expression3` debe ser de tipo `T[]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="41fda-295">Por ejemplo, la expresión de copiar y actualizar `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en los elementos correspondientes en `arr` , excepto los elementos especificados por `idx` , que se establecen en los valores de `value` .</span><span class="sxs-lookup"><span data-stu-id="41fda-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="41fda-296">Dado `arr` contiene la matriz `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="41fda-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="41fda-297">`arr w/ 0 <- 10` es la matriz `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="41fda-298">`arr w/ 2 <- 10` es la matriz `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="41fda-299">`arr w/ 0..2..3 <- [10,12]` es la matriz `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="41fda-300">Expresiones de copiar y actualizar para elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="41fda-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="41fda-301">Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="41fda-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="41fda-302">Por ejemplo, considere el tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="41fda-303">Si `c` contiene el valor de tipo `Complex(1., -1.)` , `c w/ Re <- 0.` es una expresión de tipo `Complex` que se evalúa como `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="41fda-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="41fda-304">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="41fda-304">Jagged Arrays</span></span>

<span data-ttu-id="41fda-305">Una matriz escalonada, a veces denominada "matriz de matrices", es una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="41fda-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="41fda-306">Los elementos de una matriz escalonada pueden tener distintos tamaños.</span><span class="sxs-lookup"><span data-stu-id="41fda-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="41fda-307">En el ejemplo siguiente se muestra cómo declarar e inicializar una matriz escalonada que representa una tabla de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="41fda-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="41fda-308">Matrices de llamadas</span><span class="sxs-lookup"><span data-stu-id="41fda-308">Arrays of callables</span></span> 

<span data-ttu-id="41fda-309">También puede crear una matriz de llamadas Invocables.</span><span class="sxs-lookup"><span data-stu-id="41fda-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="41fda-310">Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="41fda-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="41fda-311">El tipo de elemento de la matriz admite cualquier [funcón](xref:microsoft.quantum.guide.operationsfunctions) que admitan todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="41fda-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="41fda-312">Por ejemplo, si `Op1` , `Op2` y `Op3` todas son `Qubit[] => Unit` operaciones, pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="41fda-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="41fda-313">`[Op1, Op2]` es una matriz de `(Qubit[] => Unit)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="41fda-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="41fda-314">`[Op1, Op3]` es una matriz de `(Qubit[] => Unit is Adj)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="41fda-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="41fda-315">`[Op2, Op3]` es una matriz de `(Qubit[] => Unit is Ctl)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="41fda-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="41fda-316">Sin embargo, mientras que las operaciones `(Qubit[] => Unit is Adj)` y  `(Qubit[] => Unit is Ctl)` tienen el tipo base común de `(Qubit[] => Unit)` , las *matrices* de estas operaciones no comparten un tipo base común.</span><span class="sxs-lookup"><span data-stu-id="41fda-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="41fda-317">Por ejemplo, `[[Op1], [Op2]]` generaría un error en este momento porque intenta crear una matriz de los dos tipos de matriz incompatibles `(Qubit[] => Unit is Adj)[]` y `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="41fda-318">Para obtener más información sobre las llamadas Invocables, vea [expresiones Invocables](#callable-expressions) en esta página u [ Q# operaciones y funciones en ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="41fda-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="41fda-319">Expresiones condicionales</span><span class="sxs-lookup"><span data-stu-id="41fda-319">Conditional Expressions</span></span>

<span data-ttu-id="41fda-320">Dadas dos expresiones del mismo tipo y una expresión booleana, forman una expresión condicional mediante el signo de interrogación, `?` y la barra vertical `|` .</span><span class="sxs-lookup"><span data-stu-id="41fda-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="41fda-321">Dado `a==b ? c | d` , el valor de la expresión condicional es `c` si `a==b` es true y `d` si es false.</span><span class="sxs-lookup"><span data-stu-id="41fda-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="41fda-322">Expresiones condicionales con llamadas</span><span class="sxs-lookup"><span data-stu-id="41fda-322">Conditional expressions with callables</span></span>

<span data-ttu-id="41fda-323">Las expresiones condicionales se pueden evaluar como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores.</span><span class="sxs-lookup"><span data-stu-id="41fda-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="41fda-324">En este caso, el tipo de la expresión condicional es una operación con entradas y salidas que admiten los inactivos admitidos por ambas expresiones.</span><span class="sxs-lookup"><span data-stu-id="41fda-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="41fda-325">Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[]=>Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="41fda-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="41fda-326">`flag ? Op1 | Op2` es una `(Qubit[] => Unit)` operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="41fda-327">`flag ? Op1 | Op3` es una `(Qubit[] => Unit is Adj)` operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="41fda-328">`flag ? Op2 | Op3` es una `(Qubit[] => Unit is Ctl)` operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="41fda-329">Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tiene lugar si el resultado es el que es el valor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="41fda-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="41fda-330">Por ejemplo, en el caso de que `a==b ? C(qs) | D(qs)` `a==b` sea true, `C` se invoca la operación y, si es false, solo `D` se invoca la operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="41fda-331">Este enfoque es *similar a la cortocircuito* en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="41fda-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="41fda-332">Expresiones Invocables</span><span class="sxs-lookup"><span data-stu-id="41fda-332">Callable Expressions</span></span>

<span data-ttu-id="41fda-333">Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación.</span><span class="sxs-lookup"><span data-stu-id="41fda-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="41fda-334">Por ejemplo, `X` es un literal de operación que hace referencia a la operación de la biblioteca estándar `X` y `Message` es un literal de función que hace referencia a la función de la biblioteca estándar `Message` .</span><span class="sxs-lookup"><span data-stu-id="41fda-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="41fda-335">Si una operación admite el `Adjoint` functor, `Adjoint op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="41fda-336">Del mismo modo, si la operación admite el `Controlled` functor, `Controlled op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="41fda-337">Para obtener más información sobre los tipos de estas expresiones, vea [llamar a las especializaciones](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)de la operación.</span><span class="sxs-lookup"><span data-stu-id="41fda-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="41fda-338">Los funcrs ( `Adjoint` y `Controlled` ) se enlazan más estrechamente que todos los demás operadores, salvo el operador Unwrap `!` y la indización de matriz con `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="41fda-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="41fda-339">Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:</span><span class="sxs-lookup"><span data-stu-id="41fda-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="41fda-340">Expresiones Invocables con parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="41fda-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="41fda-341">Puede usar un literal invocable como un valor, por ejemplo, para asignarlo a una variable o pasarlo a otro que se pueda llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="41fda-342">En este caso, si el que se puede llamar tiene [parámetros de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), debe proporcionar los parámetros como parte del valor al que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="41fda-343">Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="41fda-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="41fda-344">Por ejemplo, si `Fun` es una función con la firma `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="41fda-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="41fda-345">Expresiones de invocación Invocables</span><span class="sxs-lookup"><span data-stu-id="41fda-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="41fda-346">Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma del que se puede llamar, puede formar una *expresión de invocación* anexando la expresión de tupla a la expresión que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="41fda-347">El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="41fda-348">Por ejemplo, si `Op` es una operación con la firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` es una expresión de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="41fda-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="41fda-349">Del mismo modo, si `Sin` es una función con la firma `(Double -> Double)` , `Sin(0.1)` es una expresión de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="41fda-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="41fda-350">Por último, si `Builder` es una función con la firma `(Int -> (Int -> Int))` , `Builder(3)` es una función de `Int` a `Int` .</span><span class="sxs-lookup"><span data-stu-id="41fda-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="41fda-351">La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="41fda-352">Por lo tanto, para invocar el resultado de llamar a `Builder` desde el párrafo anterior, la sintaxis correcta es:</span><span class="sxs-lookup"><span data-stu-id="41fda-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="41fda-353">Al invocar un [parámetro de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) al que se puede llamar, se pueden especificar los parámetros de tipo reales entre corchetes angulares `< >` después de la expresión que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="41fda-354">Normalmente, esta acción no es necesaria, ya que el Q# compilador deduce los tipos reales.</span><span class="sxs-lookup"><span data-stu-id="41fda-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="41fda-355">Sin embargo, *es* necesario para la [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si no se especifica un argumento con parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="41fda-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="41fda-356">También resulta útil cuando se pasan operaciones con un funcr diferente a una que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="41fda-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="41fda-357">Por ejemplo, si `Func` tiene Signature `('T1, 'T2, 'T1) -> 'T2` , `Op1` y `Op2` tiene Signature, `(Qubit[] => Unit is Adj)` y `Op3` tiene Signature `(Qubit[] => Unit)` , para invocar `Func` con `Op1` como primer argumento, `Op2` como el segundo, y `Op3` como el tercero:</span><span class="sxs-lookup"><span data-stu-id="41fda-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="41fda-358">La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.</span><span class="sxs-lookup"><span data-stu-id="41fda-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="41fda-359">Prioridad de los operadores</span><span class="sxs-lookup"><span data-stu-id="41fda-359">Operator Precedence</span></span>

* <span data-ttu-id="41fda-360">Todos los operadores binarios son asociativos a la derecha, excepto `^` .</span><span class="sxs-lookup"><span data-stu-id="41fda-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="41fda-361">Los corchetes, `[ ]` , para la segmentación e indización de matrices, se enlazan antes que cualquier operador.</span><span class="sxs-lookup"><span data-stu-id="41fda-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="41fda-362">Los funcrs `Adjoint` y se `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.</span><span class="sxs-lookup"><span data-stu-id="41fda-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="41fda-363">Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.</span><span class="sxs-lookup"><span data-stu-id="41fda-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="41fda-364">Q# operadores en orden de prioridad, de mayor a menor:</span><span class="sxs-lookup"><span data-stu-id="41fda-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="41fda-365">Operador</span><span class="sxs-lookup"><span data-stu-id="41fda-365">Operator</span></span> | <span data-ttu-id="41fda-366">Polaridad</span><span class="sxs-lookup"><span data-stu-id="41fda-366">Arity</span></span> | <span data-ttu-id="41fda-367">Descripción</span><span class="sxs-lookup"><span data-stu-id="41fda-367">Description</span></span> | <span data-ttu-id="41fda-368">Tipos de operando</span><span class="sxs-lookup"><span data-stu-id="41fda-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="41fda-369">finales `!`</span><span class="sxs-lookup"><span data-stu-id="41fda-369">trailing `!`</span></span> | <span data-ttu-id="41fda-370">Unario</span><span class="sxs-lookup"><span data-stu-id="41fda-370">Unary</span></span> | <span data-ttu-id="41fda-371">Desencapsulado</span><span class="sxs-lookup"><span data-stu-id="41fda-371">Unwrap</span></span> | <span data-ttu-id="41fda-372">Cualquier tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="41fda-372">Any user-defined type</span></span>
 <span data-ttu-id="41fda-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="41fda-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="41fda-374">Unario</span><span class="sxs-lookup"><span data-stu-id="41fda-374">Unary</span></span> | <span data-ttu-id="41fda-375">Negativo numérico, complemento bit a bit, negación lógica</span><span class="sxs-lookup"><span data-stu-id="41fda-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="41fda-376">`Int`, `BigInt` o `Double` para `-` , `Int` o `BigInt` para `~~~` , `Bool` para `not`</span><span class="sxs-lookup"><span data-stu-id="41fda-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="41fda-377">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-377">Binary</span></span> | <span data-ttu-id="41fda-378">Potencia de entero</span><span class="sxs-lookup"><span data-stu-id="41fda-378">Integer power</span></span> | <span data-ttu-id="41fda-379">`Int` o `BigInt` para la base, `Int` para el exponente</span><span class="sxs-lookup"><span data-stu-id="41fda-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="41fda-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="41fda-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="41fda-381">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-381">Binary</span></span> | <span data-ttu-id="41fda-382">División, multiplicación, módulo de entero</span><span class="sxs-lookup"><span data-stu-id="41fda-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="41fda-383">`Int`, `BigInt` o `Double` para `/` y `*` , `Int` o `BigInt` para `%`</span><span class="sxs-lookup"><span data-stu-id="41fda-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="41fda-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="41fda-384">`+`, `-`</span></span> | <span data-ttu-id="41fda-385">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-385">Binary</span></span> | <span data-ttu-id="41fda-386">Suma, concatenación de cadenas y matrices, resta</span><span class="sxs-lookup"><span data-stu-id="41fda-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="41fda-387">`Int`, `BigInt` o `Double` , además, `String` o cualquier tipo de matriz para `+`</span><span class="sxs-lookup"><span data-stu-id="41fda-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="41fda-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="41fda-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="41fda-389">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-389">Binary</span></span> | <span data-ttu-id="41fda-390">Desplazamiento a la izquierda, desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="41fda-390">Left shift, right shift</span></span> | <span data-ttu-id="41fda-391">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="41fda-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="41fda-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="41fda-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="41fda-393">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-393">Binary</span></span> | <span data-ttu-id="41fda-394">Comparaciones menor que, menor o igual que, mayor que, mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="41fda-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="41fda-395">`Int`, `BigInt` o `Double`</span><span class="sxs-lookup"><span data-stu-id="41fda-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="41fda-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="41fda-396">`==`, `!=`</span></span> | <span data-ttu-id="41fda-397">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-397">Binary</span></span> | <span data-ttu-id="41fda-398">comparaciones iguales y no iguales</span><span class="sxs-lookup"><span data-stu-id="41fda-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="41fda-399">cualquier tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="41fda-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="41fda-400">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-400">Binary</span></span> | <span data-ttu-id="41fda-401">AND bit a bit</span><span class="sxs-lookup"><span data-stu-id="41fda-401">Bitwise AND</span></span> | <span data-ttu-id="41fda-402">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="41fda-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="41fda-403">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-403">Binary</span></span> | <span data-ttu-id="41fda-404">XOR bit a bit</span><span class="sxs-lookup"><span data-stu-id="41fda-404">Bitwise XOR</span></span> | <span data-ttu-id="41fda-405">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="41fda-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="41fda-406">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-406">Binary</span></span> | <span data-ttu-id="41fda-407">OR bit a bit</span><span class="sxs-lookup"><span data-stu-id="41fda-407">Bitwise OR</span></span> | <span data-ttu-id="41fda-408">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="41fda-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="41fda-409">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-409">Binary</span></span> | <span data-ttu-id="41fda-410">Y lógico</span><span class="sxs-lookup"><span data-stu-id="41fda-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="41fda-411">Binary</span><span class="sxs-lookup"><span data-stu-id="41fda-411">Binary</span></span> | <span data-ttu-id="41fda-412">O lógico</span><span class="sxs-lookup"><span data-stu-id="41fda-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="41fda-413">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="41fda-413">Binary/Ternary</span></span> | <span data-ttu-id="41fda-414">Range (operador)</span><span class="sxs-lookup"><span data-stu-id="41fda-414">Range operator</span></span> | `Int`
 <span data-ttu-id="41fda-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="41fda-415">`?` `|`</span></span> | <span data-ttu-id="41fda-416">Ternario</span><span class="sxs-lookup"><span data-stu-id="41fda-416">Ternary</span></span> | <span data-ttu-id="41fda-417">Condicional</span><span class="sxs-lookup"><span data-stu-id="41fda-417">Conditional</span></span> | <span data-ttu-id="41fda-418">`Bool` para el lado izquierdo</span><span class="sxs-lookup"><span data-stu-id="41fda-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="41fda-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="41fda-419">`w/` `<-`</span></span> | <span data-ttu-id="41fda-420">Ternario</span><span class="sxs-lookup"><span data-stu-id="41fda-420">Ternary</span></span> | <span data-ttu-id="41fda-421">Copiar y actualizar</span><span class="sxs-lookup"><span data-stu-id="41fda-421">Copy-and-update</span></span> | <span data-ttu-id="41fda-422">Vea [expresiones de copia y actualización](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="41fda-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="41fda-423">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="41fda-423">Next steps</span></span>

<span data-ttu-id="41fda-424">Ahora que puede trabajar con expresiones en Q# , vaya a [operaciones y funciones en Q# ](xref:microsoft.quantum.guide.operationsfunctions) para obtener información sobre cómo definir y llamar a operaciones y funciones.</span><span class="sxs-lookup"><span data-stu-id="41fda-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
