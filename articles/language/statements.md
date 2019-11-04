---
title: 'Instrucciones Q # | Microsoft Docs'
description: 'Instrucciones Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184872"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="42f5b-103">Instrucciones y otras construcciones</span><span class="sxs-lookup"><span data-stu-id="42f5b-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="42f5b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42f5b-104">Comments</span></span>

<span data-ttu-id="42f5b-105">Los comentarios comienzan con dos barras diagonales, `//`y continúan hasta el final de la línea.</span><span class="sxs-lookup"><span data-stu-id="42f5b-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="42f5b-106">Puede aparecer un Comentario en cualquier parte de un archivo de código fuente de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="42f5b-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="42f5b-107">Comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="42f5b-107">Documentation Comments</span></span>

<span data-ttu-id="42f5b-108">Los comentarios que comienzan con tres barras diagonales, `///`, se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="42f5b-109">En ese caso, su contenido se toma como documentación para el tipo definido por el usuario o al que se puede llamar, como en otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="42f5b-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="42f5b-110">Dentro de `///` comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), con distintas partes de la documentación que se indican mediante encabezados con el nombre especial.</span><span class="sxs-lookup"><span data-stu-id="42f5b-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="42f5b-111">Como extensión de Markdown, se pueden incluir referencias cruzadas a operaciones, funciones y tipos definidos por el usuario en Q # mediante el `@"<ref target>"`, donde `<ref target>` se reemplaza por el nombre completo del objeto de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="42f5b-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="42f5b-112">Opcionalmente, un motor de documentación también puede admitir extensiones de Markdown adicionales.</span><span class="sxs-lookup"><span data-stu-id="42f5b-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="42f5b-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="42f5b-113">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="42f5b-114">Los nombres siguientes se reconocen como encabezados de comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="42f5b-115">**Summary**: un breve resumen del comportamiento de una función u operación, o del propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="42f5b-116">El primer párrafo del resumen se usa para la información de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="42f5b-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="42f5b-117">Debe ser texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="42f5b-117">It should be plain text.</span></span>
- <span data-ttu-id="42f5b-118">**Descripción**: Descripción del comportamiento de una función u operación, o del propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="42f5b-119">El Resumen y la descripción se concatenan para formar el archivo de documentación generado para la función, la operación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="42f5b-120">La descripción puede contener símbolos y ecuaciones con formato LaTeX en línea.</span><span class="sxs-lookup"><span data-stu-id="42f5b-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="42f5b-121">**Input**: Descripción de la tupla de entrada para una operación o función.</span><span class="sxs-lookup"><span data-stu-id="42f5b-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="42f5b-122">Puede contener subsecciones de Markdown adicionales que indican cada elemento individual de la tupla de entrada.</span><span class="sxs-lookup"><span data-stu-id="42f5b-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="42f5b-123">**Output**: Descripción de la tupla devuelta por una operación o función.</span><span class="sxs-lookup"><span data-stu-id="42f5b-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="42f5b-124">**Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="42f5b-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="42f5b-125">**Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.</span><span class="sxs-lookup"><span data-stu-id="42f5b-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="42f5b-126">**Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="42f5b-127">**Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.</span><span class="sxs-lookup"><span data-stu-id="42f5b-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="42f5b-128">**Referencias**: una lista de referencias y citas para el elemento que se documenta.</span><span class="sxs-lookup"><span data-stu-id="42f5b-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="42f5b-129">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="42f5b-129">Namespaces</span></span>

<span data-ttu-id="42f5b-130">Cada operación Q #, función y tipo definido por el usuario se definen dentro de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="42f5b-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="42f5b-131">Q # sigue las mismas reglas para asignar nombres a otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="42f5b-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="42f5b-132">Sin embargo, Q # no admite referencias relativas a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="42f5b-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="42f5b-133">Es decir, si se ha abierto el espacio de nombres `a.b`, una referencia a un nombre de operación `c.d` no se resolverá en una operación con el nombre completo `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="42f5b-134">Dentro de un bloque de espacio de nombres, la Directiva `open` se puede usar para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="42f5b-135">Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido.</span><span class="sxs-lookup"><span data-stu-id="42f5b-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="42f5b-136">La Directiva `open` se aplica a todo el bloque de espacio de nombres dentro de un archivo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="42f5b-137">Se debe hacer referencia a un tipo o al que se puede llamar en otro espacio de nombres que no esté abierto en el espacio de nombres actual mediante su nombre completo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="42f5b-138">Por ejemplo, se debe hacer referencia a una operación denominada `Op` en el espacio de nombres `X.Y` mediante su nombre completo `X.Y.Op`, a menos que el espacio de nombres de `X.Y` se haya abierto anteriormente en el bloque actual.</span><span class="sxs-lookup"><span data-stu-id="42f5b-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="42f5b-139">Como se mencionó anteriormente, incluso si se ha abierto el espacio de nombres `X`, no es posible hacer referencia a la operación como `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="42f5b-140">Si se ha definido un nombre corto `Z` para `X.Y` en ese espacio de nombres y archivo, se debe hacer referencia a `Op` como `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="42f5b-141">Normalmente es mejor incluir un espacio de nombres mediante una directiva de `open`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="42f5b-142">Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="42f5b-143">Aplicación de formato</span><span class="sxs-lookup"><span data-stu-id="42f5b-143">Formatting</span></span>

<span data-ttu-id="42f5b-144">La mayoría de las instrucciones y directivas de Q # finalizan con un punto y coma de terminación, `;`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="42f5b-145">Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones no requieren un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="42f5b-146">La descripción de cada instrucción indica si es necesario el punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="42f5b-147">Las instrucciones, como las expresiones, las declaraciones y las directivas, pueden dividirse en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="42f5b-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="42f5b-148">Se debe evitar tener varias instrucciones en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="42f5b-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="42f5b-149">Bloques de instrucciones</span><span class="sxs-lookup"><span data-stu-id="42f5b-149">Statement Blocks</span></span>

<span data-ttu-id="42f5b-150">Las instrucciones Q # se agrupan en bloques de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="42f5b-151">Un bloque de instrucciones comienza con un `{` de apertura y termina con un `}`de cierre.</span><span class="sxs-lookup"><span data-stu-id="42f5b-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="42f5b-152">Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="42f5b-153">Enlace y asignación de símbolos</span><span class="sxs-lookup"><span data-stu-id="42f5b-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="42f5b-154">Q # distingue entre símbolos mutables e inmutables.</span><span class="sxs-lookup"><span data-stu-id="42f5b-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="42f5b-155">En general, se recomienda el uso de símbolos inmutables porque permite que el compilador realice más optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="42f5b-156">La parte izquierda del enlace se compone de una tupla de símbolos y del lado derecho de una expresión.</span><span class="sxs-lookup"><span data-stu-id="42f5b-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="42f5b-157">Dado que todos los tipos de Q # son tipos de valor, con el qubits que toma un rol especialmente especial: se crea una "copia" formalmente cuando se enlaza un valor a un símbolo o cuando se reenlaza un símbolo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="42f5b-158">Es decir, el comportamiento de Q # es el mismo que si se creara una copia en la asignación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="42f5b-159">Esto, en concreto, también incluye matrices.</span><span class="sxs-lookup"><span data-stu-id="42f5b-159">This in particular also includes arrays.</span></span> <span data-ttu-id="42f5b-160">Por supuesto, en la práctica solo se recrean las piezas relevantes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="42f5b-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="42f5b-161">Desconstrucción de tuplas</span><span class="sxs-lookup"><span data-stu-id="42f5b-161">Tuple Deconstruction</span></span>

<span data-ttu-id="42f5b-162">Si el lado derecho del enlace es una tupla, esa tupla se puede desconstruir en el momento de la asignación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="42f5b-163">Estas desconstrucciones pueden implicar tuplas anidadas, y cualquier desconstrucción parcial o completa es válida siempre y cuando la forma de la tupla en el lado derecho sea compatible con la forma de la tupla de símbolos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="42f5b-164">La desconstrucción de tuplas se puede usar en concreto también cuando el lado derecho del `=` es una expresión de valor de tupla.</span><span class="sxs-lookup"><span data-stu-id="42f5b-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="42f5b-165">Símbolos inmutables</span><span class="sxs-lookup"><span data-stu-id="42f5b-165">Immutable Symbols</span></span>

<span data-ttu-id="42f5b-166">Los símbolos inmutables se enlazan mediante la instrucción `let`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="42f5b-167">Esto es aproximadamente equivalente a la declaración y la inicialización de variables C#en lenguajes como, excepto en que los símbolos de Q #, una vez enlazados, no se pueden cambiar. `let` enlaces son inmutables.</span><span class="sxs-lookup"><span data-stu-id="42f5b-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="42f5b-168">Un enlace inmutable se compone de la palabra clave `let`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión para enlazar los símbolos a y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="42f5b-169">El tipo de los símbolos enlazados se infiere en función de la expresión del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="42f5b-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="42f5b-170">Símbolos mutables</span><span class="sxs-lookup"><span data-stu-id="42f5b-170">Mutable Symbols</span></span>

<span data-ttu-id="42f5b-171">Los símbolos mutables se definen y se inicializan mediante la instrucción `mutable`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="42f5b-172">Los símbolos declarados y enlazados como parte de una instrucción `mutable` se pueden volver a enlazar a un valor diferente más adelante en el código.</span><span class="sxs-lookup"><span data-stu-id="42f5b-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="42f5b-173">Una instrucción de enlace mutable se compone de la palabra clave `mutable`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión para enlazar los símbolos a y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="42f5b-174">El tipo de los símbolos enlazados se infiere en función de la expresión del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="42f5b-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="42f5b-175">Si un símbolo se reenlaza posteriormente en el código, su tipo no cambia y el valor enlazado debe ser compatible con ese tipo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="42f5b-176">Reenlazar símbolos mutables</span><span class="sxs-lookup"><span data-stu-id="42f5b-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="42f5b-177">Una variable mutable se puede reenlazar mediante una instrucción `set`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="42f5b-178">Este tipo de reenlace consta de la palabra clave `set`, seguida de una tupla de símbolos o símbolos, una `=`de signo igual, una expresión a la que se deben volver a enlazar los símbolos y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="42f5b-179">El valor debe ser compatible con los tipos de los símbolos a los que está enlazado.</span><span class="sxs-lookup"><span data-stu-id="42f5b-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="42f5b-180">Apply-and-resign (instrucción)</span><span class="sxs-lookup"><span data-stu-id="42f5b-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="42f5b-181">Una clase concreta de Set-Statement a la que se hace referencia como una instrucción Apply-and-resign proporciona una forma cómoda de concatenación si el lado derecho está compuesto por la aplicación de un operador binario y el resultado se va a volver a enlazar al argumento izquierdo al operador.</span><span class="sxs-lookup"><span data-stu-id="42f5b-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="42f5b-182">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="42f5b-183">incrementa el valor del contador `counter` en cada iteración del bucle de `for`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="42f5b-184">El código anterior es equivalente a</span><span class="sxs-lookup"><span data-stu-id="42f5b-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="42f5b-185">Las instrucciones similares están disponibles para todos los operadores binarios en los que el tipo del lado izquierdo coincide con el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="42f5b-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="42f5b-186">Esto proporciona, por ejemplo, una manera cómoda de acumular valores:</span><span class="sxs-lookup"><span data-stu-id="42f5b-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="42f5b-187">Update-and-resign (instrucción)</span><span class="sxs-lookup"><span data-stu-id="42f5b-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="42f5b-188">Existe una concatenación similar para las expresiones de copia y actualización en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="42f5b-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="42f5b-189">En consecuencia, las instrucciones Update-and-resign existen para los elementos con nombre de los tipos definidos por el usuario, así como para los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="42f5b-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="42f5b-190">En el caso de las matrices, nuestras bibliotecas estándar contienen las herramientas necesarias para muchas necesidades comunes de inicialización y manipulación de matrices y, por tanto, ayudan a evitar tener que actualizar los elementos de la matriz en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="42f5b-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="42f5b-191">Las instrucciones Update-and-resign proporcionan una alternativa si es necesario:</span><span class="sxs-lookup"><span data-stu-id="42f5b-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="42f5b-192">Evite el uso innecesario de las instrucciones de actualización y reasignación aprovechando las herramientas proporcionadas en <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="42f5b-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="42f5b-193">La función</span><span class="sxs-lookup"><span data-stu-id="42f5b-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="42f5b-194">por ejemplo, se puede simplificar simplemente con la función `ConstantArray` en `Microsoft.Quantum.Arrays`y devolver una expresión de copia y actualización:</span><span class="sxs-lookup"><span data-stu-id="42f5b-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="42f5b-195">Ámbitos de enlace</span><span class="sxs-lookup"><span data-stu-id="42f5b-195">Binding Scopes</span></span>

<span data-ttu-id="42f5b-196">En general, los enlaces de símbolos salen del ámbito y quedan inoperativos al final del bloque de instrucciones en el que se encuentran.</span><span class="sxs-lookup"><span data-stu-id="42f5b-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="42f5b-197">Hay dos excepciones a esta regla:</span><span class="sxs-lookup"><span data-stu-id="42f5b-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="42f5b-198">El enlace de la variable de bucle de un bucle `for` está en el ámbito del cuerpo del bucle for, pero no después del final del bucle.</span><span class="sxs-lookup"><span data-stu-id="42f5b-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="42f5b-199">Las tres partes de una `repeat`/bucle `until` (el cuerpo, la prueba y la corrección) se tratan como un solo ámbito, por lo que los símbolos que están enlazados en el cuerpo están disponibles en la prueba y en la corrección.</span><span class="sxs-lookup"><span data-stu-id="42f5b-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="42f5b-200">En ambos tipos de bucles, cada paso a través del bucle se ejecuta en su propio ámbito, por lo que los enlaces de un paso anterior no están disponibles en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="42f5b-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="42f5b-201">Los enlaces de símbolos de los bloques externos los heredan los bloques internos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="42f5b-202">Un símbolo solo se puede enlazar una vez por bloque; no es válido definir un símbolo con el mismo nombre que otro símbolo que está dentro del ámbito (sin "sombreado").</span><span class="sxs-lookup"><span data-stu-id="42f5b-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="42f5b-203">Las secuencias siguientes serían válidas:</span><span class="sxs-lookup"><span data-stu-id="42f5b-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="42f5b-204">y</span><span class="sxs-lookup"><span data-stu-id="42f5b-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="42f5b-205">Pero esto sería ilegal:</span><span class="sxs-lookup"><span data-stu-id="42f5b-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="42f5b-206">como sería:</span><span class="sxs-lookup"><span data-stu-id="42f5b-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="42f5b-207">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="42f5b-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="42f5b-208">Bucle for</span><span class="sxs-lookup"><span data-stu-id="42f5b-208">For Loop</span></span>

<span data-ttu-id="42f5b-209">La instrucción `for` admite la iteración en un intervalo de enteros o en una matriz.</span><span class="sxs-lookup"><span data-stu-id="42f5b-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="42f5b-210">La instrucción consta de la palabra clave `for`, un paréntesis de apertura `(`, seguido de una tupla de símbolos o símbolos, la palabra clave `in`, una expresión de tipo `Range` o array, un paréntesis de cierre `)`y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="42f5b-211">El bloque de instrucciones (el cuerpo del bucle) se ejecuta varias veces, con los símbolos definidos (las variables de bucle) enlazados a cada valor del intervalo o de la matriz.</span><span class="sxs-lookup"><span data-stu-id="42f5b-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="42f5b-212">Tenga en cuenta que si la expresión de rango se evalúa como un intervalo o una matriz vacíos, el cuerpo no se ejecutará en absoluto.</span><span class="sxs-lookup"><span data-stu-id="42f5b-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="42f5b-213">La expresión se evalúa completamente antes de entrar en el bucle y no cambiará mientras se ejecuta el bucle.</span><span class="sxs-lookup"><span data-stu-id="42f5b-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="42f5b-214">El enlace de los símbolos declarados es inmutable y sigue las mismas reglas que otros enlaces de variables.</span><span class="sxs-lookup"><span data-stu-id="42f5b-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="42f5b-215">En concreto, es posible desestructurar, por ejemplo, los elementos de matriz de una iteración en una matriz cuando se asignan a las variables de bucle.</span><span class="sxs-lookup"><span data-stu-id="42f5b-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="42f5b-216">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="42f5b-217">La variable de bucle se enlaza en cada entrada al cuerpo del bucle y sin enlazar al final del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="42f5b-218">En concreto, la variable de bucle no se enlaza una vez completado el bucle for.</span><span class="sxs-lookup"><span data-stu-id="42f5b-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="42f5b-219">Bucle repeat-Until-Success</span><span class="sxs-lookup"><span data-stu-id="42f5b-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="42f5b-220">La instrucción `repeat` admite el patrón "repetir hasta el éxito".</span><span class="sxs-lookup"><span data-stu-id="42f5b-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="42f5b-221">Consta de la palabra clave `repeat`, seguida de un bloque de instrucciones (el cuerpo del _bucle_ ), la palabra clave `until`, una expresión booleana y un punto y coma de terminación o la palabra clave `fixup` seguido de otro bloque de instrucciones (la _corrección_).</span><span class="sxs-lookup"><span data-stu-id="42f5b-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="42f5b-222">El cuerpo, la condición y la corrección del bucle se consideran un solo ámbito, por lo que los símbolos enlazados en el cuerpo están disponibles en la condición y la corrección.</span><span class="sxs-lookup"><span data-stu-id="42f5b-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="42f5b-223">Se ejecuta el cuerpo del bucle y, a continuación, se evalúa la condición.</span><span class="sxs-lookup"><span data-stu-id="42f5b-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="42f5b-224">Si la condición es true, la instrucción se completa; de lo contrario, se ejecuta la corrección y la instrucción se vuelve a ejecutar empezando por el cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="42f5b-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="42f5b-225">Tenga en cuenta que al completar la ejecución de la corrección finaliza el ámbito de la instrucción, de modo que los enlaces de símbolos realizados durante el cuerpo o la corrección no estén disponibles en las repeticiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="42f5b-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="42f5b-226">Por ejemplo, el código siguiente es un circuito probabilística que implementa una puerta de rotación importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando las puertas Hadamard y T.</span><span class="sxs-lookup"><span data-stu-id="42f5b-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="42f5b-227">El bucle finaliza en 8/5 repeticiones de promedio.</span><span class="sxs-lookup"><span data-stu-id="42f5b-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="42f5b-228">Vea [*repetir hasta el éxito: descomposición no determinista de unitaries de un solo qubit*](https://arxiv.org/abs/1311.1074) (Paetznick y Svore, 2014) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="42f5b-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="42f5b-229">Evite el uso de bucles de repetición hasta la ejecución correcta dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="42f5b-230">La funcionalidad correspondiente la proporcionan los bucles while en las funciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="42f5b-231">While (bucle)</span><span class="sxs-lookup"><span data-stu-id="42f5b-231">While Loop</span></span>

<span data-ttu-id="42f5b-232">Los patrones de repetición hasta el éxito tienen una connotación específica de Quantum.</span><span class="sxs-lookup"><span data-stu-id="42f5b-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="42f5b-233">Se usan ampliamente en clases concretas de algoritmos Quantum; por lo tanto, la construcción de lenguaje dedicada en Q #.</span><span class="sxs-lookup"><span data-stu-id="42f5b-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="42f5b-234">Sin embargo, los bucles que se interrumpen en función de una condición y cuya longitud de ejecución se desconoce en tiempo de compilación deben controlarse con especial atención en un tiempo de ejecución de Quantum.</span><span class="sxs-lookup"><span data-stu-id="42f5b-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="42f5b-235">El uso de las funciones por otro lado no es problemático, ya que solo contienen código que se ejecutará en hardware convencional (no Quantum).</span><span class="sxs-lookup"><span data-stu-id="42f5b-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="42f5b-236">Por lo tanto, Q # solo admite el uso de bucles while dentro de funciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="42f5b-237">Una instrucción `while` consta de la palabra clave `while`, un paréntesis de apertura `(`, una condición (es decir, una expresión booleana), un paréntesis de cierre `)`y un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="42f5b-238">El bloque de instrucciones (el cuerpo del bucle) se ejecuta siempre que la condición se evalúe como `true`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="42f5b-239">Instrucción condicional</span><span class="sxs-lookup"><span data-stu-id="42f5b-239">Conditional Statement</span></span>

<span data-ttu-id="42f5b-240">La instrucción `if` admite la ejecución condicional.</span><span class="sxs-lookup"><span data-stu-id="42f5b-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="42f5b-241">Consta de la palabra clave `if`, un paréntesis de apertura `(`, una expresión booleana, un paréntesis de cierre `)`y un bloque de instrucciones (el bloque _then_ ).</span><span class="sxs-lookup"><span data-stu-id="42f5b-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="42f5b-242">Esto puede ir seguido de cualquier número de cláusulas else-if, cada una de las cuales consta de la palabra clave `elif`, un `(`de paréntesis de apertura, una expresión booleana, un paréntesis de cierre `)`y un bloque de instrucciones (el bloque _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="42f5b-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="42f5b-243">Por último, la instrucción puede terminar opcionalmente con una cláusula else, que consta de la palabra clave `else` seguido de otro bloque de instrucciones (el bloque _else_ ).</span><span class="sxs-lookup"><span data-stu-id="42f5b-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="42f5b-244">La condición se evalúa y, si es true, se ejecuta el bloque then.</span><span class="sxs-lookup"><span data-stu-id="42f5b-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="42f5b-245">Si la condición es false, se evalúa la primera condición else-if; Si es true, se ejecuta el bloque else-if.</span><span class="sxs-lookup"><span data-stu-id="42f5b-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="42f5b-246">De lo contrario, el segundo bloque else-if se prueba y, a continuación, el tercero, y así sucesivamente hasta que se encuentre una cláusula con una condición true o no haya más cláusulas else-if.</span><span class="sxs-lookup"><span data-stu-id="42f5b-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="42f5b-247">Si las cláusulas IF original y All else-if se evalúan como false, el bloque else se ejecutará si se proporciona uno.</span><span class="sxs-lookup"><span data-stu-id="42f5b-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="42f5b-248">Tenga en cuenta que el bloque que se ejecuta se ejecuta en su propio ámbito.</span><span class="sxs-lookup"><span data-stu-id="42f5b-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="42f5b-249">Los enlaces realizados dentro de un bloque then, else-if o else no están visibles después del final de la instrucción if.</span><span class="sxs-lookup"><span data-stu-id="42f5b-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="42f5b-250">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="42f5b-251">O bien</span><span class="sxs-lookup"><span data-stu-id="42f5b-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="42f5b-252">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42f5b-252">Return</span></span>

<span data-ttu-id="42f5b-253">La instrucción return finaliza la ejecución de una operación o función y devuelve un valor al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="42f5b-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="42f5b-254">Consta de la palabra clave `return`, seguida de una expresión del tipo adecuado y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="42f5b-255">Un que se puede llamar que devuelve una tupla vacía, `()`, no requiere una instrucción return.</span><span class="sxs-lookup"><span data-stu-id="42f5b-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="42f5b-256">Si se desea una salida temprana, se puede usar `return ()` en este caso.</span><span class="sxs-lookup"><span data-stu-id="42f5b-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="42f5b-257">Las llamadas que devuelven cualquier otro tipo requieren una instrucción return final.</span><span class="sxs-lookup"><span data-stu-id="42f5b-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="42f5b-258">No hay ningún número máximo de instrucciones Return en una operación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="42f5b-259">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción return dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="42f5b-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="42f5b-260">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="42f5b-261">O bien</span><span class="sxs-lookup"><span data-stu-id="42f5b-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="42f5b-262">O bien</span><span class="sxs-lookup"><span data-stu-id="42f5b-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="42f5b-263">Fail (no superado)</span><span class="sxs-lookup"><span data-stu-id="42f5b-263">Fail</span></span>

<span data-ttu-id="42f5b-264">La instrucción FAIL finaliza la ejecución de una operación y devuelve un valor de error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="42f5b-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="42f5b-265">Consta de la palabra clave `fail`, seguida de una cadena y un punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="42f5b-266">La cadena se devuelve al controlador clásico como el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="42f5b-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="42f5b-267">No hay ninguna restricción en el número de instrucciones erróneas dentro de una operación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="42f5b-268">El compilador puede emitir una advertencia si las instrucciones siguen una instrucción FAIL dentro de un bloque.</span><span class="sxs-lookup"><span data-stu-id="42f5b-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="42f5b-269">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="42f5b-270">O bien</span><span class="sxs-lookup"><span data-stu-id="42f5b-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="42f5b-271">Administración de qubit</span><span class="sxs-lookup"><span data-stu-id="42f5b-271">Qubit Management</span></span>

<span data-ttu-id="42f5b-272">Tenga en cuenta que ninguna de estas instrucciones está permitida dentro del cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="42f5b-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="42f5b-273">Solo son válidos dentro de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="42f5b-274">Limpiar qubits</span><span class="sxs-lookup"><span data-stu-id="42f5b-274">Clean Qubits</span></span>

<span data-ttu-id="42f5b-275">La instrucción `using` se usa para adquirir New qubits para su uso durante un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="42f5b-276">Se garantiza que los qubits se inicializan en el estado `Zero` de cálculo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="42f5b-277">Qubits debe estar en el estado `Zero` de cálculo al final del bloque de instrucciones; se recomienda que los simuladores apliquen esto.</span><span class="sxs-lookup"><span data-stu-id="42f5b-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="42f5b-278">La instrucción consta de la palabra clave `using`, seguida de un paréntesis de apertura `(`, un enlace, un paréntesis de cierre `)`y el bloque de instrucciones en el que estará disponible el qubits.</span><span class="sxs-lookup"><span data-stu-id="42f5b-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="42f5b-279">El enlace sigue el mismo patrón que `let` instrucciones: un solo símbolo o una tupla de símbolos, seguido de un signo igual `=`y un solo valor o una tupla coincidente de inicializadores.</span><span class="sxs-lookup"><span data-stu-id="42f5b-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="42f5b-280">Los inicializadores están disponibles para un único qubit, indicado como `Qubit()`, o una matriz de qubits, indicada por `Qubit[`, una expresión de `Int` y `]`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="42f5b-281">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="42f5b-282">Qubits sucio</span><span class="sxs-lookup"><span data-stu-id="42f5b-282">Dirty Qubits</span></span>

<span data-ttu-id="42f5b-283">La instrucción `borrowing` se usa para obtener qubits para su uso temporal.</span><span class="sxs-lookup"><span data-stu-id="42f5b-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="42f5b-284">La instrucción consta de la palabra clave `borrowing`, seguida de un paréntesis de apertura `(`, un enlace, un paréntesis de cierre `)`y el bloque de instrucciones en el que estará disponible el qubits.</span><span class="sxs-lookup"><span data-stu-id="42f5b-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="42f5b-285">El enlace sigue el mismo patrón y las mismas reglas que el de una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="42f5b-286">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="42f5b-287">Los qubits prestados se encuentran en un estado desconocido y salen del ámbito al final del bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="42f5b-288">El prestatario se compromete a mantener el qubits en el mismo estado en que se encontraban cuando se prestó, es decir, su estado al principio y al final del bloque de instrucciones se espera que sea el mismo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="42f5b-289">En concreto, este estado no es necesariamente un estado clásico, de modo que en la mayoría de los casos, los ámbitos de préstamo no deben contener medidas.</span><span class="sxs-lookup"><span data-stu-id="42f5b-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="42f5b-290">Estos qubits a menudo se conocen como "sucios Ancilla".</span><span class="sxs-lookup"><span data-stu-id="42f5b-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="42f5b-291">Consulte [*factorización con 2N + 2 qubits con multiplicación modular basada en Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler y Svore 2017) para obtener un ejemplo de uso de Dirty ancilla.</span><span class="sxs-lookup"><span data-stu-id="42f5b-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="42f5b-292">Al tomar prestado qubits, el sistema intentará en primer lugar rellenar la solicitud de qubits que están en uso, pero a las que no se tiene acceso durante el cuerpo de la instrucción de `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="42f5b-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="42f5b-293">Si no hay suficiente qubits, asignará nuevo qubits para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="42f5b-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="42f5b-294">Conjugaciones</span><span class="sxs-lookup"><span data-stu-id="42f5b-294">Conjugations</span></span>

<span data-ttu-id="42f5b-295">A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito.</span><span class="sxs-lookup"><span data-stu-id="42f5b-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="42f5b-296">Esto puede evitarse al "deshacer" correctamente los cálculos realizados antes de liberar la memoria.</span><span class="sxs-lookup"><span data-stu-id="42f5b-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="42f5b-297">Un patrón común en la informática Quantum es, por lo tanto, lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42f5b-297">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="42f5b-298">: nuevo: a partir de la versión 0,9, se admite una instrucción de conjugación que implementa la transformación anterior.</span><span class="sxs-lookup"><span data-stu-id="42f5b-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="42f5b-299">Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="42f5b-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="42f5b-300">Obviamente, este tipo de declaración es mucho más útil si la transformación externa e interna no está disponible como operaciones, pero en su lugar es más conveniente describirla mediante un bloque que consta de varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="42f5b-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="42f5b-301">El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply.</span><span class="sxs-lookup"><span data-stu-id="42f5b-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="42f5b-302">Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de.</span><span class="sxs-lookup"><span data-stu-id="42f5b-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="42f5b-303">Instrucciones de evaluación de expresiones</span><span class="sxs-lookup"><span data-stu-id="42f5b-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="42f5b-304">Cualquier expresión de llamada de tipo `Unit` se puede usar como una instrucción.</span><span class="sxs-lookup"><span data-stu-id="42f5b-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="42f5b-305">Esto se usa principalmente cuando se llama a operaciones en qubits que devuelven `Unit` porque el propósito de la instrucción es modificar el estado de Quantum implícito.</span><span class="sxs-lookup"><span data-stu-id="42f5b-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="42f5b-306">Las instrucciones de evaluación de expresiones requieren un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="42f5b-307">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="42f5b-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
