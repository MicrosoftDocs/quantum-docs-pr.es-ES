---
title: Tipos en Q#
description: Obtenga información sobre los diferentes tipos que se usan en el lenguaje de programación de preguntas y respuestas.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609148"
---
# <a name="types-in-q"></a><span data-ttu-id="e07f5-103">Tipos en Q#</span><span class="sxs-lookup"><span data-stu-id="e07f5-103">Types in Q#</span></span>

<span data-ttu-id="e07f5-104">Esta página dispone del modelo de tipo Q # y describe la sintaxis para especificar y trabajar con tipos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="e07f5-105">La página siguiente, [expresiones de tipo](xref:microsoft.quantum.guide.expressions), detalla cómo crear y operar en expresiones de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="e07f5-106">Tenemos en cuenta que Q # es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los programas de Q # en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e07f5-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="e07f5-107">Con el fin de proporcionar las garantías más fuertes posibles, las conversiones entre los tipos en Q # deben ser explícitas mediante llamadas a funciones que expresan esa conversión.</span><span class="sxs-lookup"><span data-stu-id="e07f5-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="e07f5-108">Se proporcionan varias funciones como parte del <xref:microsoft.quantum.convert> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e07f5-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="e07f5-109">Las conversiones de tipos compatibles por otro lado se producen implícitamente.</span><span class="sxs-lookup"><span data-stu-id="e07f5-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="e07f5-110">Q # proporciona ambos tipos primitivos, que se pueden usar directamente, y varias maneras de generar nuevos tipos a partir de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="e07f5-111">En el resto de esta sección se describe cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="e07f5-112">Tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="e07f5-112">Primitive Types</span></span>

<span data-ttu-id="e07f5-113">El lenguaje Q # proporciona varios *tipos primitivos*, de los que se pueden construir otros tipos:</span><span class="sxs-lookup"><span data-stu-id="e07f5-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="e07f5-114">El `Int` tipo representa un entero con signo de 64 bits, por ejemplo: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="e07f5-115">El `BigInt` tipo representa un entero con signo de tamaño arbitrario, por ejemplo `2L` , `107L` , `-5L` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="e07f5-116">Este tipo se basa en .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="e07f5-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="e07f5-117">automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e07f5-117">type.</span></span>
- <span data-ttu-id="e07f5-118">El `Double` tipo representa un número de punto flotante de precisión doble, por ejemplo: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="e07f5-119">El `Bool` tipo representa un valor booleano que puede ser `true` o `false` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="e07f5-120">El `Range` tipo representa una secuencia de enteros, indicada por `start..step..stop` , donde la indicación del paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="e07f5-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="e07f5-121">Esto se `start .. stop` corresponde con `start..1..stop` y, por ejemplo, `1..2..7` representa la secuencia $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="e07f5-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="e07f5-122">El `String` tipo es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.</span><span class="sxs-lookup"><span data-stu-id="e07f5-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="e07f5-123">Este tipo se utiliza para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e07f5-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="e07f5-124">El `Unit` tipo es el tipo que solo permite un valor `()` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="e07f5-125">Este tipo se usa para indicar que la operación o la función Q # no devuelve ninguna información.</span><span class="sxs-lookup"><span data-stu-id="e07f5-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="e07f5-126">El `Qubit` tipo representa un bit de Quantum o qubit.</span><span class="sxs-lookup"><span data-stu-id="e07f5-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="e07f5-127">`Qubit`s son opacos para el usuario; la única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).</span><span class="sxs-lookup"><span data-stu-id="e07f5-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="e07f5-128">En última instancia, las acciones en `Qubit` s se implementan llamando a instrucciones intrínsecas en un procesador Quantum (o en una simulación de la misma).</span><span class="sxs-lookup"><span data-stu-id="e07f5-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="e07f5-129">El `Pauli` tipo representa uno de los cuatro operadores de Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="e07f5-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="e07f5-130">Este tipo se utiliza para denotar la operación base para los giros y para especificar el objeto observable que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="e07f5-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="e07f5-131">Se trata de un tipo enumerado que tiene cuatro valores posibles: `PauliI` , `PauliX` , `PauliY` y `PauliZ` , que son constantes de tipo `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="e07f5-132">El `Result` tipo representa el resultado de una medida.</span><span class="sxs-lookup"><span data-stu-id="e07f5-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="e07f5-133">Se trata de un tipo enumerado con dos valores posibles: `One` y `Zero` , que son constantes de tipo `Result` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="e07f5-134">`Zero`indica que se ha medido + 1 eigenvalue; `One`indica-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="e07f5-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="e07f5-135">Las constantes, `true` `false` , `PauliI` , `PauliX` , `PauliY` , `PauliZ` , `One` y `Zero` son símbolos reservados en Q #.</span><span class="sxs-lookup"><span data-stu-id="e07f5-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="e07f5-136">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="e07f5-136">Array Types</span></span>

<span data-ttu-id="e07f5-137">Dado cualquier tipo de Q # válido `'T` , existe un tipo que representa una matriz de valores de tipo `'T` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="e07f5-138">Este tipo de matriz se representa como `'T[]` ; por ejemplo, `Qubit[]` o `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="e07f5-139">Por ejemplo, se denota una colección de enteros `Int[]` , mientras que se denota una matriz de `(Bool, Pauli)` valores `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="e07f5-140">En el segundo ejemplo, tenga en cuenta que esto representa una matriz potencialmente escalonada de matrices, y no una matriz bidimensional rectangular.</span><span class="sxs-lookup"><span data-stu-id="e07f5-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="e07f5-141">Q # no proporciona compatibilidad con matrices multidimensionales rectangulares.</span><span class="sxs-lookup"><span data-stu-id="e07f5-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="e07f5-142">Un valor de matriz se puede escribir en el código fuente de Q # mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="e07f5-143">El tipo de un literal de matriz viene determinado por el tipo base común de todos los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e07f5-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="e07f5-144">Los elementos de una matriz no se pueden cambiar una vez creada la matriz.</span><span class="sxs-lookup"><span data-stu-id="e07f5-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="e07f5-145">Las [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) y/o las [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) se pueden usar para construir una matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="e07f5-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="e07f5-146">Como alternativa, se puede crear una matriz a partir de su tamaño mediante la `new` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="e07f5-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="e07f5-147">En cualquier caso, una vez construida una matriz, `Length` se puede utilizar la función principal para obtener el número de elementos como `Int` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="e07f5-148">Las matrices se pueden incluir entre corchetes, con los subíndices de tipo `Int` o tipo `Range` , para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e07f5-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="e07f5-149">Los subíndices de las matrices son de base cero:</span><span class="sxs-lookup"><span data-stu-id="e07f5-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="e07f5-150">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="e07f5-150">Tuple Types</span></span>

<span data-ttu-id="e07f5-151">Dado cero o más tipos diferentes `T0` , `T1` ,..., `Tn` , podemos denotar un nuevo *tipo de tupla* como `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="e07f5-152">Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="e07f5-153">Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.</span><span class="sxs-lookup"><span data-stu-id="e07f5-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="e07f5-154">Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.</span><span class="sxs-lookup"><span data-stu-id="e07f5-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="e07f5-155">Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="e07f5-156">Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas, etc.</span><span class="sxs-lookup"><span data-stu-id="e07f5-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="e07f5-157">A partir de Q # 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor*de tupla vacío.</span><span class="sxs-lookup"><span data-stu-id="e07f5-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="e07f5-158">Las instancias de tupla son inmutables.</span><span class="sxs-lookup"><span data-stu-id="e07f5-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="e07f5-159">Q # no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.</span><span class="sxs-lookup"><span data-stu-id="e07f5-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="e07f5-160">Las tuplas son un concepto eficaz que se usa en Q # para recopilar valores en un único valor, lo que facilita su paso.</span><span class="sxs-lookup"><span data-stu-id="e07f5-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="e07f5-161">En concreto, mediante la notación de tupla, podemos expresar que cada operación y a la que se puede llamar toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="e07f5-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="e07f5-162">Equivalencia de tupla singleton</span><span class="sxs-lookup"><span data-stu-id="e07f5-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="e07f5-163">Es posible crear una tupla singleton (elemento único), `('T1)` , como `(5)` o `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="e07f5-164">Sin embargo, Q # trata una tupla singleton como totalmente equivalente a un valor del tipo delimitado.</span><span class="sxs-lookup"><span data-stu-id="e07f5-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="e07f5-165">Es decir, no hay ninguna diferencia entre `5` y `(5)` , o entre `5` y `(((5)))` , o entre `(5, (6))` y `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="e07f5-166">Es como válido escribir `(5)+3` como para escribir `5+3` y ambas expresiones se evaluarán como `8` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="e07f5-167">Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.</span><span class="sxs-lookup"><span data-stu-id="e07f5-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="e07f5-168">Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="e07f5-169">Por ejemplo, `(7)` es una expresión `Int` , `([1,2,3])` es una expresión de tipo matriz de `Int` s y `((1,2))` es una expresión con tipo `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="e07f5-170">En concreto, esto significa que una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo se puede considerar como tomar un único argumento o devolver un valor único.</span><span class="sxs-lookup"><span data-stu-id="e07f5-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="e07f5-171">Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_.</span><span class="sxs-lookup"><span data-stu-id="e07f5-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="e07f5-172">Tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e07f5-172">User-Defined Types</span></span>

<span data-ttu-id="e07f5-173">Una declaración de tipos definidos por el usuario se compone de la palabra clave `newtype` , seguida del nombre del tipo definido por el usuario, un `=` , una especificación de tipo válida y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="e07f5-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="e07f5-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e07f5-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="e07f5-175">Cada archivo de código fuente de Q # puede declarar cualquier número de tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e07f5-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="e07f5-176">Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.</span><span class="sxs-lookup"><span data-stu-id="e07f5-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="e07f5-177">Los tipos definidos por el usuario son distintos aunque los tipos base sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="e07f5-178">En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="e07f5-179">Elementos con nombre frente a elementos anónimos</span><span class="sxs-lookup"><span data-stu-id="e07f5-179">Named vs. anonymous items</span></span>

<span data-ttu-id="e07f5-180">Un archivo de preguntas # puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.</span><span class="sxs-lookup"><span data-stu-id="e07f5-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="e07f5-181">Para cualquier tipo `T` de tupla, se puede declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la `newtype` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e07f5-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="e07f5-182">En el @"microsoft.quantum.math" espacio de nombres, por ejemplo, los números complejos se definen como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="e07f5-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="e07f5-183">Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="e07f5-184">Además de los elementos anónimos, los tipos definidos por el usuario también admiten *elementos con nombre* a partir de la versión 0,7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e07f5-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="e07f5-185">Por ejemplo, podríamos haber llamado a items `Re` para el Double que representa la parte real de un número complejo y `Im` para la parte imaginaria:</span><span class="sxs-lookup"><span data-stu-id="e07f5-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="e07f5-186">Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre.</span><span class="sxs-lookup"><span data-stu-id="e07f5-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="e07f5-187">Además, los elementos internos también se pueden denominar.</span><span class="sxs-lookup"><span data-stu-id="e07f5-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="e07f5-188">El tipo `Nested` tal y como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))` , del que solo se denomina el elemento de tipo `Int` y todos los demás elementos son anónimos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="e07f5-189">Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del *operador de acceso* `::` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="e07f5-190">Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="e07f5-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="e07f5-191">Volviendo al ejemplo de `Complex` , también podría haber definido coordenadas polares 2D como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="e07f5-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="e07f5-192">Aunque ambos `Complex` `Polar` tienen un tipo subyacente `(Double, Double)` , los dos tipos son totalmente incompatibles en Q #, lo que minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e07f5-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="e07f5-193">De esta manera, los tipos definidos por el usuario tienen un rol similar como registros en F #, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="e07f5-194">Obtener acceso a elementos anónimos con el operador Unwrap</span><span class="sxs-lookup"><span data-stu-id="e07f5-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="e07f5-195">Para tener acceso a los elementos anónimos por otro lado, el valor ajustado primero debe extraerse mediante el operador postfijo `!` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="e07f5-196">El operador "Unwrap", `!` , permite extraer el valor contenido en un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e07f5-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="e07f5-197">El tipo de una expresión "Unwrap" es el tipo subyacente del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e07f5-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="e07f5-198">El operador Unwrap desencapsula exactamente una capa de ajuste.</span><span class="sxs-lookup"><span data-stu-id="e07f5-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="e07f5-199">Se pueden usar varios operadores Unwrap para tener acceso a un valor de ajuste de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="e07f5-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="e07f5-200">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e07f5-200">For instance:</span></span>

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

<span data-ttu-id="e07f5-201">Puede encontrar más detalles sobre el operador Unwrap en [expresiones de tipo en Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="e07f5-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="e07f5-202">Crear valores de tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e07f5-202">Creating values of user-defined types</span></span>

<span data-ttu-id="e07f5-203">Los valores de un tipo definido por el usuario se pueden crear llamando al constructor de tipo correspondiente:</span><span class="sxs-lookup"><span data-stu-id="e07f5-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="e07f5-204">Como alternativa, se pueden crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="e07f5-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="e07f5-205">Al igual que en el caso de las matrices, estas expresiones copian todos los valores de los elementos de la expresión original, con la excepción de los elementos con nombre especificados.</span><span class="sxs-lookup"><span data-stu-id="e07f5-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="e07f5-206">Estos valores se establecen en los que se definen en el lado derecho de la expresión.</span><span class="sxs-lookup"><span data-stu-id="e07f5-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="e07f5-207">Cualquier otra construcción de lenguaje, como por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), que están disponibles para los elementos de matriz existen también para los elementos con nombre en los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e07f5-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="e07f5-208">Los tipos definidos por el usuario se pueden usar en cualquier otro tipo que se pueda usar.</span><span class="sxs-lookup"><span data-stu-id="e07f5-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="e07f5-209">En concreto, es posible definir una matriz de un tipo definido por el usuario y incluir un tipo definido por el usuario como elemento de un tipo de tupla.</span><span class="sxs-lookup"><span data-stu-id="e07f5-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="e07f5-210">Nota no es posible crear estructuras de tipo recursivas.</span><span class="sxs-lookup"><span data-stu-id="e07f5-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="e07f5-211">Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e07f5-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="e07f5-212">En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no sería válido:</span><span class="sxs-lookup"><span data-stu-id="e07f5-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="e07f5-213">Tipos de operación y función</span><span class="sxs-lookup"><span data-stu-id="e07f5-213">Operation and Function Types</span></span>

<span data-ttu-id="e07f5-214">El tipo básico de cualquier que se pueda llamar se escribe como `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)` , donde `'Tinput` y `'Tresult` son tipos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="e07f5-215">Estos se denominan la *firma* de que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="e07f5-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="e07f5-216">Todas las llamadas a Q # pueden tomar un valor único como entrada y devolver un valor único como salida.</span><span class="sxs-lookup"><span data-stu-id="e07f5-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="e07f5-217">Los valores de entrada y salida pueden ser tuplas.</span><span class="sxs-lookup"><span data-stu-id="e07f5-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="e07f5-218">Se puede llamar a que no se devuelve ningún resultado `Unit` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="e07f5-219">Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.</span><span class="sxs-lookup"><span data-stu-id="e07f5-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="e07f5-220">El primer formulario, con `=>` , se utiliza para las operaciones; el segundo formulario, con `->` , para las funciones.</span><span class="sxs-lookup"><span data-stu-id="e07f5-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="e07f5-221">Por ejemplo, `((Qubit, Pauli) => Result)` representa la firma de una posible operación de medición de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="e07f5-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="e07f5-222">Los tipos de *función* se especifican completamente mediante su firma.</span><span class="sxs-lookup"><span data-stu-id="e07f5-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="e07f5-223">Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="e07f5-224">*Las operaciones*---pero no las funciones---tienen ciertas características adicionales que se expresan como parte del tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="e07f5-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="e07f5-225">Estas características incluyen información *sobre los elementos que admite* la operación.</span><span class="sxs-lookup"><span data-stu-id="e07f5-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="e07f5-226">Por ejemplo, si la ejecución de la operación se puede condicionar en el estado de otros qubits, debe admitir el `Controlled` functor; si la operación tiene un inverso, debe admitir el `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="e07f5-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="e07f5-227">Los funcdores y las operaciones se describen en detalle en [operaciones y funciones en Q #](xref:microsoft.quantum.guide.operationsfunctions), pero aquí simplemente se describe cómo modifica la firma de la operación.</span><span class="sxs-lookup"><span data-stu-id="e07f5-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="e07f5-228">Para requerir la compatibilidad con `Controlled` y/o `Adjoint` functor en un tipo de operación, es necesario agregar una anotación que indique las características correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e07f5-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="e07f5-229">Una anotación `is Ctl` (por ejemplo `(Qubit => Unit is Ctl)` ,) indica que la operación es controlable---es decir, su ejecución se condiciona en el estado de otro qubit o qubits.</span><span class="sxs-lookup"><span data-stu-id="e07f5-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="e07f5-230">Del mismo modo, `is Adj` indica que la operación tiene un tipo contiguo, o simplemente, se puede "invertir" de modo que la aplicación sucesiva de una operación y, a continuación, su unjoin a un estado deja el estado sin cambios.</span><span class="sxs-lookup"><span data-stu-id="e07f5-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="e07f5-231">Si queremos requerir que una operación de ese tipo admita el `Adjoint` y el `Controlled` functor, podemos expresar esto como `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="e07f5-232">Por ejemplo, la operación Pauli integrada <xref:microsoft.quantum.intrinsic.x> tiene el tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="e07f5-233">Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.</span><span class="sxs-lookup"><span data-stu-id="e07f5-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="e07f5-234">Operaciones y funciones con parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e07f5-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="e07f5-235">Los tipos a los que se puede llamar pueden contener parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="e07f5-236">Los parámetros de tipo se indican mediante un símbolo precedido por una comilla simple; por ejemplo, `'A` es un parámetro de tipo válido.</span><span class="sxs-lookup"><span data-stu-id="e07f5-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="e07f5-237">En las [operaciones y funciones de la página de preguntas y respuestas](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , se proporcionan detalles sobre cómo definir llamadas parametrizadas con parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="e07f5-238">Un parámetro de tipo puede aparecer más de una vez en una sola firma.</span><span class="sxs-lookup"><span data-stu-id="e07f5-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="e07f5-239">Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tendría la firma `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="e07f5-240">Del mismo modo, una función que devuelve la composición de dos operaciones podría tener la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="e07f5-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="e07f5-241">Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="e07f5-242">Q # no proporciona un mecanismo para restringir los tipos posibles que se pueden sustituir por un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f5-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="e07f5-243">¿Qué debe hacer a continuación?</span><span class="sxs-lookup"><span data-stu-id="e07f5-243">What's Next?</span></span>
<span data-ttu-id="e07f5-244">Ahora que ha visto todos los tipos que componen el lenguaje de preguntas y respuestas, puede ver las [expresiones de tipo en q #](xref:microsoft.quantum.guide.expressions) para ver cómo crear y manipular expresiones de estos diversos tipos.</span><span class="sxs-lookup"><span data-stu-id="e07f5-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


