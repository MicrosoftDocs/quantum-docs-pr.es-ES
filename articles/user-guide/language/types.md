---
title: 'Tipos de :::no-loc(Q#):::'
description: 'Obtenga información sobre los diferentes tipos que se usan en el :::no-loc(Q#)::: lenguaje de programación.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691610"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="3c35f-103">Tipos de :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="3c35f-103">Types in :::no-loc(Q#):::</span></span>

<span data-ttu-id="3c35f-104">En este artículo se describe el :::no-loc(Q#)::: modelo de tipo y la sintaxis para especificar y trabajar con tipos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-104">This article describes the :::no-loc(Q#)::: type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="3c35f-105">Para obtener más información sobre cómo crear y operar en expresiones de estos tipos, vea [expresiones de tipo](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="3c35f-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="3c35f-106">Tenemos en cuenta que :::no-loc(Q#)::: es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los :::no-loc(Q#)::: programas en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3c35f-106">We note that :::no-loc(Q#)::: is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about :::no-loc(Q#)::: programs at compile time.</span></span>
<span data-ttu-id="3c35f-107">Para proporcionar las garantías más fuertes posibles, las conversiones entre los tipos de :::no-loc(Q#)::: deben ser explícitas mediante llamadas a funciones que expresan esa conversión.</span><span class="sxs-lookup"><span data-stu-id="3c35f-107">To provide the strongest guarantees possible, conversions between types in :::no-loc(Q#)::: must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="3c35f-108">:::no-loc(Q#)::: proporciona una gran variedad de funciones como parte del espacio de <xref:Microsoft.Quantum.Convert> nombres.</span><span class="sxs-lookup"><span data-stu-id="3c35f-108">:::no-loc(Q#)::: provides a variety of such functions as a part of the <xref:Microsoft.Quantum.Convert> namespace.</span></span>
<span data-ttu-id="3c35f-109">Las reversiones a tipos compatibles, por otro lado, se producen implícitamente.</span><span class="sxs-lookup"><span data-stu-id="3c35f-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="3c35f-110">:::no-loc(Q#)::: proporciona ambos tipos primitivos, que se utilizan directamente, y diversas maneras de generar nuevos tipos a partir de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-110">:::no-loc(Q#)::: provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="3c35f-111">En el resto de este artículo se describe cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="3c35f-112">Tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="3c35f-112">Primitive Types</span></span>

<span data-ttu-id="3c35f-113">El :::no-loc(Q#)::: lenguaje proporciona los siguientes *tipos primitivos* , que se pueden usar directamente en los :::no-loc(Q#)::: programas.</span><span class="sxs-lookup"><span data-stu-id="3c35f-113">The :::no-loc(Q#)::: language provides the following *primitive types* , all of which you can use directly in :::no-loc(Q#)::: programs.</span></span> <span data-ttu-id="3c35f-114">También puede usar estos tipos primitivos para construir nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="3c35f-115">El `Int` tipo representa un entero con signo de 64 bits, por ejemplo, `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="3c35f-116">El `BigInt` tipo representa un entero con signo de tamaño arbitrario, por ejemplo, `2L` , `107L` , `-5L` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="3c35f-117">Este tipo se basa en .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="3c35f-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="3c35f-118">.</span><span class="sxs-lookup"><span data-stu-id="3c35f-118">type.</span></span>

- <span data-ttu-id="3c35f-119">El `Double` tipo representa un número de punto flotante de precisión doble, por ejemplo, `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="3c35f-120">El `Bool` tipo representa un valor booleano de `true` o `false` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="3c35f-121">El `Range` tipo representa una secuencia de enteros, indicada por `start..step..stop` , donde la indicación del paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="3c35f-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="3c35f-122">Por ejemplo, `start .. stop` corresponde a `start..1..stop` y `1..2..7` representa la secuencia $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="3c35f-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="3c35f-123">El `String` tipo es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.</span><span class="sxs-lookup"><span data-stu-id="3c35f-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="3c35f-124">Use el `string` tipo para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3c35f-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="3c35f-125">El `Unit` tipo solo puede tener un valor, `()` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="3c35f-126">Utilice este tipo para indicar que una :::no-loc(Q#)::: función u operación no devuelve información.</span><span class="sxs-lookup"><span data-stu-id="3c35f-126">Use this type to indicate that a :::no-loc(Q#)::: function or operation returns no information.</span></span> 
- <span data-ttu-id="3c35f-127">El `Qubit` tipo representa un bit de Quantum o qubit.</span><span class="sxs-lookup"><span data-stu-id="3c35f-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="3c35f-128">`Qubit`los s son opacos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="3c35f-129">La única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).</span><span class="sxs-lookup"><span data-stu-id="3c35f-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="3c35f-130">En última instancia, se implementan acciones en `Qubit` s llamando a instrucciones intrínsecas en un procesador Quantum (o un simulador Quantum).</span><span class="sxs-lookup"><span data-stu-id="3c35f-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="3c35f-131">El `Pauli` tipo representa uno de los cuatro operadores de Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="3c35f-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="3c35f-132">Utilice este tipo para indicar la operación base para los giros y especificar el objeto observable que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="3c35f-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="3c35f-133">Es un tipo enumerado que tiene cuatro valores posibles: `PauliI` , `PauliX` , `PauliY` y `PauliZ` , que son constantes de tipo `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="3c35f-134">El `Result` tipo representa el resultado de una medida.</span><span class="sxs-lookup"><span data-stu-id="3c35f-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="3c35f-135">Es un tipo enumerado con dos valores posibles: `One` y `Zero` , que son constantes de tipo `Result` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="3c35f-136">`Zero` indica que se ha medido + 1 eigenvalue; `One` indica que se midió-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="3c35f-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="3c35f-137">Las constantes, `true` , `false` `PauliI` , `PauliX` , `PauliY` , `PauliZ` , `One` y `Zero` son símbolos reservados en :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="3c35f-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in :::no-loc(Q#):::.</span></span>

## <a name="array-types"></a><span data-ttu-id="3c35f-138">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="3c35f-138">Array Types</span></span>

* <span data-ttu-id="3c35f-139">Para cualquier :::no-loc(Q#)::: tipo válido, existe un tipo que representa una matriz de valores de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3c35f-139">For any valid :::no-loc(Q#)::: type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="3c35f-140">Por ejemplo, `Qubit[]` y `(Bool, Pauli)[]` representan matrices de `Qubit` valores y `(Bool, Pauli)` valores de tupla.</span><span class="sxs-lookup"><span data-stu-id="3c35f-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="3c35f-141">Una matriz de matrices también es válida.</span><span class="sxs-lookup"><span data-stu-id="3c35f-141">An array of arrays is also valid.</span></span> <span data-ttu-id="3c35f-142">Al expandir el ejemplo anterior, se denota una matriz de `(Bool, Pauli)` matrices `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="3c35f-143">En este ejemplo, `(Bool, Pauli)[][]` , representa una matriz de matrices potencialmente escalonada y no una matriz bidimensional rectangular.</span><span class="sxs-lookup"><span data-stu-id="3c35f-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="3c35f-144">:::no-loc(Q#)::: no es compatible con matrices multidimensionales rectangulares.</span><span class="sxs-lookup"><span data-stu-id="3c35f-144">:::no-loc(Q#)::: does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="3c35f-145">Un valor de matriz se puede escribir en :::no-loc(Q#)::: el código fuente mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-145">An array value can be written in :::no-loc(Q#)::: source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="3c35f-146">El tipo base común de todos los elementos de la matriz determina el tipo de un literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="3c35f-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="3c35f-147">Por lo tanto, la construcción de una matriz con elementos que no tienen un tipo base común produce un error.</span><span class="sxs-lookup"><span data-stu-id="3c35f-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="3c35f-148">Para obtener un ejemplo, consulte [matrices de llamadas](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="3c35f-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="3c35f-149">Una vez creados, no se pueden cambiar los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3c35f-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="3c35f-150">Para construir una matriz modificada, use [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) o [expresiones de copia y actualización](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="3c35f-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="3c35f-151">Como alternativa, se puede crear una matriz a partir de su tamaño mediante la `new` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="3c35f-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="3c35f-152">Utilice la función Core `Length` para obtener el número de elementos de una matriz como `Int` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="3c35f-153">Las matrices pueden ser de subíndice para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3c35f-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="3c35f-154">Los subíndices de las matrices tienen una base cero y deben ser de tipo `Int` o tipo `Range` :</span><span class="sxs-lookup"><span data-stu-id="3c35f-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="3c35f-155">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="3c35f-155">Tuple Types</span></span>

<span data-ttu-id="3c35f-156">Las tuplas son un concepto eficaz que se usa :::no-loc(Q#)::: para recopilar valores en un único valor, lo que facilita su paso.</span><span class="sxs-lookup"><span data-stu-id="3c35f-156">Tuples are a powerful concept used throughout :::no-loc(Q#)::: to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="3c35f-157">En concreto, mediante la notación de tupla, puede expresar que cada operación y invocable toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="3c35f-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="3c35f-158">Dado cero o más tipos diferentes `T0` , `T1` ,..., `Tn` , puede denotar un nuevo  *tipo de tupla* como `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="3c35f-159">Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="3c35f-160">Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.</span><span class="sxs-lookup"><span data-stu-id="3c35f-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="3c35f-161">Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.</span><span class="sxs-lookup"><span data-stu-id="3c35f-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="3c35f-162">Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="3c35f-163">Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3c35f-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="3c35f-164">A partir de :::no-loc(Q#)::: 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor* de la tupla vacía.</span><span class="sxs-lookup"><span data-stu-id="3c35f-164">As of :::no-loc(Q#)::: 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="3c35f-165">Las instancias de tupla son inmutables.</span><span class="sxs-lookup"><span data-stu-id="3c35f-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="3c35f-166">:::no-loc(Q#)::: no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.</span><span class="sxs-lookup"><span data-stu-id="3c35f-166">:::no-loc(Q#)::: does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="3c35f-167">Equivalencia de tupla singleton</span><span class="sxs-lookup"><span data-stu-id="3c35f-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="3c35f-168">Es posible crear una tupla singleton (elemento único) `('T1)` , como `(5)` o `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="3c35f-169">Sin embargo, :::no-loc(Q#)::: trata una tupla singleton como equivalente a un valor del tipo delimitado.</span><span class="sxs-lookup"><span data-stu-id="3c35f-169">However, :::no-loc(Q#)::: treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="3c35f-170">Es decir, no hay ninguna diferencia entre `5` y `(5)` , o entre `5` y `(((5)))` , o entre `(5, (6))` y `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="3c35f-171">Es como válido escribir `(5)+3` como para escribir `5+3` ; ambas expresiones se evalúan como `8` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="3c35f-172">Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.</span><span class="sxs-lookup"><span data-stu-id="3c35f-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="3c35f-173">Dada cualquier expresión, esa misma expresión entre paréntesis es una expresión del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3c35f-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="3c35f-174">Por ejemplo, `(7)` es una expresión de tipo `Int` , `([1,2,3])` es una expresión de tipo `Int[]` y `((1,2))` es una expresión de tipo `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="3c35f-175">En concreto, esto significa que puede ver una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo que toma un solo argumento o devuelve un valor único.</span><span class="sxs-lookup"><span data-stu-id="3c35f-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="3c35f-176">Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_ .</span><span class="sxs-lookup"><span data-stu-id="3c35f-176">We refer to this property as _singleton tuple equivalence_ .</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="3c35f-177">Tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="3c35f-177">User-Defined Types</span></span>

<span data-ttu-id="3c35f-178">Una declaración de tipos definidos por el usuario se compone de la palabra clave `newtype` , seguida del nombre del tipo definido por el usuario, un `=` , una especificación de tipo válida y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="3c35f-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="3c35f-179">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c35f-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="3c35f-180">Cada :::no-loc(Q#)::: archivo de código fuente puede declarar cualquier número de tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-180">Each :::no-loc(Q#)::: source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="3c35f-181">Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.</span><span class="sxs-lookup"><span data-stu-id="3c35f-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="3c35f-182">Los tipos definidos por el usuario son distintos, aunque los tipos base sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="3c35f-183">En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="3c35f-184">Elementos con nombre frente a elementos anónimos</span><span class="sxs-lookup"><span data-stu-id="3c35f-184">Named vs. anonymous items</span></span>

<span data-ttu-id="3c35f-185">Un :::no-loc(Q#)::: archivo puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.</span><span class="sxs-lookup"><span data-stu-id="3c35f-185">A :::no-loc(Q#)::: file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="3c35f-186">Para cualquier tipo `T` de tupla, puede declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la `newtype` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3c35f-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="3c35f-187">En el @"microsoft.quantum.math" espacio de nombres, por ejemplo, los números complejos se definen como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="3c35f-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="3c35f-188">Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="3c35f-189">Además de los elementos anónimos, los tipos definidos por el usuario también admiten *elementos con nombre* a partir de la :::no-loc(Q#)::: versión 0,7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3c35f-189">Aside from anonymous items, user-defined types also support *named items* as of :::no-loc(Q#)::: version 0.7 or higher.</span></span> <span data-ttu-id="3c35f-190">Por ejemplo, podría asignar un nombre a los elementos para `Real` el valor Double que representa la parte real de un número complejo y `Imag` para la parte imaginaria:</span><span class="sxs-lookup"><span data-stu-id="3c35f-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="3c35f-191">Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre.</span><span class="sxs-lookup"><span data-stu-id="3c35f-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="3c35f-192">Además, los elementos internos también se pueden denominar.</span><span class="sxs-lookup"><span data-stu-id="3c35f-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="3c35f-193">El tipo `Nested` , como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))` , del que solo se denomina el elemento de tipo `Int` , y todos los demás elementos son anónimos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="3c35f-194">Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del *operador de acceso* `::` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="3c35f-195">Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="3c35f-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="3c35f-196">Volviendo al ejemplo de `Complex` , también podría haber definido una representación de coordenadas polares como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="3c35f-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="3c35f-197">Aunque ambos `Complex` `ComplexPolar` tienen un tipo subyacente `(Double, Double)` , los dos tipos son totalmente incompatibles en, lo que :::no-loc(Q#)::: minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.</span><span class="sxs-lookup"><span data-stu-id="3c35f-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in :::no-loc(Q#):::, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="3c35f-198">Obtener acceso a elementos anónimos con el operador Unwrap</span><span class="sxs-lookup"><span data-stu-id="3c35f-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="3c35f-199">Para obtener acceso a los elementos anónimos, extraiga primero el valor ajustado mediante el operador postfijo `!` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="3c35f-200">Con el operador "Unwrap", `!` , puede extraer el valor contenido en un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="3c35f-201">El tipo de una expresión "Unwrap" es el tipo subyacente del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="3c35f-202">Un único operador Unwrap desencapsula un nivel de ajuste.</span><span class="sxs-lookup"><span data-stu-id="3c35f-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="3c35f-203">Use varios operadores Unwrap para tener acceso a un valor de ajuste de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="3c35f-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="3c35f-204">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c35f-204">For example:</span></span>

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

<span data-ttu-id="3c35f-205">Para obtener más detalles sobre el operador Unwrap, vea [expresiones de :::no-loc(Q#)::: tipo en ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="3c35f-205">For more details on the unwrap operator, see [Type Expressions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="3c35f-206">Crear valores de tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="3c35f-206">Creating values of user-defined types</span></span>

<span data-ttu-id="3c35f-207">Cree valores de un tipo definido por el usuario mediante una llamada al constructor de tipo correspondiente:</span><span class="sxs-lookup"><span data-stu-id="3c35f-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="3c35f-208">Como alternativa, puede crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="3c35f-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="3c35f-209">Del mismo modo que con las matrices, las expresiones de copiar y actualizar copian todos los valores de los elementos de la expresión original, excepto los elementos con nombre especificados.</span><span class="sxs-lookup"><span data-stu-id="3c35f-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="3c35f-210">Para estas excepciones, los valores de estos elementos son los valores definidos en el lado derecho de la expresión.</span><span class="sxs-lookup"><span data-stu-id="3c35f-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="3c35f-211">Cualquier otra construcción de lenguaje que esté disponible para los elementos de matriz, por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existe también para los elementos con nombre de tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

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

* <span data-ttu-id="3c35f-212">Puede usar tipos definidos por el usuario en cualquier lugar en el que use cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="3c35f-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="3c35f-213">En concreto, es posible definir una matriz de un tipo definido por el usuario y incluir un tipo definido por el usuario como elemento de un tipo de tupla.</span><span class="sxs-lookup"><span data-stu-id="3c35f-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="3c35f-214">No es posible crear estructuras de tipo recursivas.</span><span class="sxs-lookup"><span data-stu-id="3c35f-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="3c35f-215">Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c35f-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="3c35f-216">En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no es válido:</span><span class="sxs-lookup"><span data-stu-id="3c35f-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="3c35f-217">Tipos de operación y función</span><span class="sxs-lookup"><span data-stu-id="3c35f-217">Operation and Function Types</span></span>

<span data-ttu-id="3c35f-218">Dados los tipos `'Tinput` y `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="3c35f-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="3c35f-219">`('Tinput => 'Tresult)` es el tipo básico de cualquier *operación* , por ejemplo `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-219">`('Tinput => 'Tresult)` is the basic type for any *operation* , for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="3c35f-220">`('Tinput -> 'Tresult)` es el tipo básico de cualquier *función* , por ejemplo `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-220">`('Tinput -> 'Tresult)` is the basic type for any *function* , for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="3c35f-221">Estos se denominan la *firma* de que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="3c35f-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="3c35f-222">Todas las :::no-loc(Q#)::: llamadas a aceptan un valor único como entrada y devuelven un valor único como salida.</span><span class="sxs-lookup"><span data-stu-id="3c35f-222">All :::no-loc(Q#)::: callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="3c35f-223">Puede usar tuplas para los valores de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="3c35f-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="3c35f-224">Llamadas que no tienen ningún resultado, devuelven `Unit` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="3c35f-225">Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.</span><span class="sxs-lookup"><span data-stu-id="3c35f-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="3c35f-226">Funciones</span><span class="sxs-lookup"><span data-stu-id="3c35f-226">Functors</span></span>

<span data-ttu-id="3c35f-227">Los tipos de *función* se especifican completamente mediante su firma.</span><span class="sxs-lookup"><span data-stu-id="3c35f-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="3c35f-228">Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="3c35f-229">*Las operaciones* tienen ciertas características adicionales que se expresan como parte del tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="3c35f-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="3c35f-230">Estas características incluyen información sobre los *inactivos* que admite la operación.</span><span class="sxs-lookup"><span data-stu-id="3c35f-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="3c35f-231">Por ejemplo, si la ejecución de la operación se basa en el estado de otros qubits, debe admitir el `Controlled` functor; si la operación tiene un inverso, debe admitir el `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="3c35f-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="3c35f-232">En este artículo solo se explica cómo los funcers modifican la firma de la operación.</span><span class="sxs-lookup"><span data-stu-id="3c35f-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="3c35f-233">Para obtener más información acerca de los funcrs y las operaciones, vea [operaciones y funciones en :::no-loc(Q#)::: ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="3c35f-233">For more details about functors and operations, see [Operations and Functions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="3c35f-234">Para requerir la compatibilidad con `Controlled` y/o `Adjoint` functor en un tipo de operación, debe agregar una anotación que indique las características correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3c35f-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="3c35f-235">La anotación `is Ctl` (por ejemplo, `(Qubit => Unit is Ctl)` ) indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="3c35f-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="3c35f-236">Es decir, su ejecución se basa en el estado de otro qubit o qubits.</span><span class="sxs-lookup"><span data-stu-id="3c35f-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="3c35f-237">Del mismo modo, la anotación `is Adj` indica que la operación tiene un uncontiguo, es decir, se puede "invertir" de modo que la aplicación de una operación sucesivamente y después su contigua a un estado deja el estado sin cambios.</span><span class="sxs-lookup"><span data-stu-id="3c35f-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="3c35f-238">Si desea exigir que una operación de ese tipo admita `Adjoint` y el `Controlled` functor, puede expresarlo como `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="3c35f-239">Por ejemplo, la operación Pauli integrada <xref:Microsoft.Quantum.Intrinsic.X> tiene el tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-239">For example, the built-in Pauli <xref:Microsoft.Quantum.Intrinsic.X> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="3c35f-240">Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.</span><span class="sxs-lookup"><span data-stu-id="3c35f-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="3c35f-241">Funciones y operaciones de Type-Parameterized</span><span class="sxs-lookup"><span data-stu-id="3c35f-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="3c35f-242">Los tipos a los que se puede llamar pueden contener *parámetros de tipo* .</span><span class="sxs-lookup"><span data-stu-id="3c35f-242">Callable types may contain *type parameters* .</span></span>
<span data-ttu-id="3c35f-243">Use un símbolo con una comilla simple como prefijo para indicar un parámetro de tipo; por ejemplo, `'A` es un parámetro de tipo válido.</span><span class="sxs-lookup"><span data-stu-id="3c35f-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="3c35f-244">Para obtener más información y detalles sobre cómo definir las llamadas a parámetros de tipo, vea [operaciones y funciones en :::no-loc(Q#)::: ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="3c35f-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="3c35f-245">Un parámetro de tipo puede aparecer más de una vez en una sola firma.</span><span class="sxs-lookup"><span data-stu-id="3c35f-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="3c35f-246">Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tiene la firma `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="3c35f-247">Del mismo modo, una función que devuelve la composición de dos operaciones tiene la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="3c35f-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="3c35f-248">Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3c35f-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="3c35f-249">:::no-loc(Q#)::: no proporciona un mecanismo para restringir los tipos posibles que un usuario puede sustituir para un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="3c35f-249">:::no-loc(Q#)::: does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c35f-250">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3c35f-250">Next steps</span></span>

<span data-ttu-id="3c35f-251">Ahora que ha visto todos los tipos que componen el :::no-loc(Q#)::: lenguaje, vea [expresiones de tipo :::no-loc(Q#)::: en](xref:microsoft.quantum.guide.expressions) para obtener información sobre cómo crear y manipular expresiones de estos diversos tipos.</span><span class="sxs-lookup"><span data-stu-id="3c35f-251">Now that you've seen all the types which comprise the :::no-loc(Q#)::: language, see [Type Expressions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
