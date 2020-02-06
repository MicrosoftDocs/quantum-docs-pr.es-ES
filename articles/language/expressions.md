---
title: Expresiones | Microsoft Docs
description: Expresiones
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036321"
---
# <a name="expressions"></a><span data-ttu-id="5897d-103">Expresiones</span><span class="sxs-lookup"><span data-stu-id="5897d-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="5897d-104">Agrupación</span><span class="sxs-lookup"><span data-stu-id="5897d-104">Grouping</span></span>

<span data-ttu-id="5897d-105">Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="5897d-106">Por ejemplo, `(7)` es una expresión `Int`, `([1,2,3])` es una expresión de tipo array de `Int`s y `((1,2))` es una expresión con el tipo `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="5897d-107">La equivalencia entre los valores simples y las tuplas de un solo elemento que se describen en [el modelo de tipo](xref:microsoft.quantum.language.type-model#tuple-types) elimina la ambigüedad entre `(6)` como un grupo y `(6)` como una tupla de un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="5897d-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="5897d-108">Symbols</span><span class="sxs-lookup"><span data-stu-id="5897d-108">Symbols</span></span>

<span data-ttu-id="5897d-109">El nombre de un símbolo enlazado o asignado a un valor de tipo `'T` es una expresión de tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="5897d-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="5897d-110">Por ejemplo, si el `count` de símbolos se enlaza al valor entero `5`, `count` es una expresión de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="5897d-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="5897d-111">Expresiones numéricas</span><span class="sxs-lookup"><span data-stu-id="5897d-111">Numeric Expressions</span></span>

<span data-ttu-id="5897d-112">Las expresiones numéricas son expresiones de tipo `Int`, `BigInt`o `Double`.</span><span class="sxs-lookup"><span data-stu-id="5897d-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="5897d-113">Es decir, son números enteros o de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="5897d-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="5897d-114">`Int` literales en Q # son idénticos a los literales enteros C#en, excepto en que no se requiere (o se permite) ninguna "l" o "l" final.</span><span class="sxs-lookup"><span data-stu-id="5897d-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="5897d-115">Los enteros hexadecimales y binarios se admiten con un prefijo "0x" y "0B", respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5897d-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="5897d-116">`BigInt` literales en Q # son idénticos a cadenas de tipo entero Big en .NET, con una "l" o "L" final.</span><span class="sxs-lookup"><span data-stu-id="5897d-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="5897d-117">Los enteros Big hexadecimales se admiten con un prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="5897d-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="5897d-118">Por lo tanto, a continuación se muestran todos los usos válidos de `BigInt` literales:</span><span class="sxs-lookup"><span data-stu-id="5897d-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="5897d-119">`Double` literales en Q # son idénticos a los literales C#dobles de, salvo que no se requiere (o se permite) ninguna "d" o "d" final.</span><span class="sxs-lookup"><span data-stu-id="5897d-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="5897d-120">Dada una expresión de matriz de cualquier tipo de elemento, una expresión `Int` se puede formar utilizando la función integrada `Length`, con la expresión de matriz entre paréntesis, `(` y `)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="5897d-121">Por ejemplo, si `a` se enlaza a una matriz, `Length(a)` es una expresión de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="5897d-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="5897d-122">Si `b` es una matriz de matrices de enteros, `Int[][]`, `Length(b)` es el número de submatrices de `b`y `Length(b[1])` es el número de enteros de la segunda submatriz de `b`...</span><span class="sxs-lookup"><span data-stu-id="5897d-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="5897d-123">Dadas dos expresiones numéricas del mismo tipo, los operadores binarios `+`, `-`, `*`y `/` se pueden usar para formar una nueva expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="5897d-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="5897d-124">El tipo de la nueva expresión será el mismo que los tipos de las expresiones constituyentes.</span><span class="sxs-lookup"><span data-stu-id="5897d-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="5897d-125">Dadas dos expresiones de tipo entero, el operador binario `^` (Power) se puede usar para formar una nueva expresión de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="5897d-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="5897d-126">Del mismo modo, `^` se pueden utilizar con dos expresiones Double para formar una nueva expresión Double.</span><span class="sxs-lookup"><span data-stu-id="5897d-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="5897d-127">Por último, se puede usar `^` con un entero grande a la izquierda y un entero a la derecha para formar una nueva expresión de tipo entero grande.</span><span class="sxs-lookup"><span data-stu-id="5897d-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="5897d-128">En este caso, el segundo parámetro debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5897d-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="5897d-129">Dadas dos expresiones integer o Big Integer, se puede formar una nueva expresión de tipo entero o grande con los operadores `%` (módulo), `&&&` (and bit a bit), `|||` (OR bit a bit) o `^^^` (XOR bit a bit).</span><span class="sxs-lookup"><span data-stu-id="5897d-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="5897d-130">Si se especifica una expresión de tipo entero o Big Integer a la izquierda, y una expresión de entero a la derecha, se pueden usar los operadores `<<<` (desplazamiento aritmético a la izquierda) o `>>>` (desplazamiento aritmético a la derecha) para crear una nueva expresión con el mismo tipo que la expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5897d-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="5897d-131">El segundo parámetro (la cantidad de desplazamiento) de una operación de desplazamiento debe ser mayor o igual que cero; el comportamiento de los valores de desplazamiento negativos es indefinido.</span><span class="sxs-lookup"><span data-stu-id="5897d-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="5897d-132">La cantidad de desplazamiento de una operación de desplazamiento también debe caber en 32 bits; Si no es así, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5897d-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="5897d-133">Si el número que se va a desplazar es un entero, la cantidad de desplazamiento se interpreta `mod 64`; es decir, un desplazamiento de 1 y un turno de 65 tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="5897d-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="5897d-134">En el caso de los valores entero y Big Integer, ShiftS es aritmético.</span><span class="sxs-lookup"><span data-stu-id="5897d-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="5897d-135">Si se desplaza un valor negativo a la izquierda o a la derecha, se producirá un número negativo.</span><span class="sxs-lookup"><span data-stu-id="5897d-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="5897d-136">Es decir, el desplazamiento de un paso a la izquierda o a la derecha es exactamente el mismo que si se multiplica o se divide por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5897d-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="5897d-137">La división de enteros y los módulos de enteros siguen el mismo comportamiento para los C#números negativos que.</span><span class="sxs-lookup"><span data-stu-id="5897d-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="5897d-138">Es decir, `a % b` siempre tendrá el mismo signo que `a`y `b * (a / b) + a % b` siempre será igual `a`.</span><span class="sxs-lookup"><span data-stu-id="5897d-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="5897d-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5897d-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="5897d-140">5</span><span class="sxs-lookup"><span data-stu-id="5897d-140">5</span></span> | <span data-ttu-id="5897d-141">2</span><span class="sxs-lookup"><span data-stu-id="5897d-141">2</span></span> | <span data-ttu-id="5897d-142">2</span><span class="sxs-lookup"><span data-stu-id="5897d-142">2</span></span> | <span data-ttu-id="5897d-143">1</span><span class="sxs-lookup"><span data-stu-id="5897d-143">1</span></span>
 <span data-ttu-id="5897d-144">5</span><span class="sxs-lookup"><span data-stu-id="5897d-144">5</span></span> | <span data-ttu-id="5897d-145">-2</span><span class="sxs-lookup"><span data-stu-id="5897d-145">-2</span></span> | <span data-ttu-id="5897d-146">-2</span><span class="sxs-lookup"><span data-stu-id="5897d-146">-2</span></span> | <span data-ttu-id="5897d-147">1</span><span class="sxs-lookup"><span data-stu-id="5897d-147">1</span></span>
 <span data-ttu-id="5897d-148">-5</span><span class="sxs-lookup"><span data-stu-id="5897d-148">-5</span></span> | <span data-ttu-id="5897d-149">2</span><span class="sxs-lookup"><span data-stu-id="5897d-149">2</span></span> | <span data-ttu-id="5897d-150">-2</span><span class="sxs-lookup"><span data-stu-id="5897d-150">-2</span></span> | <span data-ttu-id="5897d-151">-1</span><span class="sxs-lookup"><span data-stu-id="5897d-151">-1</span></span>
 <span data-ttu-id="5897d-152">-5</span><span class="sxs-lookup"><span data-stu-id="5897d-152">-5</span></span> | <span data-ttu-id="5897d-153">-2</span><span class="sxs-lookup"><span data-stu-id="5897d-153">-2</span></span> | <span data-ttu-id="5897d-154">2</span><span class="sxs-lookup"><span data-stu-id="5897d-154">2</span></span> | <span data-ttu-id="5897d-155">-1</span><span class="sxs-lookup"><span data-stu-id="5897d-155">-1</span></span>

<span data-ttu-id="5897d-156">La división y el módulo Big Integer funcionan de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="5897d-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="5897d-157">Dada cualquier expresión numérica, se puede formar una nueva expresión mediante el `-` operador unario.</span><span class="sxs-lookup"><span data-stu-id="5897d-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="5897d-158">La nueva expresión será del mismo tipo que la expresión constituyente.</span><span class="sxs-lookup"><span data-stu-id="5897d-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="5897d-159">Dado cualquier expresión integer o Big Integer, se puede formar una nueva expresión del mismo tipo mediante el operador unario `~~~` (complemento bit a bit).</span><span class="sxs-lookup"><span data-stu-id="5897d-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="5897d-160">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="5897d-160">Boolean Expressions</span></span>

<span data-ttu-id="5897d-161">Los dos `Bool` valores literales son `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="5897d-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="5897d-162">Dadas dos expresiones cualesquiera del mismo tipo primitivo, se pueden usar los operadores binarios `==` y `!=` para construir una expresión `Bool`.</span><span class="sxs-lookup"><span data-stu-id="5897d-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="5897d-163">La expresión será true si las dos expresiones son iguales y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="5897d-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="5897d-164">No se pueden comparar los valores de los tipos definidos por el usuario, solo se pueden comparar los valores desencapsulados.</span><span class="sxs-lookup"><span data-stu-id="5897d-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="5897d-165">Por ejemplo, mediante el operador "desencapsular" `!` (se explica en la [Página modelo de Q # type](xref:microsoft.quantum.language.type-model#user-defined-types)).</span><span class="sxs-lookup"><span data-stu-id="5897d-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="5897d-166">La comparación de igualdad para los valores `Qubit` es la igualdad de identidad; es decir, si las dos expresiones identifican el mismo qubit.</span><span class="sxs-lookup"><span data-stu-id="5897d-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="5897d-167">Esta comparación no compara, tiene acceso, mide o modifica el estado de los dos qubits.</span><span class="sxs-lookup"><span data-stu-id="5897d-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="5897d-168">La comparación de igualdad para los valores de `Double` puede ser engañosa debido a efectos de redondeo.</span><span class="sxs-lookup"><span data-stu-id="5897d-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="5897d-169">Por ejemplo, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="5897d-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="5897d-170">Dadas dos expresiones numéricas, se pueden usar los operadores binarios `>`, `<`, `>=`y `<=` para construir una nueva expresión booleana que es true si la primera expresión es respectivamente mayor que, menor que, mayor o igual que, o menor o igual que la segunda expresión.</span><span class="sxs-lookup"><span data-stu-id="5897d-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="5897d-171">Dadas dos expresiones booleanas, se pueden usar los operadores binarios `and` y `or` para construir una nueva expresión booleana que es true si las dos expresiones son verdaderas (o ambas).</span><span class="sxs-lookup"><span data-stu-id="5897d-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="5897d-172">Dada cualquier expresión booleana, el `not` operador unario se puede usar para construir una nueva expresión booleana que es true si la expresión constituyente es falsa.</span><span class="sxs-lookup"><span data-stu-id="5897d-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="5897d-173">Expresiones de cadena</span><span class="sxs-lookup"><span data-stu-id="5897d-173">String Expressions</span></span>

<span data-ttu-id="5897d-174">Q # permite usar cadenas en la instrucción `fail` y en la función estándar `Log`.</span><span class="sxs-lookup"><span data-stu-id="5897d-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="5897d-175">Las cadenas en Q # son literales o cadenas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="5897d-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="5897d-176">Los literales de cadena son similares a los literales de cadena simples en la mayoría de los lenguajes: una secuencia de caracteres Unicode entre comillas dobles, `"`.</span><span class="sxs-lookup"><span data-stu-id="5897d-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="5897d-177">Dentro de una cadena, el carácter de barra diagonal inversa `\` se puede usar para escapar un carácter de comilla doble e insertar una nueva línea como `\n`, un retorno de carro como `\r`y una tabulación como `\t`.</span><span class="sxs-lookup"><span data-stu-id="5897d-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="5897d-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5897d-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="5897d-179">La sintaxis de Q # para las interpolaciones de cadenas es un C# subconjunto de la sintaxis 7,0; Q # no admite cadenas interpoladas textuales (multilínea).</span><span class="sxs-lookup"><span data-stu-id="5897d-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="5897d-180">Vea [*cadenas interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para la C# sintaxis.</span><span class="sxs-lookup"><span data-stu-id="5897d-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="5897d-181">Las expresiones incluidas en una cadena interpolada siguen la sintaxis de Q C# #, no la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="5897d-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="5897d-182">Cualquier expresión Q # válida puede aparecer en una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="5897d-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="5897d-183">Expresiones qubit</span><span class="sxs-lookup"><span data-stu-id="5897d-183">Qubit Expressions</span></span>

<span data-ttu-id="5897d-184">Las únicas expresiones `Qubit` son símbolos que se enlazan a `Qubit` valores o elementos de matriz de matrices de `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="5897d-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="5897d-185">No hay literales de `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="5897d-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="5897d-186">Expresiones Pauli</span><span class="sxs-lookup"><span data-stu-id="5897d-186">Pauli Expressions</span></span>

<span data-ttu-id="5897d-187">Los cuatro valores `Pauli`, `PauliI`, `PauliX`, `PauliY`y `PauliZ`son expresiones de `Pauli` válidas.</span><span class="sxs-lookup"><span data-stu-id="5897d-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="5897d-188">Aparte de eso, las únicas expresiones `Pauli` son símbolos que están enlazados a `Pauli` valores o elementos de matriz de `Pauli` matrices.</span><span class="sxs-lookup"><span data-stu-id="5897d-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="5897d-189">Expresiones de resultado</span><span class="sxs-lookup"><span data-stu-id="5897d-189">Result Expressions</span></span>

<span data-ttu-id="5897d-190">Los dos valores `Result`, `One` y `Zero`, son expresiones de `Result` válidas.</span><span class="sxs-lookup"><span data-stu-id="5897d-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="5897d-191">Aparte de eso, las únicas expresiones `Result` son símbolos que están enlazados a `Result` valores o elementos de matriz de `Result` matrices.</span><span class="sxs-lookup"><span data-stu-id="5897d-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="5897d-192">En concreto, tenga en cuenta que `One` no es el mismo que el `1`entero y no hay ninguna conversión directa entre ellos.</span><span class="sxs-lookup"><span data-stu-id="5897d-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="5897d-193">Lo mismo se aplica a `Zero` y `0`.</span><span class="sxs-lookup"><span data-stu-id="5897d-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="5897d-194">Expresiones de rango</span><span class="sxs-lookup"><span data-stu-id="5897d-194">Range Expressions</span></span>

<span data-ttu-id="5897d-195">Dadas las tres expresiones `Int` `start`, `step`y `stop`, `start .. step .. stop` es una expresión de rango cuyo primer elemento es `start`, el segundo elemento es `start+step`, el tercer elemento es `start+step+step`, etc., hasta que se pasa `stop`.</span><span class="sxs-lookup"><span data-stu-id="5897d-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="5897d-196">Un intervalo puede estar vacío si, por ejemplo, `step` es positivo y `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="5897d-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="5897d-197">El último elemento del intervalo se `stop` si la diferencia entre `start` y `stop` es un múltiplo entero de `step`; es decir, el intervalo es inclusivo en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="5897d-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="5897d-198">Dado dos expresiones `Int` `start` y `stop`, `start .. stop` es una expresión de rango que es igual a `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="5897d-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="5897d-199">Tenga en cuenta que el `step` implícito es + 1 incluso si `stop` es menor que `start`; en tal caso, el intervalo está vacío.</span><span class="sxs-lookup"><span data-stu-id="5897d-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="5897d-200">Algunos intervalos de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="5897d-200">Some example ranges are:</span></span>

- <span data-ttu-id="5897d-201">`1..3` es el intervalo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="5897d-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="5897d-202">`2..2..5` es el intervalo de 2 a 4.</span><span class="sxs-lookup"><span data-stu-id="5897d-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="5897d-203">`2..2..6` es el intervalo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="5897d-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="5897d-204">`6..-2..2` es el rango 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="5897d-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="5897d-205">`2..1` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="5897d-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="5897d-206">`2..6..7` es el intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="5897d-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="5897d-207">`2..2..1` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="5897d-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="5897d-208">`1..-1..2` es el intervalo vacío.</span><span class="sxs-lookup"><span data-stu-id="5897d-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="5897d-209">Expresiones Invocables</span><span class="sxs-lookup"><span data-stu-id="5897d-209">Callable Expressions</span></span>

<span data-ttu-id="5897d-210">Un literal al que se puede llamar es el nombre de una operación o función definida en el ámbito de compilación.</span><span class="sxs-lookup"><span data-stu-id="5897d-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="5897d-211">Por ejemplo, `X` es un literal de operación que hace referencia a la operación de `X` de la biblioteca estándar y `Message` es un literal de función que hace referencia a la función `Message` de la biblioteca estándar.</span><span class="sxs-lookup"><span data-stu-id="5897d-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="5897d-212">Si una operación admite la `Adjoint` functor, `Adjoint op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="5897d-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="5897d-213">Del mismo modo, si la operación admite la `Controlled` functor, `Controlled op` es una expresión de operación.</span><span class="sxs-lookup"><span data-stu-id="5897d-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="5897d-214">Los tipos de estas expresiones se especifican en [funcs](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="5897d-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="5897d-215">Los funcers (`Adjoint` y `Controlled`) se enlazan más estrechamente que todos los demás operadores, excepto el operador Unwrap `!` y la indexación de matrices con `[]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="5897d-216">Por lo tanto, todos los siguientes son válidos, suponiendo que las operaciones admiten los elementos que se usan de forma inactiva:</span><span class="sxs-lookup"><span data-stu-id="5897d-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="5897d-217">Un literal al que se puede llamar se puede usar como un valor, por ejemplo, para asignar a una variable o para pasar a otra que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="5897d-218">En este caso, si el que se puede llamar tiene parámetros de tipo, deben proporcionarse como parte del valor al que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="5897d-219">Un valor al que se puede llamar no puede tener ningún parámetro de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="5897d-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="5897d-220">Por ejemplo, si `Fun` es una función con `'T1->Unit`de firma:</span><span class="sxs-lookup"><span data-stu-id="5897d-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="5897d-221">Expresiones de invocación Invocables</span><span class="sxs-lookup"><span data-stu-id="5897d-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="5897d-222">Dada una expresión a la que se puede llamar (operación o función) y una expresión de tupla del tipo de entrada de la firma de la que se puede llamar, se puede formar una expresión de invocación anexando la expresión de tupla a la expresión a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="5897d-223">El tipo de la expresión de invocación es el tipo de salida de la firma de la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="5897d-224">Por ejemplo, si `Op` es una operación con `((Int, Qubit) => Double)`de firma, `Op(3, qubit1)` es una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="5897d-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5897d-225">Del mismo modo, si `Sin` es una función con `(Double -> Double)`de firma, `Sin(0.1)` es una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="5897d-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5897d-226">Por último, si `Builder` es una función con `(Int -> (Int -> Int))`de firma, `Builder(3)` es una función de into a int.</span><span class="sxs-lookup"><span data-stu-id="5897d-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="5897d-227">La invocación del resultado de una expresión de valor que se puede llamar requiere un par adicional de paréntesis alrededor de la expresión a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="5897d-228">Por lo tanto, para invocar el resultado de llamar a `Builder` del párrafo anterior, la sintaxis correcta es:</span><span class="sxs-lookup"><span data-stu-id="5897d-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="5897d-229">Al invocar un parámetro de tipo al que se puede llamar, los parámetros de tipo reales se pueden especificar entre corchetes angulares `<` y `>` después de la expresión que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="5897d-230">Normalmente esto no es necesario, ya que el compilador de preguntas y respuestas inferirá los tipos reales.</span><span class="sxs-lookup"><span data-stu-id="5897d-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="5897d-231">Es necesario para la aplicación parcial (vea más abajo) si no se especifica un argumento con parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="5897d-232">También es útil a veces cuando se pasan operaciones con un functor diferente para llamar a.</span><span class="sxs-lookup"><span data-stu-id="5897d-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="5897d-233">Por ejemplo, si `Func` tiene `('T1, 'T2, 'T1) -> 'T2`de firma, `Op1` y `Op2` tienen `(Qubit[] => Unit is Adj)`de firma y `Op3` tiene `(Qubit[] => Unit)`de firma, para invocar `Func` con `Op1` como primer argumento, `Op2` como segundo y `Op3` como el tercero:</span><span class="sxs-lookup"><span data-stu-id="5897d-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="5897d-234">La especificación de tipo es necesaria porque `Op3` y `Op1` tienen tipos diferentes, por lo que el compilador lo tratará como ambiguo sin la especificación.</span><span class="sxs-lookup"><span data-stu-id="5897d-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="5897d-235">Aplicación parcial</span><span class="sxs-lookup"><span data-stu-id="5897d-235">Partial Application</span></span>

<span data-ttu-id="5897d-236">Dada una expresión invocable, se puede crear una nueva a la que se pueda llamar proporcionando un subconjunto de los argumentos al que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="5897d-237">Esto se denomina _aplicación parcial_.</span><span class="sxs-lookup"><span data-stu-id="5897d-237">This is called _partial application_.</span></span>

<span data-ttu-id="5897d-238">En Q #, una función de llamada parcialmente aplicada se expresa escribiendo una expresión de invocación normal, pero usando un carácter de subrayado, `_`, para los argumentos no especificados.</span><span class="sxs-lookup"><span data-stu-id="5897d-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="5897d-239">La operación invocable resultante tiene el mismo tipo de resultado que la base a la que se puede llamar y las mismas especializaciones para las operaciones.</span><span class="sxs-lookup"><span data-stu-id="5897d-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="5897d-240">El tipo de entrada de la aplicación parcial es simplemente el tipo original con los argumentos especificados quitados.</span><span class="sxs-lookup"><span data-stu-id="5897d-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="5897d-241">Si se pasa una variable mutable como argumento especificado al crear una aplicación parcial, se utiliza el valor actual de la variable.</span><span class="sxs-lookup"><span data-stu-id="5897d-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="5897d-242">El cambio del valor de la variable después no afectará a la aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="5897d-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="5897d-243">Por ejemplo, si `Op` tiene el tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="5897d-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="5897d-244">`Op(5,(_,_))` tiene el tipo `(((Qubit,Qubit), Double) => Unit is Adj)`y, por tanto, tiene `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="5897d-245">`Op(_,(_,1.0))` tiene el tipo `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="5897d-246">`Op(_,((q1,q2),_))` tiene el tipo `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="5897d-247">Tenga en cuenta que hemos aplicado aquí la equivalencia de tupla singleton.</span><span class="sxs-lookup"><span data-stu-id="5897d-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="5897d-248">Si la llamada aplicada parcialmente tiene parámetros de tipo que el compilador no puede inferir, deben proporcionarse en el sitio de invocación.</span><span class="sxs-lookup"><span data-stu-id="5897d-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="5897d-249">La aplicación parcial no puede tener ningún parámetro de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="5897d-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="5897d-250">Por ejemplo, si `Op` tiene el tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="5897d-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="5897d-251">Recursividad</span><span class="sxs-lookup"><span data-stu-id="5897d-251">Recursion</span></span>

<span data-ttu-id="5897d-252">Se permite que las llamadas a Q # sean recursivas directa o indirectamente.</span><span class="sxs-lookup"><span data-stu-id="5897d-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="5897d-253">Es decir, una operación o función se puede llamar a sí misma, o puede llamar a otra llamada invocable que llama directa o indirectamente a la operación que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="5897d-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="5897d-254">Sin embargo, hay dos comentarios importantes sobre el uso de la recursividad:</span><span class="sxs-lookup"><span data-stu-id="5897d-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="5897d-255">Es probable que el uso de la recursividad en las operaciones interfiera con ciertas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="5897d-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="5897d-256">Esto puede tener un impacto considerable en el tiempo de ejecución del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5897d-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="5897d-257">Cuando se ejecuta en un dispositivo Quantum real, el espacio de pila puede estar limitado y, por tanto, la recursividad profunda puede provocar un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5897d-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="5897d-258">En concreto, el compilador y el tiempo de ejecución de Q # no identifican y optimizan la recursividad del final.</span><span class="sxs-lookup"><span data-stu-id="5897d-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="5897d-259">Expresiones de tupla</span><span class="sxs-lookup"><span data-stu-id="5897d-259">Tuple Expressions</span></span>

<span data-ttu-id="5897d-260">Un literal de tupla es una secuencia de expresiones de elemento del tipo adecuado, separadas por comas, delimitadas por `(` y `)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="5897d-261">Por ejemplo, `(1, One)` es una expresión de `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="5897d-262">Aparte de los literales, las únicas expresiones de tupla son símbolos que se enlazan a valores de tupla, elementos de matriz de matrices de tupla e invocaciones Invocables que devuelven tuplas.</span><span class="sxs-lookup"><span data-stu-id="5897d-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="5897d-263">Expresiones de tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="5897d-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="5897d-264">Un literal de un tipo definido por el usuario consta del nombre de tipo seguido de un literal de tupla del tipo de tupla base del tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="5897d-265">Por ejemplo, si `IntPair` es un tipo definido por el usuario basado en `(Int, Int)`, `IntPair(2,3)` sería un literal válido de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="5897d-266">Aparte de los literales, las únicas expresiones de un tipo definido por el usuario son los símbolos que se enlazan a los valores de ese tipo, los elementos de matriz de las matrices de ese tipo y las invocaciones Invocables que devuelven ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="5897d-267">Desencapsular expresiones</span><span class="sxs-lookup"><span data-stu-id="5897d-267">Unwrap Expressions</span></span>

<span data-ttu-id="5897d-268">En Q #, el operador Unwrap es un signo de exclamación final `!`.</span><span class="sxs-lookup"><span data-stu-id="5897d-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="5897d-269">Por ejemplo, si `IntPair` es un tipo definido por el usuario con el tipo subyacente `(Int, Int)`y `s` era una variable con `IntPair(2,3)`de valor, `s!` sería `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="5897d-270">Para los tipos definidos por el usuario definidos en términos de otros tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5897d-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="5897d-271">el operador Unwrap puede repetirse; por ejemplo, `s!!` indica el valor doble de desencapsulado de `s`.</span><span class="sxs-lookup"><span data-stu-id="5897d-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="5897d-272">Por lo tanto, si `WrappedPair` es un tipo definido por el usuario con el tipo subyacente `IntPair`y `t` es una variable con `WrappedPair(IntPair(1,2))`de valor, `t!!` se `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="5897d-273">El operador `!` tiene mayor precedencia que el resto de operadores distintos de `[]` para la indización y segmentación de matrices.</span><span class="sxs-lookup"><span data-stu-id="5897d-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="5897d-274">`!` y `[]` enlazar de posición; es decir, `a[i]![3]` se debe leer como `((a[i])!)[3]`: tome el `i`elemento de `a`, desajustelo y, a continuación, obtenga el tercer elemento del valor desencapsulado (que debe ser una matriz).</span><span class="sxs-lookup"><span data-stu-id="5897d-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="5897d-275">La precedencia del operador `!` tiene un impacto que podría no ser obvio.</span><span class="sxs-lookup"><span data-stu-id="5897d-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="5897d-276">Si una función u operación devuelve un valor que, a continuación, se desencapsula, la llamada a la función o la operación se debe incluir entre paréntesis para que la tupla del argumento se enlace a la llamada en lugar de a la desencapsulación.</span><span class="sxs-lookup"><span data-stu-id="5897d-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="5897d-277">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5897d-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="5897d-278">Expresiones de matriz</span><span class="sxs-lookup"><span data-stu-id="5897d-278">Array Expressions</span></span>

<span data-ttu-id="5897d-279">Un literal de matriz es una secuencia de una o varias expresiones de elemento, separadas por comas, delimitadas por `[` y `]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="5897d-280">Todos los elementos deben ser compatibles con el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="5897d-281">Si el tipo de elemento común es una operación o un tipo de función, todos los elementos deben tener los mismos tipos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="5897d-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="5897d-282">El tipo de elemento de la matriz será compatible con cualquier functor que admitan todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="5897d-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="5897d-283">Por ejemplo, si se `Qubit[] => Unit``Op1`, `Op2`y `Op3` todos, pero `Op1` admite `Adjoint`, `Op2` admite `Controlled`y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="5897d-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5897d-284">`[Op1, Op2]` es una matriz de operaciones de `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="5897d-285">`[Op1, Op3]` es una matriz de operaciones de `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="5897d-286">`[Op2, Op3]` es una matriz de operaciones de `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="5897d-287">No se permiten literales de matriz vacíos, `[]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="5897d-288">En lugar de usar `new ★[0]`, donde `★` es como marcador de posición para un tipo adecuado, permite crear la matriz deseada de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="5897d-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="5897d-289">Dadas dos matrices del mismo tipo, se puede utilizar el operador binario `+` para formar una nueva matriz que es la concatenación de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="5897d-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="5897d-290">Por ejemplo, `[1,2,3] + [4,5,6]` es `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="5897d-291">Creación de matriz</span><span class="sxs-lookup"><span data-stu-id="5897d-291">Array Creation</span></span>

<span data-ttu-id="5897d-292">Dado un tipo y una expresión de `Int`, el operador de `new` se puede utilizar para asignar una nueva matriz del tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="5897d-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="5897d-293">Por ejemplo, `new Int[i+1]` asignaría una nueva matriz de `Int` con elementos `i+1`.</span><span class="sxs-lookup"><span data-stu-id="5897d-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="5897d-294">Los elementos de una nueva matriz se inicializan en un valor predeterminado dependiente del tipo.</span><span class="sxs-lookup"><span data-stu-id="5897d-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="5897d-295">En la mayoría de los casos, se trata de una variación de cero.</span><span class="sxs-lookup"><span data-stu-id="5897d-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="5897d-296">Para qubits y Callable, que son referencias a entidades, no hay ningún valor predeterminado razonable.</span><span class="sxs-lookup"><span data-stu-id="5897d-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="5897d-297">Por lo tanto, para estos tipos, el valor predeterminado es una referencia no válida que no se puede utilizar sin que se produzca un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5897d-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="5897d-298">Esto es similar a una referencia nula en lenguajes como C# o Java.</span><span class="sxs-lookup"><span data-stu-id="5897d-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="5897d-299">Las matrices que contienen qubits o llamadas se deben inicializar correctamente con valores no predeterminados antes de que sus elementos se puedan usar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="5897d-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="5897d-300">En <xref:microsoft.quantum.arrays>se pueden encontrar rutinas de inicialización adecuadas.</span><span class="sxs-lookup"><span data-stu-id="5897d-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="5897d-301">Los valores predeterminados para cada tipo son:</span><span class="sxs-lookup"><span data-stu-id="5897d-301">The default values for each type are:</span></span>

<span data-ttu-id="5897d-302">Tipo</span><span class="sxs-lookup"><span data-stu-id="5897d-302">Type</span></span> | <span data-ttu-id="5897d-303">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="5897d-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="5897d-304">_qubit no válido_</span><span class="sxs-lookup"><span data-stu-id="5897d-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="5897d-305">Rango vacío, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="5897d-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="5897d-306">_no válido_</span><span class="sxs-lookup"><span data-stu-id="5897d-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="5897d-307">Los tipos de tupla se inicializan elemento a elemento.</span><span class="sxs-lookup"><span data-stu-id="5897d-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="5897d-308">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="5897d-308">Jagged Arrays</span></span>

<span data-ttu-id="5897d-309">Una matriz escalonada, a veces denominada "matriz de matrices", es una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="5897d-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="5897d-310">Los elementos de una matriz escalonada pueden tener distintos tamaños.</span><span class="sxs-lookup"><span data-stu-id="5897d-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="5897d-311">En el ejemplo siguiente se muestra cómo declarar e inicializar una matriz escalonada que representa una tabla de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="5897d-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="5897d-312">Segmentos de matriz</span><span class="sxs-lookup"><span data-stu-id="5897d-312">Array Slices</span></span>

<span data-ttu-id="5897d-313">Dada una expresión de matriz y una expresión de `Range`, se puede formar una nueva expresión mediante el operador `[` y `]` segmento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5897d-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="5897d-314">La nueva expresión será del mismo tipo que la matriz y contendrá los elementos de matriz indizados por los elementos de la `Range`, en el orden definido por la `Range`.</span><span class="sxs-lookup"><span data-stu-id="5897d-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="5897d-315">Por ejemplo, si `a` está enlazado a una matriz de `Double`s, `a[3..-1..0]` es una expresión de `Double[]` que contiene los cuatro primeros elementos de `a`, pero en orden inverso a medida que aparecen en `a`.</span><span class="sxs-lookup"><span data-stu-id="5897d-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="5897d-316">Si el `Range` está vacío, el segmento de la matriz resultante tendrá una longitud de cero.</span><span class="sxs-lookup"><span data-stu-id="5897d-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="5897d-317">Si la expresión de matriz no es un identificador simple, debe encerrarse entre paréntesis para segmentar.</span><span class="sxs-lookup"><span data-stu-id="5897d-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="5897d-318">Por ejemplo, si `a` y `b` son matrices de `Int`s, un segmento de la concatenación se expresaría como:</span><span class="sxs-lookup"><span data-stu-id="5897d-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="5897d-319">Todas las matrices en Q # son de base cero.</span><span class="sxs-lookup"><span data-stu-id="5897d-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="5897d-320">Es decir, el primer elemento de una matriz `a` siempre se `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="5897d-321">A partir de la versión 0,8, se admiten expresiones contextuales para la segmentación de intervalos.</span><span class="sxs-lookup"><span data-stu-id="5897d-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="5897d-322">En concreto, los valores de inicio y fin de intervalo se pueden omitir en el contexto de una expresión de división de intervalo.</span><span class="sxs-lookup"><span data-stu-id="5897d-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="5897d-323">En ese caso, el compilador aplicará las siguientes reglas para deducir los delimitadores deseados para el intervalo.</span><span class="sxs-lookup"><span data-stu-id="5897d-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="5897d-324">Por ejemplo, si se omite el valor de inicio de intervalo, el valor de inicio deducido</span><span class="sxs-lookup"><span data-stu-id="5897d-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="5897d-325">es cero si no se especifica ningún paso o el paso especificado es positivo, y</span><span class="sxs-lookup"><span data-stu-id="5897d-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5897d-326">es la longitud de la matriz segmentada menos uno si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="5897d-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="5897d-327">Si se omite el valor final del intervalo, el valor final deducido</span><span class="sxs-lookup"><span data-stu-id="5897d-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="5897d-328">es la longitud de la matriz segmentada menos uno si no se especifica ningún paso o el paso especificado es positivo, y</span><span class="sxs-lookup"><span data-stu-id="5897d-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5897d-329">es cero si el paso especificado es negativo.</span><span class="sxs-lookup"><span data-stu-id="5897d-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="5897d-330">Expresiones de elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="5897d-330">Array Element Expressions</span></span>

<span data-ttu-id="5897d-331">Dada una expresión de matriz y una expresión de `Int`, se puede formar una nueva expresión mediante el operador de elementos de matriz `[` y `]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="5897d-332">La nueva expresión será del mismo tipo que el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5897d-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="5897d-333">Por ejemplo, si `a` está enlazado a una matriz de `Double`s, `a[4]` es una expresión de `Double`.</span><span class="sxs-lookup"><span data-stu-id="5897d-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="5897d-334">Si la expresión de matriz no es un identificador simple, debe encerrarse entre paréntesis para poder seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="5897d-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="5897d-335">Por ejemplo, si `a` y `b` son matrices de `Int`s, un elemento de la concatenación se expresaría como:</span><span class="sxs-lookup"><span data-stu-id="5897d-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="5897d-336">Todas las matrices en Q # son de base cero.</span><span class="sxs-lookup"><span data-stu-id="5897d-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="5897d-337">Es decir, el primer elemento de una matriz `a` siempre se `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="5897d-338">Expresiones de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="5897d-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="5897d-339">Las nuevas matrices se pueden crear a partir de las existentes a través de expresiones de copia y actualización.</span><span class="sxs-lookup"><span data-stu-id="5897d-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="5897d-340">Una expresión de copia y actualización es una expresión con el formato `expression1 w/ expression2 <- expression3`, donde `expression1` debe ser de tipo `T[]` para algún tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5897d-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="5897d-341">La segunda `expression2` define los índices de los elementos que se van a modificar en comparación con la matriz de `expression1` y debe ser de tipo `Int` o de `Range`.</span><span class="sxs-lookup"><span data-stu-id="5897d-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="5897d-342">Si `expression2` es de tipo `Int`, `expression3` debe ser de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5897d-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="5897d-343">Si `expression2` es de tipo `Range`, `expression3` debe ser de tipo `T[]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="5897d-344">Una expresión de copia y actualización `arr w/ idx <- value` crea una nueva matriz con todos los elementos establecidos en el elemento correspondiente en `arr`, excepto los elementos de `idx`, que se establecen en los elementos de la `value`.</span><span class="sxs-lookup"><span data-stu-id="5897d-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="5897d-345">Por ejemplo, si `arr` contiene una matriz `[0,1,2,3]`,</span><span class="sxs-lookup"><span data-stu-id="5897d-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="5897d-346">`arr w/ 0 <- 10` es la matriz `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="5897d-347">`arr w/ 2 <- 10` es la matriz `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="5897d-348">`arr w/ 0..2..3 <- [10,12]` es la matriz `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="5897d-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="5897d-349">Existen expresiones similares para los elementos con nombre en los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5897d-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="5897d-350">Considere, por ejemplo, el tipo</span><span class="sxs-lookup"><span data-stu-id="5897d-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="5897d-351">Si `c` contiene el valor de tipo `Complex(1.,-1.)`, `c w/ Re <- 0.` es una expresión de tipo `Complex` que se evalúa como `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="5897d-352">Expresiones condicionales</span><span class="sxs-lookup"><span data-stu-id="5897d-352">Conditional Expressions</span></span>

<span data-ttu-id="5897d-353">Dadas otras dos expresiones del mismo tipo y una expresión booleana, la expresión condicional se puede formar con el signo de interrogación `?` y la barra vertical `|`.</span><span class="sxs-lookup"><span data-stu-id="5897d-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="5897d-354">Por ejemplo, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="5897d-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="5897d-355">En este ejemplo, el valor de la expresión condicional será `c` si `a==b` es true y `d` si es false.</span><span class="sxs-lookup"><span data-stu-id="5897d-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="5897d-356">Las dos expresiones pueden evaluarse como operaciones que tienen las mismas entradas y salidas, pero admiten los distintos funcdores.</span><span class="sxs-lookup"><span data-stu-id="5897d-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="5897d-357">En este caso, el tipo de la expresión condicional es una operación con esas entradas y salidas que admite cualquier functor compatible con ambas expresiones.</span><span class="sxs-lookup"><span data-stu-id="5897d-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="5897d-358">Por ejemplo, si se `Qubit[]=>Unit``Op1`, `Op2`y `Op3` todos, pero `Op1` admite `Adjoint`, `Op2` admite `Controlled`y `Op3` admite ambos:</span><span class="sxs-lookup"><span data-stu-id="5897d-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5897d-359">`flag ? Op1 | Op2` es una operación de `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="5897d-360">`flag ? Op1 | Op3` es una operación de `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="5897d-361">`flag ? Op2 | Op3` es una operación de `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="5897d-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="5897d-362">Si cualquiera de las dos expresiones de resultado posibles incluye una llamada a una función o una operación, esa llamada solo tendrá lugar si ese resultado es el que será el valor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5897d-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="5897d-363">Por ejemplo, en el caso `a==b ? C(qs) | D(qs)`, si `a==b` es true, se invocará la operación de `C` y, si es false, solo se invocará `D`.</span><span class="sxs-lookup"><span data-stu-id="5897d-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="5897d-364">Esto es similar a la cortocircuito en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="5897d-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="5897d-365">Prioridad de los operadores</span><span class="sxs-lookup"><span data-stu-id="5897d-365">Operator Precedence</span></span>

<span data-ttu-id="5897d-366">Todos los operadores binarios son asociativos a la derecha, excepto en el caso de `^`.</span><span class="sxs-lookup"><span data-stu-id="5897d-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="5897d-367">Los corchetes, `[` y `]`para la segmentación e indización de matrices, se enlazan antes que cualquier operador.</span><span class="sxs-lookup"><span data-stu-id="5897d-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="5897d-368">Los funcrs `Adjoint` y `Controlled` enlazan después de la indización de matriz, pero antes de todos los demás operadores.</span><span class="sxs-lookup"><span data-stu-id="5897d-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="5897d-369">Los paréntesis para la invocación de la operación y la función también se enlazan antes que cualquier operador, pero después de la indización de matriz y los funcdores.</span><span class="sxs-lookup"><span data-stu-id="5897d-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="5897d-370">Operadores en orden de prioridad, de mayor a menor:</span><span class="sxs-lookup"><span data-stu-id="5897d-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="5897d-371">Operator</span><span class="sxs-lookup"><span data-stu-id="5897d-371">Operator</span></span> | <span data-ttu-id="5897d-372">Polaridad</span><span class="sxs-lookup"><span data-stu-id="5897d-372">Arity</span></span> | <span data-ttu-id="5897d-373">Descripción</span><span class="sxs-lookup"><span data-stu-id="5897d-373">Description</span></span> | <span data-ttu-id="5897d-374">Tipos de operando</span><span class="sxs-lookup"><span data-stu-id="5897d-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="5897d-375">`!` finales</span><span class="sxs-lookup"><span data-stu-id="5897d-375">trailing `!`</span></span> | <span data-ttu-id="5897d-376">Unario</span><span class="sxs-lookup"><span data-stu-id="5897d-376">Unary</span></span> | <span data-ttu-id="5897d-377">Desencapsulado</span><span class="sxs-lookup"><span data-stu-id="5897d-377">Unwrap</span></span> | <span data-ttu-id="5897d-378">Cualquier tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="5897d-378">Any user-defined type</span></span>
 <span data-ttu-id="5897d-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="5897d-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="5897d-380">Unario</span><span class="sxs-lookup"><span data-stu-id="5897d-380">Unary</span></span> | <span data-ttu-id="5897d-381">Negativo numérico, complemento bit a bit, negación lógica</span><span class="sxs-lookup"><span data-stu-id="5897d-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="5897d-382">`Int`, `BigInt` o `Double` para `-`, `Int` o `BigInt` para `~~~``Bool` `not`</span><span class="sxs-lookup"><span data-stu-id="5897d-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="5897d-383">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-383">Binary</span></span> | <span data-ttu-id="5897d-384">Potencia de entero</span><span class="sxs-lookup"><span data-stu-id="5897d-384">Integer power</span></span> | <span data-ttu-id="5897d-385">`Int` o `BigInt` para la base `Int` para el exponente</span><span class="sxs-lookup"><span data-stu-id="5897d-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="5897d-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="5897d-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="5897d-387">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-387">Binary</span></span> | <span data-ttu-id="5897d-388">División, multiplicación, módulo de entero</span><span class="sxs-lookup"><span data-stu-id="5897d-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="5897d-389">`Int`, `BigInt` o `Double` para `/` y `*`, `Int` o `BigInt` para `%`</span><span class="sxs-lookup"><span data-stu-id="5897d-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="5897d-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="5897d-390">`+`, `-`</span></span> | <span data-ttu-id="5897d-391">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-391">Binary</span></span> | <span data-ttu-id="5897d-392">Suma, concatenación de cadenas y matrices, resta</span><span class="sxs-lookup"><span data-stu-id="5897d-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="5897d-393">`Int`, `BigInt` o `Double`, además `String` o cualquier tipo de matriz para `+`</span><span class="sxs-lookup"><span data-stu-id="5897d-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="5897d-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="5897d-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="5897d-395">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-395">Binary</span></span> | <span data-ttu-id="5897d-396">Desplazamiento a la izquierda, desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="5897d-396">Left shift, right shift</span></span> | <span data-ttu-id="5897d-397">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5897d-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="5897d-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="5897d-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="5897d-399">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-399">Binary</span></span> | <span data-ttu-id="5897d-400">Comparaciones menor que, menor o igual que, mayor que, mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="5897d-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="5897d-401">`Int`, `BigInt` o `Double`</span><span class="sxs-lookup"><span data-stu-id="5897d-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="5897d-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="5897d-402">`==`, `!=`</span></span> | <span data-ttu-id="5897d-403">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-403">Binary</span></span> | <span data-ttu-id="5897d-404">comparaciones iguales y no iguales</span><span class="sxs-lookup"><span data-stu-id="5897d-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="5897d-405">cualquier tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="5897d-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="5897d-406">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-406">Binary</span></span> | <span data-ttu-id="5897d-407">AND bit a bit</span><span class="sxs-lookup"><span data-stu-id="5897d-407">Bitwise AND</span></span> | <span data-ttu-id="5897d-408">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5897d-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="5897d-409">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-409">Binary</span></span> | <span data-ttu-id="5897d-410">XOR bit a bit</span><span class="sxs-lookup"><span data-stu-id="5897d-410">Bitwise XOR</span></span> | <span data-ttu-id="5897d-411">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5897d-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="5897d-412">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-412">Binary</span></span> | <span data-ttu-id="5897d-413">OR bit a bit</span><span class="sxs-lookup"><span data-stu-id="5897d-413">Bitwise OR</span></span> | <span data-ttu-id="5897d-414">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5897d-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="5897d-415">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-415">Binary</span></span> | <span data-ttu-id="5897d-416">Y lógico</span><span class="sxs-lookup"><span data-stu-id="5897d-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="5897d-417">Binary</span><span class="sxs-lookup"><span data-stu-id="5897d-417">Binary</span></span> | <span data-ttu-id="5897d-418">O lógico</span><span class="sxs-lookup"><span data-stu-id="5897d-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="5897d-419">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="5897d-419">Binary/Ternary</span></span> | <span data-ttu-id="5897d-420">Range (operador)</span><span class="sxs-lookup"><span data-stu-id="5897d-420">Range operator</span></span> | `Int`
 <span data-ttu-id="5897d-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="5897d-421">`?` `|`</span></span> | <span data-ttu-id="5897d-422">Ternario</span><span class="sxs-lookup"><span data-stu-id="5897d-422">Ternary</span></span> | <span data-ttu-id="5897d-423">Condicional</span><span class="sxs-lookup"><span data-stu-id="5897d-423">Conditional</span></span> | <span data-ttu-id="5897d-424">`Bool` para el lado izquierdo</span><span class="sxs-lookup"><span data-stu-id="5897d-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="5897d-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="5897d-425">`w/` `<-`</span></span> | <span data-ttu-id="5897d-426">Ternario</span><span class="sxs-lookup"><span data-stu-id="5897d-426">Ternary</span></span> | <span data-ttu-id="5897d-427">Copiar y actualizar</span><span class="sxs-lookup"><span data-stu-id="5897d-427">Copy-and-update</span></span> | <span data-ttu-id="5897d-428">vea [expresiones de copia y actualización](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="5897d-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
