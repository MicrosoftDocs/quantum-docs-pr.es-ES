---
title: 'Tipos de datos de Q #'
description: Obtenga información sobre los diferentes tipos que se usan en el lenguaje de programación de preguntas y respuestas, incluidos tipos integrados, matrices, tuplas, operaciones, funciones y tipos definidos por el usuario.
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904662"
---
# <a name="the-type-model"></a><span data-ttu-id="16528-103">Modelo de tipo</span><span class="sxs-lookup"><span data-stu-id="16528-103">The Type Model</span></span>

<span data-ttu-id="16528-104">En esta sección se presenta el modelo de tipo Q # y se describe la sintaxis para especificar y trabajar con tipos.</span><span class="sxs-lookup"><span data-stu-id="16528-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="16528-105">Tenemos en cuenta que Q # es un lenguaje *fuertemente tipado* , de modo que el uso meticuloso de estos tipos puede ayudar al compilador a proporcionar garantías sólidas sobre los programas de Q # en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="16528-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="16528-106">Con el fin de proporcionar las garantías más fuertes posibles, las conversiones entre los tipos en Q # deben ser explícitas mediante llamadas a funciones que expresan esa conversión.</span><span class="sxs-lookup"><span data-stu-id="16528-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="16528-107">Se proporcionan varias funciones como parte del espacio de nombres <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="16528-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="16528-108">Las conversiones de tipos compatibles por otro lado se producen implícitamente.</span><span class="sxs-lookup"><span data-stu-id="16528-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="16528-109">Q # proporciona ambos tipos primitivos, que se pueden usar directamente, y varias maneras de generar nuevos tipos a partir de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="16528-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="16528-110">En el resto de esta sección se describe cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="16528-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="16528-111">Tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="16528-111">Primitive Types</span></span>

<span data-ttu-id="16528-112">El lenguaje Q # proporciona varios *tipos primitivos*, de los que se pueden construir otros tipos:</span><span class="sxs-lookup"><span data-stu-id="16528-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="16528-113">El tipo de `Int` representa un entero con signo de 64 bits, por ejemplo: `2`, `107``-5`.</span><span class="sxs-lookup"><span data-stu-id="16528-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="16528-114">El tipo de `BigInt` representa un entero con signo de tamaño arbitrario, por ejemplo, `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="16528-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="16528-115">Este tipo se basa en .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="16528-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="16528-116">automáticamente.</span><span class="sxs-lookup"><span data-stu-id="16528-116">type.</span></span>
- <span data-ttu-id="16528-117">El tipo de `Double` representa un número de punto flotante de precisión doble, por ejemplo: `0.0`, `-1.3``4e-7`.</span><span class="sxs-lookup"><span data-stu-id="16528-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="16528-118">El tipo de `Bool` representa un valor booleano que puede ser `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="16528-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="16528-119">El tipo de `Qubit` representa un bit de Quantum o qubit.</span><span class="sxs-lookup"><span data-stu-id="16528-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="16528-120">`Qubit`s son opacas para el usuario; la única operación posible con ellos, aparte de pasarlos a otra operación, es comprobar la identidad (igualdad).</span><span class="sxs-lookup"><span data-stu-id="16528-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="16528-121">En última instancia, las acciones en `Qubit`s se implementan llamando a instrucciones intrínsecas en un procesador Quantum (o en una simulación de la misma).</span><span class="sxs-lookup"><span data-stu-id="16528-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="16528-122">El tipo de `Pauli` representa uno de los cuatro operadores de Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="16528-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="16528-123">Este tipo se utiliza para denotar la operación base para los giros y para especificar el objeto observable que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="16528-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="16528-124">Se trata de un tipo enumerado que tiene cuatro valores posibles: `PauliI`, `PauliX`, `PauliY`y `PauliZ`, que son constantes de tipo `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="16528-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="16528-125">El tipo de `Result` representa el resultado de una medida.</span><span class="sxs-lookup"><span data-stu-id="16528-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="16528-126">Se trata de un tipo enumerado con dos valores posibles: `One` y `Zero`, que son constantes de tipo `Result`.</span><span class="sxs-lookup"><span data-stu-id="16528-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="16528-127">`Zero` indica que se midió + 1 eigenvalue; `One` indica-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="16528-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="16528-128">El tipo de `Range` representa una secuencia de enteros, indicada por `start..step..stop`, donde la indicación del paso es opciones.</span><span class="sxs-lookup"><span data-stu-id="16528-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="16528-129">Es decir, `start .. stop` corresponde a `start..1..stop`y, por ejemplo, `1..2..7` representa la secuencia $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="16528-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="16528-130">El tipo de `String` es una secuencia de caracteres Unicode que es opaca para el usuario una vez creado.</span><span class="sxs-lookup"><span data-stu-id="16528-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="16528-131">Este tipo se utiliza para notificar mensajes a un host clásico en caso de un error o un evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="16528-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="16528-132">El tipo de `Unit` es el tipo que solo permite un `()`de valor.</span><span class="sxs-lookup"><span data-stu-id="16528-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="16528-133">Este tipo se usa para indicar que la operación o la función Q # no devuelve ninguna información.</span><span class="sxs-lookup"><span data-stu-id="16528-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="16528-134">Las constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`y `Zero` son símbolos reservados en Q #.</span><span class="sxs-lookup"><span data-stu-id="16528-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="16528-135">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="16528-135">Array Types</span></span>

<span data-ttu-id="16528-136">Dado cualquier `'T`válido de Q # type, existe un tipo que representa una matriz de valores de tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="16528-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="16528-137">Este tipo de matriz se representa como `'T[]`; por ejemplo, `Qubit[]` o `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="16528-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="16528-138">Por ejemplo, una colección de enteros se denota `Int[]`, mientras que una matriz de matrices de valores de `(Bool, Pauli)` se indica `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="16528-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="16528-139">En el segundo ejemplo, tenga en cuenta que esto representa una matriz potencialmente escalonada de matrices, y no una matriz bidimensional rectangular.</span><span class="sxs-lookup"><span data-stu-id="16528-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="16528-140">Q # no proporciona compatibilidad con matrices multidimensionales rectangulares.</span><span class="sxs-lookup"><span data-stu-id="16528-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="16528-141">Un valor de matriz se puede escribir en el código fuente de Q # mediante el uso de corchetes alrededor de los elementos de una matriz, como en `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="16528-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="16528-142">El tipo de un literal de matriz viene determinado por el tipo base común de todos los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="16528-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="16528-143">Los elementos de una matriz no se pueden cambiar una vez creada la matriz.</span><span class="sxs-lookup"><span data-stu-id="16528-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="16528-144">Las instrucciones Update-and-resign y/o las expresiones de copia y actualización se pueden usar para construir una matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="16528-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="16528-145">Como alternativa, se puede crear una matriz a partir de su tamaño mediante la palabra clave `new`:</span><span class="sxs-lookup"><span data-stu-id="16528-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="16528-146">En cualquier caso, una vez construida una matriz, se puede utilizar la función principal `Length` para obtener el número de elementos como `Int`.</span><span class="sxs-lookup"><span data-stu-id="16528-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="16528-147">Las matrices se pueden incluir en un subíndice con corchetes, con subíndices que tienen el tipo `Int` o el tipo `Range`, para obtener elementos individuales o matrices nuevas que contengan un subconjunto de los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="16528-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="16528-148">Los subíndices de las matrices son de base cero:</span><span class="sxs-lookup"><span data-stu-id="16528-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="16528-149">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="16528-149">Tuple Types</span></span>

<span data-ttu-id="16528-150">Dado cero o más tipos diferentes `T0`, `T1`,... `Tn`, podemos denotar un nuevo *tipo de tupla* como `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="16528-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="16528-151">Los tipos usados para construir un nuevo tipo de tupla pueden ser tuplas, como en `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="16528-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="16528-152">Sin embargo, este anidamiento siempre es finito, ya que los tipos de tupla no pueden incluirse en ningún caso.</span><span class="sxs-lookup"><span data-stu-id="16528-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="16528-153">Los valores del nuevo tipo de tupla son tuplas formadas por secuencias de valores de cada tipo de la tupla.</span><span class="sxs-lookup"><span data-stu-id="16528-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="16528-154">Por ejemplo, `(3, false)` es una tupla cuyo tipo es el tipo de tupla `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="16528-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="16528-155">Es posible crear matrices de tuplas, tuplas de matrices, tuplas de subtuplas, etc.</span><span class="sxs-lookup"><span data-stu-id="16528-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="16528-156">A partir de Q # 0,3, `Unit` es el nombre del *tipo* de la tupla vacía; `()` se usa para el *valor*de tupla vacío.</span><span class="sxs-lookup"><span data-stu-id="16528-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="16528-157">Las instancias de tupla son inmutables.</span><span class="sxs-lookup"><span data-stu-id="16528-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="16528-158">Q # no proporciona un mecanismo para cambiar el contenido de una tupla una vez creada.</span><span class="sxs-lookup"><span data-stu-id="16528-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="16528-159">Las tuplas son un concepto eficaz que se usa en Q # para recopilar valores en un único valor, lo que facilita su paso.</span><span class="sxs-lookup"><span data-stu-id="16528-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="16528-160">En concreto, mediante la notación de tupla, podemos expresar que cada operación y a la que se puede llamar toma exactamente una entrada y devuelve exactamente una salida.</span><span class="sxs-lookup"><span data-stu-id="16528-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="16528-161">Equivalencia de tupla singleton</span><span class="sxs-lookup"><span data-stu-id="16528-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="16528-162">Es posible crear una tupla singleton (elemento único), `('T1)`, como `(5)` o `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="16528-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="16528-163">Sin embargo, Q # trata una tupla singleton como totalmente equivalente a un valor del tipo delimitado.</span><span class="sxs-lookup"><span data-stu-id="16528-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="16528-164">Es decir, no hay ninguna diferencia entre `5` y `(5)`, o entre `5` y `(((5)))`, o entre `(5, (6))` y `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="16528-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="16528-165">Esta equivalencia se aplica a todos los propósitos, incluidas las asignaciones y las expresiones.</span><span class="sxs-lookup"><span data-stu-id="16528-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="16528-166">Solo es válido escribir `(5)+3` como para escribir `5+3`y ambas expresiones se evaluarán como `8`.</span><span class="sxs-lookup"><span data-stu-id="16528-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="16528-167">En concreto, esto significa que una operación o función cuyo tipo de tupla de entrada o de salida tiene un campo se puede considerar como tomar un único argumento o devolver un valor único.</span><span class="sxs-lookup"><span data-stu-id="16528-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="16528-168">Hacemos referencia a esta propiedad como _equivalencia de tupla singleton_.</span><span class="sxs-lookup"><span data-stu-id="16528-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="16528-169">Tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="16528-169">User-Defined Types</span></span>

<span data-ttu-id="16528-170">Un archivo de preguntas # puede definir un nuevo tipo con nombre que contenga un valor único de cualquier tipo válido.</span><span class="sxs-lookup"><span data-stu-id="16528-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="16528-171">Para cualquier tipo de tupla `T`, podemos declarar un nuevo tipo definido por el usuario que sea un subtipo de `T` con la instrucción `newtype`.</span><span class="sxs-lookup"><span data-stu-id="16528-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="16528-172">En el espacio de nombres @"microsoft.quantum.math", por ejemplo, los números complejos se definen como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="16528-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="16528-173">Esta instrucción crea un nuevo tipo con dos elementos anónimos de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="16528-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="16528-174">Además de los elementos anónimos, los tipos definidos por el usuario también admiten elementos con nombre a partir de la versión 0,7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="16528-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="16528-175">Por ejemplo, podríamos haber llamado a items `Re` para el Double que representa la parte real de un número complejo y `Im` para la parte imaginaria:</span><span class="sxs-lookup"><span data-stu-id="16528-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="16528-176">Asignar un nombre a un elemento de un tipo definido por el usuario no implica que todos los elementos deban tener nombre; se admite cualquier combinación de elementos con nombre y sin nombre.</span><span class="sxs-lookup"><span data-stu-id="16528-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="16528-177">Además, también se pueden asignar nombres a los elementos internos.</span><span class="sxs-lookup"><span data-stu-id="16528-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="16528-178">El tipo `Nested` tal y como se define a continuación, por ejemplo, tiene un tipo subyacente `(Double, (Int, String))`, de la que solo se asigna un nombre al elemento de tipo `Int` y todos los demás elementos son anónimos.</span><span class="sxs-lookup"><span data-stu-id="16528-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="16528-179">Los elementos con nombre tienen la ventaja de que se puede tener acceso a ellos directamente a través del operador de acceso `::`.</span><span class="sxs-lookup"><span data-stu-id="16528-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="16528-180">Para tener acceso a los elementos anónimos por otro lado, el valor ajustado primero debe extraerse mediante el operador postfijo `!`.</span><span class="sxs-lookup"><span data-stu-id="16528-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="16528-181">El operador "Unwrap", `!`, permite extraer el valor contenido en un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="16528-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="16528-182">El tipo de una expresión "Unwrap" es el tipo subyacente del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="16528-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="16528-183">El operador Unwrap desencapsula exactamente una capa de ajuste.</span><span class="sxs-lookup"><span data-stu-id="16528-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="16528-184">Se pueden usar varios operadores Unwrap para tener acceso a un valor de ajuste de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="16528-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="16528-185">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16528-185">For instance:</span></span>

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

<span data-ttu-id="16528-186">Eche un vistazo a la sección sobre cómo [desencapsular las expresiones](xref:microsoft.quantum.language.expressions#unwrap-expressions) y la precedencia de los [operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="16528-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="16528-187">Los valores de un tipo definido por el usuario se pueden crear llamando al constructor de tipo correspondiente:</span><span class="sxs-lookup"><span data-stu-id="16528-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="16528-188">Como alternativa, se pueden crear nuevos valores a partir de los existentes mediante [expresiones de copiar y actualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="16528-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="16528-189">Al igual que en el caso de las matrices, estas expresiones copian todos los valores de los elementos de la expresión original, con la excepción de los elementos con nombre especificados.</span><span class="sxs-lookup"><span data-stu-id="16528-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="16528-190">Estos valores se establecen en los que se definen en el lado derecho de la expresión.</span><span class="sxs-lookup"><span data-stu-id="16528-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="16528-191">Cualquier otra construcción de lenguaje, como por ejemplo [instrucciones Update-and-resign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), que están disponibles para los elementos de matriz existen también para los elementos con nombre en los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="16528-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="16528-192">Los tipos definidos por el usuario se pueden usar en cualquier otro tipo que se pueda usar.</span><span class="sxs-lookup"><span data-stu-id="16528-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="16528-193">En concreto, es posible definir una matriz de un tipo definido por el usuario y incluir un tipo definido por el usuario como elemento de un tipo de tupla.</span><span class="sxs-lookup"><span data-stu-id="16528-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="16528-194">No es posible crear estructuras de tipo recursivas.</span><span class="sxs-lookup"><span data-stu-id="16528-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="16528-195">Es decir, el tipo que define un tipo definido por el usuario no puede ser un tipo de tupla que incluya un elemento del tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="16528-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="16528-196">En general, los tipos definidos por el usuario no pueden tener dependencias cíclicas entre sí, por lo que el siguiente conjunto de definiciones de tipo no sería válido:</span><span class="sxs-lookup"><span data-stu-id="16528-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="16528-197">Además de proporcionar alias cortos para tipos de tupla potencialmente complicados, una ventaja importante de definir estos tipos es que pueden documentar el propósito de un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="16528-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="16528-198">Volviendo al ejemplo de `Complex`, puede haber definido también coordenadas polares 2D como un tipo definido por el usuario:</span><span class="sxs-lookup"><span data-stu-id="16528-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="16528-199">Aunque tanto `Complex` como `Polar` tienen un tipo subyacente `(Double, Double)`, los dos tipos son totalmente incompatibles en Q #, lo que minimiza el riesgo de llamar accidentalmente a una función matemática compleja con coordenadas polares y viceversa.</span><span class="sxs-lookup"><span data-stu-id="16528-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="16528-200">De esta manera, los tipos definidos por el usuario tienen un rol similar como F# registros en, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="16528-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="16528-201">Tipos de operación y función</span><span class="sxs-lookup"><span data-stu-id="16528-201">Operation and Function Types</span></span>

<span data-ttu-id="16528-202">Una _operación_ Q # es una subrutina Quantum.</span><span class="sxs-lookup"><span data-stu-id="16528-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="16528-203">Es decir, es una rutina invocable que contiene operaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="16528-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="16528-204">Una _función_ Q # es una subrutina clásica utilizada en un algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="16528-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="16528-205">Puede contener código clásico pero sin operaciones Quantum.</span><span class="sxs-lookup"><span data-stu-id="16528-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="16528-206">En concreto, las funciones no pueden asignar o tomar prestado qubits ni llamar a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="16528-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="16528-207">Sin embargo, es posible pasar operaciones o qubits para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="16528-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="16528-208">Por lo tanto, las funciones son completamente deterministas en el sentido de que si se llama con los mismos argumentos, siempre se producirá el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="16528-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="16528-209">Juntas, las operaciones y las funciones _se llaman llamadas_.</span><span class="sxs-lookup"><span data-stu-id="16528-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="16528-210">Puede ver algunos [ejemplos](#examples) de estos siguientes.</span><span class="sxs-lookup"><span data-stu-id="16528-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="16528-211">Todas las llamadas a Q # pueden tomar un valor único como entrada y devolver un valor único como salida.</span><span class="sxs-lookup"><span data-stu-id="16528-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="16528-212">Los valores de entrada y salida pueden ser tuplas.</span><span class="sxs-lookup"><span data-stu-id="16528-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="16528-213">Se puede llamar a que no se devuelve ningún resultado `Unit`.</span><span class="sxs-lookup"><span data-stu-id="16528-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="16528-214">Las invocaciones que no tienen ninguna entrada toman la tupla vacía como entrada.</span><span class="sxs-lookup"><span data-stu-id="16528-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="16528-215">El tipo básico de cualquier que se pueda llamar se escribe como `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)`, donde tanto `'Tinput` como `'Tresult` son tipos.</span><span class="sxs-lookup"><span data-stu-id="16528-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="16528-216">El primer formulario, con `=>`, se utiliza para las operaciones; la segunda forma, con `->`, para las funciones.</span><span class="sxs-lookup"><span data-stu-id="16528-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="16528-217">Por ejemplo, `((Qubit, Pauli) => Result)` representa la firma de una posible operación de medición de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="16528-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="16528-218">Los tipos de función se especifican completamente mediante su firma.</span><span class="sxs-lookup"><span data-stu-id="16528-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="16528-219">Por ejemplo, una función que calcula el seno de un ángulo tendría el tipo `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="16528-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="16528-220">Las operaciones, pero no las funciones, tienen ciertas _características_ adicionales que se expresan como parte del tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="16528-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="16528-221">Estas características incluyen información sobre los elementos que admite la operación.</span><span class="sxs-lookup"><span data-stu-id="16528-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="16528-222">Los funcdores son metaoperaciones que generan una especialización de una operación base; Vea los [funcers](#functors)más abajo.</span><span class="sxs-lookup"><span data-stu-id="16528-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="16528-223">Los tipos de operación se especifican mediante su tipo de entrada, tipo de salida y sus características.</span><span class="sxs-lookup"><span data-stu-id="16528-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="16528-224">Para requerir la compatibilidad con la `Controlled` y/o el functor `Adjoint` en un tipo de operación, es necesario agregar una anotación que indique las características correspondientes.</span><span class="sxs-lookup"><span data-stu-id="16528-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="16528-225">Un `is Ctl` de anotación, por ejemplo, indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="16528-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="16528-226">Si queremos requerir que una operación de ese tipo admita los `Adjoint` y `Controlled` functor, podemos expresar esto como `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="16528-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="16528-227">Las características de la operación utilizadas `Adj` y `Ctl` de forma rigurosa son dos conjuntos predefinidos de etiquetas, donde cada etiqueta indica una operación determinada, como por ejemplo, la compatibilidad con un functor determinado.</span><span class="sxs-lookup"><span data-stu-id="16528-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="16528-228">Por lo tanto, `+` se usa para indicar la Unión de estos dos conjuntos y `*` se usa para indicar la intersección, es decir, las etiquetas que son comunes a ambos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="16528-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="16528-229">Por ejemplo, la operación Pauli `X` tiene el tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="16528-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="16528-230">Un tipo de operación que no admita ningún functor se especifica solo por su tipo de entrada y salida, sin ninguna anotación adicional.</span><span class="sxs-lookup"><span data-stu-id="16528-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="16528-231">Operaciones y funciones con parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="16528-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="16528-232">Los tipos a los que se puede llamar pueden contener parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="16528-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="16528-233">Los parámetros de tipo se indican mediante un símbolo precedido por una comilla simple; por ejemplo, `'A` es un parámetro de tipo válido.</span><span class="sxs-lookup"><span data-stu-id="16528-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="16528-234">Un parámetro de tipo puede aparecer más de una vez en una sola firma.</span><span class="sxs-lookup"><span data-stu-id="16528-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="16528-235">Por ejemplo, una función que aplica otra función a cada elemento de una matriz y devuelve los resultados recopilados tendría `(('A[], 'A->'A) -> 'A[])`de firma.</span><span class="sxs-lookup"><span data-stu-id="16528-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="16528-236">Del mismo modo, una función que devuelve la composición de dos operaciones puede tener `((('A=>'B), ('B=>'C)) -> ('A=>'C))`de firma.</span><span class="sxs-lookup"><span data-stu-id="16528-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="16528-237">Al invocar un parámetro de tipo al que se puede llamar, todos los argumentos que tienen el mismo parámetro de tipo deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="16528-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="16528-238">Q # no proporciona un mecanismo para restringir los tipos posibles que se pueden sustituir por un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="16528-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="16528-239">Compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="16528-239">Type Compatibility</span></span>

<span data-ttu-id="16528-240">Se puede usar una operación con funciones de compatibilidad adicionales que admitan en cualquier lugar una operación con menos inactivos, pero se espera la misma firma.</span><span class="sxs-lookup"><span data-stu-id="16528-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="16528-241">Por ejemplo, se puede usar una operación de tipo `(Qubit => Unit is Adj)` en cualquier lugar en el que se espere una operación de tipo `(Qubit => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="16528-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="16528-242">Q # es covariante con respecto a los tipos de valor devueltos a los que se puede llamar: una invocable que devuelve un tipo `'A` es compatible con una que se puede llamar con el mismo tipo de entrada y un tipo de resultado que `'A` es compatible con.</span><span class="sxs-lookup"><span data-stu-id="16528-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="16528-243">Q # es contravariante con respecto a los tipos de entrada: una invocable que toma un tipo `'A` como entrada es compatible con una operación invocable con el mismo tipo de resultado y un tipo de entrada que es compatible con `'A`.</span><span class="sxs-lookup"><span data-stu-id="16528-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="16528-244">Es decir, dadas las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="16528-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="16528-245">lo siguiente es cierto:</span><span class="sxs-lookup"><span data-stu-id="16528-245">the following are true:</span></span>

- <span data-ttu-id="16528-246">La función `ConjugateInvertWith` se puede invocar con un argumento `inner` de `Invert` o `ApplyUnitary`.</span><span class="sxs-lookup"><span data-stu-id="16528-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="16528-247">La función `ConjugateUnitaryWith` se puede invocar con un argumento `inner` de `ApplyUnitary`, pero no `Invert`.</span><span class="sxs-lookup"><span data-stu-id="16528-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="16528-248">Un valor de tipo `(Qubit[] => Unit is Adj + Ctl)` puede devolverse desde `ConjugateInvertWith`.</span><span class="sxs-lookup"><span data-stu-id="16528-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16528-249">Q # 0,3 presenta una diferencia significativa en el comportamiento de los tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="16528-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="16528-250">Los tipos definidos por el usuario se tratan como una versión ajustada del tipo subyacente, en lugar de como un subtipo.</span><span class="sxs-lookup"><span data-stu-id="16528-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="16528-251">Esto significa que un valor de un tipo definido por el usuario no se puede usar cuando se espera un valor del tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="16528-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="16528-252">Funciones</span><span class="sxs-lookup"><span data-stu-id="16528-252">Functors</span></span>

<span data-ttu-id="16528-253">Un functor en Q # es un generador que define una nueva operación desde otra operación.</span><span class="sxs-lookup"><span data-stu-id="16528-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="16528-254">Los funcers tienen acceso a la implementación de la operación base al definir la implementación de la nueva operación.</span><span class="sxs-lookup"><span data-stu-id="16528-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="16528-255">Por lo tanto, los funcdores pueden realizar funciones más complejas que las funciones de nivel superior tradicionales.</span><span class="sxs-lookup"><span data-stu-id="16528-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="16528-256">Los inactivos no tienen una representación en el sistema de tipos de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="16528-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="16528-257">Por lo tanto, actualmente no es posible enlazarlas a una variable o pasarlas como argumentos.</span><span class="sxs-lookup"><span data-stu-id="16528-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="16528-258">Se usa un functor si se aplica a una operación y se devuelve una nueva operación.</span><span class="sxs-lookup"><span data-stu-id="16528-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="16528-259">Por ejemplo, la operación que resulta de aplicar el `Adjoint` functor a la operación de `Y` se escribe como `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="16528-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="16528-260">La nueva operación se puede invocar después como cualquier otra operación.</span><span class="sxs-lookup"><span data-stu-id="16528-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="16528-261">Por lo tanto, `Adjoint Y(q1)` aplica el functor injoin a la operación de `Y` para generar una nueva operación y aplica esa nueva operación a `q1`.</span><span class="sxs-lookup"><span data-stu-id="16528-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="16528-262">Del mismo modo, `Controlled X(controls, target)` aplica el functor controlado a la operación de `X` para generar una nueva operación y aplica esa nueva operación a `controls` y `target`.</span><span class="sxs-lookup"><span data-stu-id="16528-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="16528-263">Los dos funcdores estándar en Q # son `Adjoint` y `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="16528-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="16528-264">Contiguo</span><span class="sxs-lookup"><span data-stu-id="16528-264">Adjoint</span></span>

<span data-ttu-id="16528-265">En Quantum Computing, el contiguo de una operación es la transposición de conjugada compleja de la operación.</span><span class="sxs-lookup"><span data-stu-id="16528-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="16528-266">En el caso de las operaciones que implementan un operador unitario, el contiguo es el inverso de la operación.</span><span class="sxs-lookup"><span data-stu-id="16528-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="16528-267">En el caso de una operación simple que simplemente invoca una secuencia de otras operaciones unitarios en un conjunto de qubits, el elemento contiguo puede calcularse aplicando los elementos contiguos de las suboperaciones en el mismo qubits, en la secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="16528-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="16528-268">Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="16528-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="16528-269">Por ejemplo, `Adjoint QFT` designa el contiguo de la operación de `QFT`.</span><span class="sxs-lookup"><span data-stu-id="16528-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="16528-270">La nueva operación tiene la misma signatura y el mismo tipo que la operación base.</span><span class="sxs-lookup"><span data-stu-id="16528-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="16528-271">En concreto, la nueva operación también permite `Adjoint`y permitirá `Controlled` solo si la operación base lo hizo.</span><span class="sxs-lookup"><span data-stu-id="16528-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="16528-272">El inverso inmediato es su propio inverso; es decir, `Adjoint Adjoint Op` siempre es igual que `Op`.</span><span class="sxs-lookup"><span data-stu-id="16528-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="16528-273">Regula</span><span class="sxs-lookup"><span data-stu-id="16528-273">Controlled</span></span>

<span data-ttu-id="16528-274">La versión controlada de una operación es una operación nueva que aplica eficazmente la operación base solo si todos los qubits de control están en un estado especificado.</span><span class="sxs-lookup"><span data-stu-id="16528-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="16528-275">Si el control qubits se encuentra en la superposición, la operación base se aplica de forma coherente a la parte adecuada de la superposición.</span><span class="sxs-lookup"><span data-stu-id="16528-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="16528-276">Por lo tanto, las operaciones controladas suelen usarse para generar el inenredo.</span><span class="sxs-lookup"><span data-stu-id="16528-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="16528-277">En Q #, las versiones controladas siempre toman una matriz de qubits de control, y el estado especificado siempre es para que todo el qubits de control esté en el estado de `One` de cálculo (`PauliZ`), $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="16528-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="16528-278">El control basado en otros Estados puede lograrse aplicando la operación unitario adecuada al control qubits antes de la operación controlada y aplicando después los inversos de la operación unitario después de la operación controlada.</span><span class="sxs-lookup"><span data-stu-id="16528-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="16528-279">Por ejemplo, la aplicación de una operación de `X` a un qubit de control antes y después de una operación controlada hará que la operación se controle en el estado `Zero` ($ \ket{0}$) para ese qubit; al aplicar una operación de `H` antes y después de que se controle el estado de la `PauliX` `One`, es decir,-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ en lugar de `PauliZ` estado `One`.</span><span class="sxs-lookup"><span data-stu-id="16528-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="16528-280">Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="16528-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="16528-281">La firma de la nueva operación se basa en la firma de la operación original.</span><span class="sxs-lookup"><span data-stu-id="16528-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="16528-282">El tipo de resultado es el mismo, pero el tipo de entrada es una tupla de dos tuplas con una matriz qubit que contiene el control qubit (s) como primer elemento y los argumentos de la operación original como el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="16528-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="16528-283">La nueva operación admite `Controlled`y admitirá `Adjoint` si y solo si la operación original lo hizo.</span><span class="sxs-lookup"><span data-stu-id="16528-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="16528-284">Si la operación original solo tomó un argumento, la equivalencia de la tupla singleton entrará en juego aquí.</span><span class="sxs-lookup"><span data-stu-id="16528-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="16528-285">Por ejemplo, `Controlled X` es la versión controlada de la operación de `X`.</span><span class="sxs-lookup"><span data-stu-id="16528-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="16528-286">`X` tiene el tipo `(Qubit => Unit is Adj + Ctl)`, por lo que `Controlled X` tiene el tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; debido a la equivalencia de la tupla singleton, es igual que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="16528-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="16528-287">Si la operación base tomó varios argumentos, Recuerde incluir los argumentos correspondientes de la versión controlada de la operación entre paréntesis para convertirlos en una tupla.</span><span class="sxs-lookup"><span data-stu-id="16528-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="16528-288">Por ejemplo, `Controlled Rz` es la versión controlada de la operación de `Rz`.</span><span class="sxs-lookup"><span data-stu-id="16528-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="16528-289">`Rz` tiene el tipo `((Double, Qubit) => Unit is Adj + Ctl)`, por lo que `Controlled Rz` tiene `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`de tipo.</span><span class="sxs-lookup"><span data-stu-id="16528-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="16528-290">Por lo tanto, `Controlled Rz(controls, (0.1, target))` sería una invocación válida de `Controlled Rz` (observe los paréntesis alrededor de `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="16528-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="16528-291">Como otro ejemplo, `CNOT(control, target)` se puede implementar como `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="16528-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="16528-292">Si un destino debe controlarse mediante 2 control qubits (CCNOT), se puede usar `Controlled X([control1, control2], target)` instrucción.</span><span class="sxs-lookup"><span data-stu-id="16528-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="16528-293">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="16528-293">Examples</span></span>

<span data-ttu-id="16528-294">Este ejemplo de una operación de Q # procede del ejemplo de [medición](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="16528-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="16528-295">Dentro de las operaciones, podemos asignar qubits y usar las operaciones Quantum en esos qubits, como `H` y `X`:</span><span class="sxs-lookup"><span data-stu-id="16528-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="16528-296">Este ejemplo de una función proviene del ejemplo [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="16528-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="16528-297">Contiene código puramente clásico.</span><span class="sxs-lookup"><span data-stu-id="16528-297">It contains purely classical code.</span></span> <span data-ttu-id="16528-298">Puede ver que, a diferencia del ejemplo anterior, no se asigna ningún qubits y no se usa ninguna operación Quantum.</span><span class="sxs-lookup"><span data-stu-id="16528-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="16528-299">También es posible que una función se pase qubits para su procesamiento, como en este ejemplo del ejemplo [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="16528-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="16528-300">Los qubits se pasan a la función y se usan para el procesamiento, aunque en ningún momento se modifican los Estados de qubit.</span><span class="sxs-lookup"><span data-stu-id="16528-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
