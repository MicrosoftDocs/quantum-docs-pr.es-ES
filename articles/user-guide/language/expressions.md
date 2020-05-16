---
title: 'Expresiones de tipo en Q #'
description: 'Aprenda a especificar, hacer referencia y combinar constantes, variables, operadores, operaciones y funciones como expresiones en Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431213"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="77fdd-103">Expresiones de tipo en Q #</span><span class="sxs-lookup"><span data-stu-id="77fdd-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="77fdd-104">Expresiones numéricas</span><span class="sxs-lookup"><span data-stu-id="77fdd-104">Numeric Expressions</span></span>

<span data-ttu-id="77fdd-105">Las expresiones numéricas son expresiones de tipo `Int` , `BigInt` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="77fdd-106">Es decir, son números enteros o de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="77fdd-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="77fdd-107">`Int`los literales en Q # se escriben simplemente como una secuencia de dígitos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="77fdd-108">Los enteros hexadecimales y binarios se admiten con un `0x` `0b` prefijo y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="77fdd-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="77fdd-109">`BigInt`los literales en Q # se escriben con un `l` sufijo o final `L` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="77fdd-110">Los enteros Big hexadecimales se admiten con un prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="77fdd-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="77fdd-111">Por lo tanto, los siguientes son usos válidos de los `BigInt` literales:</span><span class="sxs-lookup"><span data-stu-id="77fdd-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="77fdd-112">`Double`los literales de Q # son números de punto flotante escritos con dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="77fdd-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="77fdd-113">Se pueden escribir con un separador decimal, `.` y/o una parte exponencial indicada con ' e ' o ' e ' (después de los cuales solo hay un posible signo negativo y dígitos decimales válidos).</span><span class="sxs-lookup"><span data-stu-id="77fdd-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="77fdd-114">Los siguientes son `Double` literales válidos: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="77fdd-115">Dada una expresión de matriz de cualquier tipo de elemento, una `Int` expresión se puede formar utilizando la [`Length`](xref:microsoft.quantum.core.length) función integrada, con la expresión de matriz entre paréntesis, `(` y `)` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="77fdd-116">Por ejemplo, si `a` está enlazado a una matriz, `Length(a)` es una expresión de entero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="77fdd-117">Si `b` es una matriz de matrices de enteros, `Int[][]` , entonces `Length(b)` es el número de submatrices de y `b` `Length(b[1])` es el número de enteros de la segunda submatriz de `b` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="77fdd-118">Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+` ,, `-` `*` y `/` se pueden usar para formar una nueva expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="77fdd-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="77fdd-119">El tipo de la nueva expresión será el mismo que los tipos de las expresiones constituyentes.</span><span class="sxs-lookup"><span data-stu-id="77fdd-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="77fdd-120">Dadas dos expresiones de tipo entero, el operador binario `^` (Power) se puede usar para formar una nueva expresión de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="77fdd-121">De forma similar, `^` se puede usar con dos expresiones Double para formar una nueva expresión Double.</span><span class="sxs-lookup"><span data-stu-id="77fdd-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="77fdd-122">Por último, `^` se puede usar con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.</span><span class="sxs-lookup"><span data-stu-id="77fdd-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="77fdd-123">En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77fdd-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="77fdd-124">Dadas dos expresiones integer o Big Integer, se puede formar una nueva expresión de tipo entero o Big Integer mediante los `%` operadores (modulus), `&&&` (AND bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).</span><span class="sxs-lookup"><span data-stu-id="77fdd-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="77fdd-125">Dado un entero o una expresión Big Integer a la izquierda, y una expresión de entero a la derecha, `<<<` se pueden usar los operadores (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que la expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="77fdd-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="77fdd-126">El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.</span><span class="sxs-lookup"><span data-stu-id="77fdd-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="77fdd-127">La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77fdd-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="77fdd-128">Si el número que se va a desplazar es un entero, se interpreta la cantidad de desplazamiento, es `mod 64` decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="77fdd-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="77fdd-129">En el caso de los valores entero y Big Integer, ShiftS es aritmético.</span><span class="sxs-lookup"><span data-stu-id="77fdd-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="77fdd-130">Si se desplaza un valor negativo a la izquierda o a la derecha, se producirá un número negativo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="77fdd-131">Es decir, el desplazamiento de un paso a la izquierda o a la derecha es exactamente el mismo que si se multiplica o se divide por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="77fdd-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="77fdd-132">La división de enteros y los módulos de enteros siguen el mismo comportamiento para los números negativos que en C#.</span><span class="sxs-lookup"><span data-stu-id="77fdd-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="77fdd-133">Es decir, `a % b` siempre tendrá el mismo signo que `a` y `b * (a / b) + a % b` siempre será igual que `a` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="77fdd-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="77fdd-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="77fdd-135">5</span><span class="sxs-lookup"><span data-stu-id="77fdd-135">5</span></span> | <span data-ttu-id="77fdd-136">2</span><span class="sxs-lookup"><span data-stu-id="77fdd-136">2</span></span> | <span data-ttu-id="77fdd-137">2</span><span class="sxs-lookup"><span data-stu-id="77fdd-137">2</span></span> | <span data-ttu-id="77fdd-138">1</span><span class="sxs-lookup"><span data-stu-id="77fdd-138">1</span></span>
 <span data-ttu-id="77fdd-139">5</span><span class="sxs-lookup"><span data-stu-id="77fdd-139">5</span></span> | <span data-ttu-id="77fdd-140">-2</span><span class="sxs-lookup"><span data-stu-id="77fdd-140">-2</span></span> | <span data-ttu-id="77fdd-141">-2</span><span class="sxs-lookup"><span data-stu-id="77fdd-141">-2</span></span> | <span data-ttu-id="77fdd-142">1</span><span class="sxs-lookup"><span data-stu-id="77fdd-142">1</span></span>
 <span data-ttu-id="77fdd-143">-5</span><span class="sxs-lookup"><span data-stu-id="77fdd-143">-5</span></span> | <span data-ttu-id="77fdd-144">2</span><span class="sxs-lookup"><span data-stu-id="77fdd-144">2</span></span> | <span data-ttu-id="77fdd-145">-2</span><span class="sxs-lookup"><span data-stu-id="77fdd-145">-2</span></span> | <span data-ttu-id="77fdd-146">-1</span><span class="sxs-lookup"><span data-stu-id="77fdd-146">-1</span></span>
 <span data-ttu-id="77fdd-147">-5</span><span class="sxs-lookup"><span data-stu-id="77fdd-147">-5</span></span> | <span data-ttu-id="77fdd-148">-2</span><span class="sxs-lookup"><span data-stu-id="77fdd-148">-2</span></span> | <span data-ttu-id="77fdd-149">2</span><span class="sxs-lookup"><span data-stu-id="77fdd-149">2</span></span> | <span data-ttu-id="77fdd-150">-1</span><span class="sxs-lookup"><span data-stu-id="77fdd-150">-1</span></span>

<span data-ttu-id="77fdd-151">La división y el módulo Big Integer funcionan de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="77fdd-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="77fdd-152">Dada cualquier expresión numérica, se puede formar una nueva expresión mediante el `-` operador unario.</span><span class="sxs-lookup"><span data-stu-id="77fdd-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="77fdd-153">La nueva expresión será del mismo tipo que la expresión constituyente.</span><span class="sxs-lookup"><span data-stu-id="77fdd-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="77fdd-154">Dado cualquier expresión integer o Big Integer, se puede formar una nueva expresión del mismo tipo mediante el `~~~` operador unario (complemento bit a bit).</span><span class="sxs-lookup"><span data-stu-id="77fdd-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="77fdd-155">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="77fdd-155">Boolean Expressions</span></span>

<span data-ttu-id="77fdd-156">Los dos `Bool` valores literales son `true` y `false` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="77fdd-157">Dadas dos expresiones cualesquiera del mismo tipo primitivo, `==` `!=` se pueden usar los operadores binarios y para construir una `Bool` expresión.</span><span class="sxs-lookup"><span data-stu-id="77fdd-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="77fdd-158">La expresión será true si las dos expresiones son iguales y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="77fdd-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="77fdd-159">No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar los valores desencapsulados.</span><span class="sxs-lookup"><span data-stu-id="77fdd-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="77fdd-160">Por ejemplo, mediante el operador "Unwrap" `!` (que se explica en detalle en [tipos en Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="77fdd-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="77fdd-161">La comparación de igualdad para `Qubit` los valores es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.</span><span class="sxs-lookup"><span data-stu-id="77fdd-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="77fdd-162">Esta comparación no compara, tiene acceso, mide o modifica el estado de los dos qubits.</span><span class="sxs-lookup"><span data-stu-id="77fdd-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="77fdd-163">La comparación de igualdad de `Double` los valores puede ser engañosa debido a efectos de redondeo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="77fdd-164">Por ejemplo, `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="77fdd-165">Dadas dos expresiones numéricas, los operadores binarios `>` ,, `<` `>=` y `<=` se pueden usar para crear una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que, o menor o igual que la segunda expresión.</span><span class="sxs-lookup"><span data-stu-id="77fdd-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="77fdd-166">Dadas dos expresiones booleanas, se `and` `or` pueden usar los operadores binarios y para construir una nueva expresión booleana que es true si las dos expresiones son verdaderas (o ambas).</span><span class="sxs-lookup"><span data-stu-id="77fdd-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="77fdd-167">Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.</span><span class="sxs-lookup"><span data-stu-id="77fdd-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="77fdd-168">Expresiones de cadena</span><span class="sxs-lookup"><span data-stu-id="77fdd-168">String Expressions</span></span>

<span data-ttu-id="77fdd-169">Q # permite usar cadenas en la `fail` instrucción (explicadas en el [flujo de control](xref:microsoft.quantum.guide.controlflow#fail-statement)) y en la [`Message`](xref:microsoft.quantum.intrinsic.message) función estándar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="77fdd-170">El comportamiento específico de este último depende del simulador utilizado, pero normalmente escribe un mensaje en la consola del host cuando se llama durante un programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="77fdd-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="77fdd-171">Las cadenas en Q # son literales o cadenas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="77fdd-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="77fdd-172">Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles, `"` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="77fdd-173">Dentro de una cadena, el carácter de barra diagonal inversa `\` se puede usar para escapar un carácter de comillas dobles e insertar una nueva línea como `\n` , un retorno de carro como `\r` y una tabulación como `\t` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="77fdd-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="77fdd-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="77fdd-175">Cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="77fdd-175">Interpolated strings</span></span>

<span data-ttu-id="77fdd-176">La sintaxis de Q # para las interpolaciones de cadenas es un subconjunto de la sintaxis de C#, pero se resumen aquí los puntos clave tal y como se relacionan con preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="77fdd-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="77fdd-177">A continuación se describen las distinciones principales.</span><span class="sxs-lookup"><span data-stu-id="77fdd-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="77fdd-178">Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="77fdd-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="77fdd-179">No puede haber ningún espacio en blanco entre `$` y `"` que inicia un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="77fdd-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="77fdd-180">El siguiente es un ejemplo básico que usa la [`Message`](xref:microsoft.quantum.intrinsic.message) función para escribir el resultado de una medida en la consola, junto con otras expresiones de Q #.</span><span class="sxs-lookup"><span data-stu-id="77fdd-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="77fdd-181">Cualquier expresión Q # válida puede aparecer en una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="77fdd-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="77fdd-182">Puede encontrar más información sobre la sintaxis de C# en [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="77fdd-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="77fdd-183">La diferencia más notable es que Q # no admite cadenas interpoladas textuales (multilínea).</span><span class="sxs-lookup"><span data-stu-id="77fdd-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="77fdd-184">Las expresiones incluidas en una cadena interpolada siguen la sintaxis de Q #, no la sintaxis de C#.</span><span class="sxs-lookup"><span data-stu-id="77fdd-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="77fdd-185">Expresiones de rango</span><span class="sxs-lookup"><span data-stu-id="77fdd-185">Range Expressions</span></span>

<span data-ttu-id="77fdd-186">Dadas las tres `Int` expresiones `start` , y, `step` `stop` `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start` , el segundo elemento es, el `start+step` tercer elemento es `start+step+step` , etc., hasta que `stop` se pasa.</span><span class="sxs-lookup"><span data-stu-id="77fdd-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="77fdd-187">Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="77fdd-188">El último elemento del intervalo será `stop` si la diferencia entre `start` y `stop` es un múltiplo entero de; es `step` decir, el intervalo es inclusivo en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="77fdd-189">Dadas dos `Int` expresiones cualesquiera `start` y `stop` , `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="77fdd-190">Observe que el implícito `step` es + 1 incluso si `stop` es menor que `start` ; en tal caso, el intervalo está vacío.</span><span class="sxs-lookup"><span data-stu-id="77fdd-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="77fdd-191">Algunos intervalos de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="77fdd-191">Some example ranges are:</span></span>

- <span data-ttu-id="77fdd-192">`1..3`es el intervalo de 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="77fdd-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="77fdd-193">`2..2..5`es el intervalo de 2 a 4.</span><span class="sxs-lookup"><span data-stu-id="77fdd-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="77fdd-194">`2..2..6`es el intervalo de 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="77fdd-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="77fdd-195">`6..-2..2`es el rango 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="77fdd-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="77fdd-196">`2..1`es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="77fdd-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="77fdd-197">`2..6..7`es el intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="77fdd-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="77fdd-198">`2..2..1`es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="77fdd-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="77fdd-199">`1..-1..2`es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="77fdd-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="77fdd-200">Expresiones qubit</span><span class="sxs-lookup"><span data-stu-id="77fdd-200">Qubit Expressions</span></span>

<span data-ttu-id="77fdd-201">Las únicas `Qubit` expresiones son símbolos que se enlazan a `Qubit` valores o elementos de matriz de `Qubit` matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="77fdd-202">No hay `Qubit` literales.</span><span class="sxs-lookup"><span data-stu-id="77fdd-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="77fdd-203">Expresiones Pauli</span><span class="sxs-lookup"><span data-stu-id="77fdd-203">Pauli Expressions</span></span>

<span data-ttu-id="77fdd-204">Los cuatro `Pauli` valores,,, `PauliI` `PauliX` `PauliY` y `PauliZ` , son expresiones válidas `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="77fdd-205">Aparte de eso, las únicas `Pauli` expresiones son símbolos que se enlazan a `Pauli` valores o elementos de matriz de `Pauli` matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="77fdd-206">Expresiones de resultado</span><span class="sxs-lookup"><span data-stu-id="77fdd-206">Result Expressions</span></span>

<span data-ttu-id="77fdd-207">Los dos `Result` valores, `One` y `Zero` , son expresiones válidas `Result` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="77fdd-208">Aparte de eso, las únicas `Result` expresiones son símbolos que se enlazan a `Result` valores o elementos de matriz de `Result` matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="77fdd-209">En concreto, tenga en cuenta que `One` no es igual que el entero `1` y no hay ninguna conversión directa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="77fdd-210">Lo mismo se cumple para `Zero` y `0` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="77fdd-211">Expresiones de tupla</span><span class="sxs-lookup"><span data-stu-id="77fdd-211">Tuple Expressions</span></span>

<span data-ttu-id="77fdd-212">Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, entre `(` y `)` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="77fdd-213">Por ejemplo, `(1, One)` es una `(Int, Result)` expresión.</span><span class="sxs-lookup"><span data-stu-id="77fdd-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="77fdd-214">Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.</span><span class="sxs-lookup"><span data-stu-id="77fdd-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="77fdd-215">Expresiones de tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="77fdd-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="77fdd-216">Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="77fdd-217">Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)` , `IntPair(2, 3)` sería un literal válido de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="77fdd-218">Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="77fdd-219">Desencapsular expresiones</span><span class="sxs-lookup"><span data-stu-id="77fdd-219">Unwrap Expressions</span></span>

<span data-ttu-id="77fdd-220">En Q #, el operador Unwrap es un signo de exclamación final `!` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="77fdd-221">Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)` y `s` era una variable con el valor `IntPair(2, 3)` , `s!` sería `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="77fdd-222">Para los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="77fdd-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="77fdd-223">el operador Unwrap puede repetirse; por ejemplo, `s!!` indica el valor de doble desencapsulado de `s` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="77fdd-224">Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair` , y `t` es una variable con el valor `WrappedPair(IntPair(1,2))` , entonces `t!!` sería `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="77fdd-225">El `!` operador tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="77fdd-226">`!`y `[]` enlazar positionly; es decir, `a[i]![3]` se debe leer como `((a[i])!)[3]` : tomar el `i` elemento ' th de `a` , desencapsularlo y, a continuación, obtener el tercer elemento del valor desencapsulado (que debe ser una matriz).</span><span class="sxs-lookup"><span data-stu-id="77fdd-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="77fdd-227">La precedencia del `!` operador tiene un impacto que podría no ser obvio.</span><span class="sxs-lookup"><span data-stu-id="77fdd-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="77fdd-228">Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="77fdd-229">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="77fdd-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="77fdd-230">Expresiones de matriz</span><span class="sxs-lookup"><span data-stu-id="77fdd-230">Array Expressions</span></span>

<span data-ttu-id="77fdd-231">Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, entre `[` y `]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="77fdd-232">Todos los elementos deben ser compatibles con el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-232">All elements must be compatible with the same type.</span></span>


<span data-ttu-id="77fdd-233">Dadas dos matrices del mismo tipo, `+` se puede utilizar el operador binario para formar una nueva matriz que es la concatenación de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="77fdd-234">Por ejemplo, `[1,2,3] + [4,5,6]` es `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="77fdd-235">Creación de matriz</span><span class="sxs-lookup"><span data-stu-id="77fdd-235">Array Creation</span></span>

<span data-ttu-id="77fdd-236">Dado un tipo y una `Int` expresión, el `new` operador se puede utilizar para asignar una nueva matriz del tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="77fdd-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="77fdd-237">Por ejemplo, `new Int[i + 1]` asignaría una nueva `Int` matriz con `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="77fdd-238">Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-238">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="77fdd-239">En la mayoría de los casos, se trata de una variación de cero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-239">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="77fdd-240">Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.</span><span class="sxs-lookup"><span data-stu-id="77fdd-240">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="77fdd-241">Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede utilizar sin que se produzca un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77fdd-241">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="77fdd-242">Esto es similar a una referencia nula en lenguajes como C# o Java.</span><span class="sxs-lookup"><span data-stu-id="77fdd-242">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="77fdd-243">Las matrices que contienen qubits o llamadas se deben inicializar correctamente con valores no predeterminados antes de que sus elementos se puedan usar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="77fdd-243">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="77fdd-244">Se pueden encontrar rutinas de inicialización adecuadas en <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="77fdd-244">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="77fdd-245">Los valores predeterminados para cada tipo son:</span><span class="sxs-lookup"><span data-stu-id="77fdd-245">The default values for each type are:</span></span>

<span data-ttu-id="77fdd-246">Tipo</span><span class="sxs-lookup"><span data-stu-id="77fdd-246">Type</span></span> | <span data-ttu-id="77fdd-247">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77fdd-247">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="77fdd-248">_qubit no válido_</span><span class="sxs-lookup"><span data-stu-id="77fdd-248">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="77fdd-249">El intervalo vacío,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="77fdd-249">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="77fdd-250">_no válido_</span><span class="sxs-lookup"><span data-stu-id="77fdd-250">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="77fdd-251">Los tipos de tupla se inicializan elemento a elemento.</span><span class="sxs-lookup"><span data-stu-id="77fdd-251">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="77fdd-252">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="77fdd-252">Array Elements</span></span>

<span data-ttu-id="77fdd-253">Dada una expresión de matriz y una `Int` expresión, se puede formar una nueva expresión mediante `[` el `]` operador de elemento de matriz y.</span><span class="sxs-lookup"><span data-stu-id="77fdd-253">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="77fdd-254">La nueva expresión será del mismo tipo que el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="77fdd-254">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="77fdd-255">Por ejemplo, si `a` está enlazado a una matriz de `Double` s, `a[4]` es una `Double` expresión.</span><span class="sxs-lookup"><span data-stu-id="77fdd-255">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="77fdd-256">Si la expresión de matriz no es un identificador simple, se debe incluir entre paréntesis para poder seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="77fdd-256">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="77fdd-257">Por ejemplo, si `a` y `b` son matrices de `Int` s, un elemento de la concatenación se expresaría como:</span><span class="sxs-lookup"><span data-stu-id="77fdd-257">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="77fdd-258">Todas las matrices en Q # son de base cero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-258">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="77fdd-259">Es decir, el primer elemento de una matriz `a` siempre es `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-259">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="77fdd-260">Segmentos de matriz</span><span class="sxs-lookup"><span data-stu-id="77fdd-260">Array Slices</span></span>

<span data-ttu-id="77fdd-261">Dada una expresión de matriz y una `Range` expresión, se puede formar una nueva expresión mediante `[` el `]` operador de segmento de matriz y.</span><span class="sxs-lookup"><span data-stu-id="77fdd-261">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="77fdd-262">La nueva expresión será del mismo tipo que la matriz y contendrá los elementos de matriz indizados por los elementos de `Range` , en el orden definido por `Range` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-262">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="77fdd-263">Por ejemplo, si `a` está enlazado a una matriz de `Double` s, `a[3..-1..0]` es una `Double[]` expresión que contiene los cuatro primeros elementos de, `a` pero en el orden inverso en el que aparecen en `a` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-263">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="77fdd-264">Si `Range` está vacío, el segmento de la matriz resultante tendrá una longitud de cero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-264">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="77fdd-265">Al igual que con los elementos de la matriz que hacen referencia, si la expresión de matriz no es un identificador simple, se debe incluir entre paréntesis para segmentar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-265">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="77fdd-266">Si `a` y `b` son matrices de `Int` s, un segmento de la concatenación se expresaría como:</span><span class="sxs-lookup"><span data-stu-id="77fdd-266">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="77fdd-267">Valores de inicio y fin inferidos</span><span class="sxs-lookup"><span data-stu-id="77fdd-267">Inferred start/end values</span></span>

<span data-ttu-id="77fdd-268">A partir de la versión 0,8, se admiten expresiones contextuales para la segmentación de intervalos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-268">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="77fdd-269">En concreto, los valores de inicio y fin de intervalo se pueden omitir en el contexto de una expresión de división de intervalo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-269">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="77fdd-270">En ese caso, el compilador aplicará las siguientes reglas para deducir los delimitadores deseados para el intervalo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-270">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="77fdd-271">Por ejemplo, si se omite el valor de inicio de intervalo, el valor de inicio deducido</span><span class="sxs-lookup"><span data-stu-id="77fdd-271">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="77fdd-272">es cero si no se especifica ningún paso o el paso especificado es positivo, y</span><span class="sxs-lookup"><span data-stu-id="77fdd-272">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="77fdd-273">es la longitud de la matriz segmentada menos uno si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-273">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="77fdd-274">Si se omite el valor final del intervalo, el valor final deducido</span><span class="sxs-lookup"><span data-stu-id="77fdd-274">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="77fdd-275">es la longitud de la matriz segmentada menos uno si no se especifica ningún paso o el paso especificado es positivo, y</span><span class="sxs-lookup"><span data-stu-id="77fdd-275">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="77fdd-276">es cero si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-276">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="77fdd-277">Expresiones de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="77fdd-277">Copy-and-Update Expressions</span></span>

<span data-ttu-id="77fdd-278">Dado que todos los tipos de Q # son tipos de valor, con el qubits que toma un rol especialmente especial, se crea formalmente una "copia" cuando se enlaza un valor a un símbolo o cuando se reenlaza un símbolo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-278">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="77fdd-279">Es decir, el comportamiento de Q # es el mismo que si se creara una copia en la asignación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-279">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="77fdd-280">Por supuesto, en la práctica solo se recrean las piezas relevantes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="77fdd-280">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="77fdd-281">Esto, en concreto, también incluye matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-281">This in particular also includes arrays.</span></span>
<span data-ttu-id="77fdd-282">En concreto, no es posible actualizar los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="77fdd-282">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="77fdd-283">Para modificar una matriz existente, es necesario aprovechar un mecanismo de *copia y actualización* .</span><span class="sxs-lookup"><span data-stu-id="77fdd-283">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="77fdd-284">Las nuevas matrices se pueden crear a partir de las existentes a través de expresiones de *copia y actualización* .</span><span class="sxs-lookup"><span data-stu-id="77fdd-284">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="77fdd-285">Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3` , donde debe `expression1` ser de tipo `T[]` para algún tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-285">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="77fdd-286">La segunda `expression2` define los índices de los elementos que se van a modificar en comparación con la matriz de `expression1` y debe ser de tipo `Int` o de tipo `Range` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-286">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="77fdd-287">Si `expression2` es de tipo `Int` , debe `expression3` ser de tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-287">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="77fdd-288">Si `expression2` es de tipo `Range` , debe `expression3` ser de tipo `T[]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-288">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="77fdd-289">Una expresión de copia y actualización `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en el elemento correspondiente de `arr` , excepto los elementos de `idx` , que se establecen en los elementos de, que están establecidos en `value` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-289">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="77fdd-290">Por ejemplo, si `arr` contiene una matriz `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="77fdd-290">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="77fdd-291">`arr w/ 0 <- 10`es la matriz `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-291">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="77fdd-292">`arr w/ 2 <- 10`es la matriz `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-292">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="77fdd-293">`arr w/ 0..2..3 <- [10,12]`es la matriz `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-293">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="77fdd-294">Expresiones de copiar y actualizar para elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="77fdd-294">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="77fdd-295">Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="77fdd-295">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="77fdd-296">Considere, por ejemplo, el tipo</span><span class="sxs-lookup"><span data-stu-id="77fdd-296">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="77fdd-297">Si `c` contiene el valor de tipo `Complex(1., -1.)` , `c w/ Re <- 0.` es una expresión de tipo `Complex` que se evalúa como `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-297">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="77fdd-298">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="77fdd-298">Jagged Arrays</span></span>

<span data-ttu-id="77fdd-299">Una matriz escalonada, a veces denominada "matriz de matrices", es una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="77fdd-299">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="77fdd-300">Los elementos de una matriz escalonada pueden tener distintos tamaños.</span><span class="sxs-lookup"><span data-stu-id="77fdd-300">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="77fdd-301">En el ejemplo siguiente se muestra cómo declarar e inicializar una matriz escalonada que representa una tabla de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-301">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="77fdd-302">Matrices de llamadas</span><span class="sxs-lookup"><span data-stu-id="77fdd-302">Arrays of callables</span></span> 

<span data-ttu-id="77fdd-303">Tenga en cuenta que se pueden encontrar más detalles sobre los tipos a los que se puede llamar, así como en la página siguiente, [operaciones y funciones en Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="77fdd-303">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="77fdd-304">Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="77fdd-304">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="77fdd-305">El tipo de elemento de la matriz será compatible con cualquier functor que admitan todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="77fdd-305">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="77fdd-306">Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[] => Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="77fdd-306">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="77fdd-307">`[Op1, Op2]`es una matriz de `(Qubit[] => Unit)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="77fdd-307">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="77fdd-308">`[Op1, Op3]`es una matriz de `(Qubit[] => Unit is Adj)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="77fdd-308">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="77fdd-309">`[Op2, Op3]`es una matriz de `(Qubit[] => Unit is Ctl)` operaciones.</span><span class="sxs-lookup"><span data-stu-id="77fdd-309">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="77fdd-310">No se permiten literales de matriz vacíos, `[]` ,.</span><span class="sxs-lookup"><span data-stu-id="77fdd-310">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="77fdd-311">En lugar `new ★[0]` de usar, donde `★` es un marcador de posición para un tipo adecuado, permite crear la matriz deseada de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="77fdd-311">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="77fdd-312">Expresiones condicionales</span><span class="sxs-lookup"><span data-stu-id="77fdd-312">Conditional Expressions</span></span>

<span data-ttu-id="77fdd-313">Dadas otras dos expresiones del mismo tipo y una expresión booleana, la expresión condicional se puede formar mediante el signo de interrogación `?` y la barra vertical `|` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-313">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="77fdd-314">Por ejemplo, `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-314">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="77fdd-315">En este ejemplo, el valor de la expresión condicional será `c` si `a==b` es true y `d` si es false.</span><span class="sxs-lookup"><span data-stu-id="77fdd-315">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="77fdd-316">Expresiones condicionales con llamadas</span><span class="sxs-lookup"><span data-stu-id="77fdd-316">Conditional expressions with callables</span></span>

<span data-ttu-id="77fdd-317">Las dos expresiones pueden evaluarse como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores.</span><span class="sxs-lookup"><span data-stu-id="77fdd-317">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="77fdd-318">En este caso, el tipo de la expresión condicional es una operación con esas entradas y salidas que admite cualquier functor compatible con ambas expresiones.</span><span class="sxs-lookup"><span data-stu-id="77fdd-318">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="77fdd-319">Por ejemplo, si `Op1` , `Op2` y `Op3` todos son `Qubit[]=>Unit` , pero `Op1` admite, `Adjoint` `Op2` `Controlled` y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="77fdd-319">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="77fdd-320">`flag ? Op1 | Op2`es una `(Qubit[] => Unit)` operación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-320">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="77fdd-321">`flag ? Op1 | Op3`es una `(Qubit[] => Unit is Adj)` operación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-321">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="77fdd-322">`flag ? Op2 | Op3`es una `(Qubit[] => Unit is Ctl)` operación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-322">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="77fdd-323">Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tendrá lugar si ese resultado es el que será el valor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="77fdd-323">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="77fdd-324">Por ejemplo, en caso de que `a==b ? C(qs) | D(qs)` `a==b` sea true, se `C` invocará la operación y, si es false, solo se `D` invocará.</span><span class="sxs-lookup"><span data-stu-id="77fdd-324">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="77fdd-325">Esto es similar a la cortocircuito en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="77fdd-325">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="77fdd-326">Expresiones Invocables</span><span class="sxs-lookup"><span data-stu-id="77fdd-326">Callable Expressions</span></span>

<span data-ttu-id="77fdd-327">Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-327">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="77fdd-328">Por ejemplo, `X` es un literal de operación que hace referencia a la operación de la biblioteca estándar `X` y `Message` es un literal de función que hace referencia a la función de la biblioteca estándar `Message` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-328">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="77fdd-329">Si una operación admite el `Adjoint` functor, `Adjoint op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-329">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="77fdd-330">Del mismo modo, si la operación admite el `Controlled` functor, `Controlled op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-330">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="77fdd-331">Los tipos de estas expresiones se especifican en las [especializaciones](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)de la operación de llamada.</span><span class="sxs-lookup"><span data-stu-id="77fdd-331">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="77fdd-332">Los funcrs ( `Adjoint` y `Controlled` ) se enlazan más estrechamente que todos los demás operadores, salvo el operador Unwrap `!` y la indización de matriz con [] '.</span><span class="sxs-lookup"><span data-stu-id="77fdd-332">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="77fdd-333">Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:</span><span class="sxs-lookup"><span data-stu-id="77fdd-333">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="77fdd-334">Expresiones Invocables con parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="77fdd-334">Type-parameterized callable expressions</span></span>

<span data-ttu-id="77fdd-335">Un literal al que se puede llamar se puede usar como un valor, por ejemplo, para asignar a una variable o para pasar a otra que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-335">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="77fdd-336">En este caso, si el que se puede llamar tiene [parámetros de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), deben proporcionarse como parte del valor al que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-336">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="77fdd-337">Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="77fdd-337">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="77fdd-338">Por ejemplo, si `Fun` es una función con firma `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="77fdd-338">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="77fdd-339">Expresiones de invocación Invocables</span><span class="sxs-lookup"><span data-stu-id="77fdd-339">Callable Invocation Expressions</span></span>

<span data-ttu-id="77fdd-340">Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma de la que se puede llamar, se puede formar una expresión de invocación anexando la expresión de tupla a la expresión a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-340">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="77fdd-341">El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-341">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="77fdd-342">Por ejemplo, si `Op` es una operación con firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` es una expresión de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-342">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="77fdd-343">Del mismo modo, si `Sin` es una función con firma `(Double -> Double)` , `Sin(0.1)` es una expresión de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-343">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="77fdd-344">Por último, si `Builder` es una función con firma `(Int -> (Int -> Int))` , `Builder(3)` es una función de into a int.</span><span class="sxs-lookup"><span data-stu-id="77fdd-344">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="77fdd-345">La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-345">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="77fdd-346">Por lo tanto, para invocar el resultado de llamar a `Builder` desde el párrafo anterior, la sintaxis correcta es:</span><span class="sxs-lookup"><span data-stu-id="77fdd-346">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="77fdd-347">Al invocar un [parámetro de tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) invocable, los parámetros de tipo reales se pueden especificar entre corchetes angulares `<` y `>` después de la expresión que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="77fdd-347">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="77fdd-348">Normalmente esto no es necesario, ya que el compilador de preguntas y respuestas inferirá los tipos reales.</span><span class="sxs-lookup"><span data-stu-id="77fdd-348">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="77fdd-349">Sin embargo, *es* necesario para la [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si no se especifica un argumento con parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="77fdd-349">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="77fdd-350">También es útil a veces cuando se pasan operaciones con un functor diferente para llamar a.</span><span class="sxs-lookup"><span data-stu-id="77fdd-350">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="77fdd-351">Por ejemplo, si `Func` tiene Signature `('T1, 'T2, 'T1) -> 'T2` , `Op1` y `Op2` tiene Signature, `(Qubit[] => Unit is Adj)` y `Op3` tiene Signature `(Qubit[] => Unit)` , para invocar `Func` con `Op1` como primer argumento, `Op2` como el segundo y `Op3` como el tercero:</span><span class="sxs-lookup"><span data-stu-id="77fdd-351">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="77fdd-352">La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.</span><span class="sxs-lookup"><span data-stu-id="77fdd-352">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="77fdd-353">Prioridad de los operadores</span><span class="sxs-lookup"><span data-stu-id="77fdd-353">Operator Precedence</span></span>

<span data-ttu-id="77fdd-354">Todos los operadores binarios son asociativos a la derecha, excepto `^` .</span><span class="sxs-lookup"><span data-stu-id="77fdd-354">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="77fdd-355">Los corchetes y `[` `]` , para la segmentación e indización de matrices, se enlazan antes que cualquier operador.</span><span class="sxs-lookup"><span data-stu-id="77fdd-355">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="77fdd-356">Los funcrs `Adjoint` y se `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.</span><span class="sxs-lookup"><span data-stu-id="77fdd-356">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="77fdd-357">Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.</span><span class="sxs-lookup"><span data-stu-id="77fdd-357">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="77fdd-358">Operadores en orden de prioridad, de mayor a menor:</span><span class="sxs-lookup"><span data-stu-id="77fdd-358">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="77fdd-359">Operador</span><span class="sxs-lookup"><span data-stu-id="77fdd-359">Operator</span></span> | <span data-ttu-id="77fdd-360">Polaridad</span><span class="sxs-lookup"><span data-stu-id="77fdd-360">Arity</span></span> | <span data-ttu-id="77fdd-361">Descripción</span><span class="sxs-lookup"><span data-stu-id="77fdd-361">Description</span></span> | <span data-ttu-id="77fdd-362">Tipos de operando</span><span class="sxs-lookup"><span data-stu-id="77fdd-362">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="77fdd-363">finales`!`</span><span class="sxs-lookup"><span data-stu-id="77fdd-363">trailing `!`</span></span> | <span data-ttu-id="77fdd-364">Unario</span><span class="sxs-lookup"><span data-stu-id="77fdd-364">Unary</span></span> | <span data-ttu-id="77fdd-365">Desencapsulado</span><span class="sxs-lookup"><span data-stu-id="77fdd-365">Unwrap</span></span> | <span data-ttu-id="77fdd-366">Cualquier tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="77fdd-366">Any user-defined type</span></span>
 <span data-ttu-id="77fdd-367">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="77fdd-367">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="77fdd-368">Unario</span><span class="sxs-lookup"><span data-stu-id="77fdd-368">Unary</span></span> | <span data-ttu-id="77fdd-369">Negativo numérico, complemento bit a bit, negación lógica</span><span class="sxs-lookup"><span data-stu-id="77fdd-369">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="77fdd-370">`Int`, `BigInt` o `Double` para `-` , `Int` o `BigInt` para `~~~` , `Bool` para`not`</span><span class="sxs-lookup"><span data-stu-id="77fdd-370">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="77fdd-371">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-371">Binary</span></span> | <span data-ttu-id="77fdd-372">Potencia de entero</span><span class="sxs-lookup"><span data-stu-id="77fdd-372">Integer power</span></span> | <span data-ttu-id="77fdd-373">`Int`o `BigInt` para la base, `Int` para el exponente</span><span class="sxs-lookup"><span data-stu-id="77fdd-373">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="77fdd-374">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="77fdd-374">`/`, `*`, `%`</span></span> | <span data-ttu-id="77fdd-375">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-375">Binary</span></span> | <span data-ttu-id="77fdd-376">División, multiplicación, módulo de entero</span><span class="sxs-lookup"><span data-stu-id="77fdd-376">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="77fdd-377">`Int`, `BigInt` o `Double` para `/` y `*` , `Int` o `BigInt` para`%`</span><span class="sxs-lookup"><span data-stu-id="77fdd-377">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="77fdd-378">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="77fdd-378">`+`, `-`</span></span> | <span data-ttu-id="77fdd-379">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-379">Binary</span></span> | <span data-ttu-id="77fdd-380">Suma, concatenación de cadenas y matrices, resta</span><span class="sxs-lookup"><span data-stu-id="77fdd-380">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="77fdd-381">`Int`, `BigInt` o `Double` , además, `String` o cualquier tipo de matriz para`+`</span><span class="sxs-lookup"><span data-stu-id="77fdd-381">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="77fdd-382">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="77fdd-382">`<<<`, `>>>`</span></span> | <span data-ttu-id="77fdd-383">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-383">Binary</span></span> | <span data-ttu-id="77fdd-384">Desplazamiento a la izquierda, desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="77fdd-384">Left shift, right shift</span></span> | <span data-ttu-id="77fdd-385">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="77fdd-385">`Int` or `BigInt`</span></span>
 <span data-ttu-id="77fdd-386">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="77fdd-386">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="77fdd-387">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-387">Binary</span></span> | <span data-ttu-id="77fdd-388">Comparaciones menor que, menor o igual que, mayor que, mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="77fdd-388">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="77fdd-389">`Int`, `BigInt` o`Double`</span><span class="sxs-lookup"><span data-stu-id="77fdd-389">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="77fdd-390">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="77fdd-390">`==`, `!=`</span></span> | <span data-ttu-id="77fdd-391">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-391">Binary</span></span> | <span data-ttu-id="77fdd-392">comparaciones iguales y no iguales</span><span class="sxs-lookup"><span data-stu-id="77fdd-392">equal, not-equal comparisons</span></span> | <span data-ttu-id="77fdd-393">cualquier tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="77fdd-393">any primitive type</span></span>
 `&&&` | <span data-ttu-id="77fdd-394">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-394">Binary</span></span> | <span data-ttu-id="77fdd-395">AND bit a bit</span><span class="sxs-lookup"><span data-stu-id="77fdd-395">Bitwise AND</span></span> | <span data-ttu-id="77fdd-396">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="77fdd-396">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="77fdd-397">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-397">Binary</span></span> | <span data-ttu-id="77fdd-398">XOR bit a bit</span><span class="sxs-lookup"><span data-stu-id="77fdd-398">Bitwise XOR</span></span> | <span data-ttu-id="77fdd-399">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="77fdd-399">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="77fdd-400">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-400">Binary</span></span> | <span data-ttu-id="77fdd-401">OR bit a bit</span><span class="sxs-lookup"><span data-stu-id="77fdd-401">Bitwise OR</span></span> | <span data-ttu-id="77fdd-402">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="77fdd-402">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="77fdd-403">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-403">Binary</span></span> | <span data-ttu-id="77fdd-404">Y lógico</span><span class="sxs-lookup"><span data-stu-id="77fdd-404">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="77fdd-405">Binary</span><span class="sxs-lookup"><span data-stu-id="77fdd-405">Binary</span></span> | <span data-ttu-id="77fdd-406">O lógico</span><span class="sxs-lookup"><span data-stu-id="77fdd-406">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="77fdd-407">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="77fdd-407">Binary/Ternary</span></span> | <span data-ttu-id="77fdd-408">Range (operador)</span><span class="sxs-lookup"><span data-stu-id="77fdd-408">Range operator</span></span> | `Int`
 <span data-ttu-id="77fdd-409">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="77fdd-409">`?` `|`</span></span> | <span data-ttu-id="77fdd-410">Ternario</span><span class="sxs-lookup"><span data-stu-id="77fdd-410">Ternary</span></span> | <span data-ttu-id="77fdd-411">Condicional</span><span class="sxs-lookup"><span data-stu-id="77fdd-411">Conditional</span></span> | <span data-ttu-id="77fdd-412">`Bool`para el lado izquierdo</span><span class="sxs-lookup"><span data-stu-id="77fdd-412">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="77fdd-413">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="77fdd-413">`w/` `<-`</span></span> | <span data-ttu-id="77fdd-414">Ternario</span><span class="sxs-lookup"><span data-stu-id="77fdd-414">Ternary</span></span> | <span data-ttu-id="77fdd-415">Copiar y actualizar</span><span class="sxs-lookup"><span data-stu-id="77fdd-415">Copy-and-update</span></span> | <span data-ttu-id="77fdd-416">vea [expresiones de copia y actualización](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="77fdd-416">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="whats-next"></a><span data-ttu-id="77fdd-417">¿Qué debe hacer a continuación?</span><span class="sxs-lookup"><span data-stu-id="77fdd-417">What's Next?</span></span>
<span data-ttu-id="77fdd-418">Ahora que puede trabajar con expresiones en Q #, puede empezar a usar [operaciones y funciones en q #](xref:microsoft.quantum.guide.operationsfunctions) para obtener información sobre cómo definir y llamar a operaciones y funciones.</span><span class="sxs-lookup"><span data-stu-id="77fdd-418">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
