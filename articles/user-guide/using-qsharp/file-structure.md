---
title: Estructura de archivos de preguntas y respuestas
description: Describe la estructura y la sintaxis de un archivo de preguntas y respuestas.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327465"
---
# <a name="q-file-structure"></a><span data-ttu-id="34368-103">Estructura de archivos de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="34368-103">Q# File Structure</span></span>

<span data-ttu-id="34368-104">Cada operación Q #, función y tipo definido por el usuario se definen dentro de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="34368-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="34368-105">Un archivo de preguntas # consta de una secuencia de *declaraciones de espacios de nombres*.</span><span class="sxs-lookup"><span data-stu-id="34368-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="34368-106">Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="34368-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="34368-107">Una declaración de espacio de nombres puede contener cualquier número de cada tipo de declaración y en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="34368-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="34368-108">Siga estos vínculos para obtener más información sobre cómo declarar tipos, [operaciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)y [funciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types)dentro de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="34368-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="34368-109">El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.</span><span class="sxs-lookup"><span data-stu-id="34368-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="34368-110">En concreto, los comentarios de documentación (más detalles a continuación) para un espacio de nombres preceden a la declaración.</span><span class="sxs-lookup"><span data-stu-id="34368-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="34368-111">Declaraciones de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="34368-111">Namespace Declarations</span></span>

<span data-ttu-id="34368-112">Un archivo de preguntas # normalmente tendrá exactamente una declaración de espacio de nombres, pero puede tener ninguno (y estar vacío o contener solo comentarios) o puede contener varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="34368-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="34368-113">Las declaraciones de espacio de nombres no pueden estar anidadas.</span><span class="sxs-lookup"><span data-stu-id="34368-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="34368-114">El mismo espacio de nombres se puede declarar en varios archivos Q # que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="34368-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="34368-115">En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.</span><span class="sxs-lookup"><span data-stu-id="34368-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="34368-116">Una declaración de espacio de nombres consta de la palabra clave `namespace` , seguida del nombre del espacio de nombres, una llave de apertura `{` , las declaraciones contenidas en el espacio de nombres y una llave de cierre `}` .</span><span class="sxs-lookup"><span data-stu-id="34368-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="34368-117">Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.` .</span><span class="sxs-lookup"><span data-stu-id="34368-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="34368-118">Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Intrinsic` son nombres de espacio de nombres válidos.</span><span class="sxs-lookup"><span data-stu-id="34368-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="34368-119">Por Convención, los símbolos de un nombre de espacio de nombres se escriben en mayúsculas, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="34368-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="34368-120">Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.</span><span class="sxs-lookup"><span data-stu-id="34368-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="34368-121">Directivas Open</span><span class="sxs-lookup"><span data-stu-id="34368-121">Open Directives</span></span>

<span data-ttu-id="34368-122">Dentro de un bloque de espacio de nombres, la `open` Directiva se puede usar para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.</span><span class="sxs-lookup"><span data-stu-id="34368-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="34368-123">Esta `open` Directiva se compone de la `open` palabra clave, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="34368-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="34368-124">Todas las `open` directivas deben aparecer antes `function` `operation` de cualquier declaración, o `newtype` en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="34368-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="34368-125">Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido.</span><span class="sxs-lookup"><span data-stu-id="34368-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="34368-126">Por ejemplo, dada la siguiente declaración de espacio de nombres y las directivas Open,</span><span class="sxs-lookup"><span data-stu-id="34368-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="34368-127">Si una operación declarada usa una operación `Op` de `Microsoft.Quantum.Intrinsic` , se llamaría simplemente mediante el uso de `Op` .</span><span class="sxs-lookup"><span data-stu-id="34368-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="34368-128">Sin embargo, si deseáramos llamar a una función determinada `Fn` de `Microsoft.Quantum.Math` , deberíamos llamarlo mediante `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="34368-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="34368-129">La `open` Directiva se aplica a todo el bloque de espacio de nombres dentro de un archivo.</span><span class="sxs-lookup"><span data-stu-id="34368-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="34368-130">Por lo tanto, si fuera a definir un espacio de nombres adicional en el mismo archivo Q # que `NS` anteriormente, las operaciones, funciones o tipos definidos en el segundo espacio de nombres no tendrían acceso a nada desde `Microsoft.Quantum.Intrinsic` o `Microsoft.Quantum.Math` a menos que repetimos las directivas Open.</span><span class="sxs-lookup"><span data-stu-id="34368-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="34368-131">Se debe hacer referencia a un tipo o al que se puede llamar en otro espacio de nombres que *no* esté abierto en el espacio de nombres actual mediante su nombre completo.</span><span class="sxs-lookup"><span data-stu-id="34368-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="34368-132">Por ejemplo, `Op` se debe hacer referencia a una operación denominada desde el `X.Y` espacio de nombres mediante su nombre completo `X.Y.Op` , a menos que el espacio de nombres se haya `X.Y` abierto anteriormente en el bloque actual.</span><span class="sxs-lookup"><span data-stu-id="34368-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="34368-133">Como se mencionó anteriormente, incluso si se ha `X` abierto el espacio de nombres, no es posible hacer referencia a la operación como `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="34368-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="34368-134">Si se ha definido un nombre corto `Z` para `X.Y` en ese espacio de nombres y archivo, `Op` debe hacerse referencia a él como `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="34368-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="34368-135">Normalmente es mejor incluir un espacio de nombres mediante una `open` Directiva.</span><span class="sxs-lookup"><span data-stu-id="34368-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="34368-136">Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.</span><span class="sxs-lookup"><span data-stu-id="34368-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="34368-137">Q # sigue las mismas reglas para asignar nombres a otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="34368-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="34368-138">Sin embargo, Q # no admite referencias relativas a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="34368-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="34368-139">Es decir, si se ha abierto el espacio de nombres `a.b` , una referencia a una operación denominada `c.d` *no* se resolverá en una operación con el nombre completo `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="34368-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="34368-140">Aplicación de formato</span><span class="sxs-lookup"><span data-stu-id="34368-140">Formatting</span></span>

<span data-ttu-id="34368-141">La mayoría de las instrucciones y directivas de Q # finalizan con un punto y coma de terminación, `;` .</span><span class="sxs-lookup"><span data-stu-id="34368-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="34368-142">Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones (vea a continuación) no requieren un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="34368-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="34368-143">La descripción de cada instrucción indica si es necesario el punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="34368-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="34368-144">Las instrucciones, como las expresiones, las declaraciones y las directivas, pueden dividirse en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="34368-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="34368-145">Se debe evitar tener varias instrucciones en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="34368-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="34368-146">Bloques de instrucciones</span><span class="sxs-lookup"><span data-stu-id="34368-146">Statement Blocks</span></span>

<span data-ttu-id="34368-147">Las instrucciones Q # se agrupan en bloques de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="34368-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="34368-148">Un bloque de instrucciones comienza con una apertura `{` y termina con un cierre `}` .</span><span class="sxs-lookup"><span data-stu-id="34368-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="34368-149">Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.</span><span class="sxs-lookup"><span data-stu-id="34368-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="34368-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34368-150">Comments</span></span>

<span data-ttu-id="34368-151">Los comentarios comienzan con dos barras diagonales, `//` y continúan hasta el final de la línea.</span><span class="sxs-lookup"><span data-stu-id="34368-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="34368-152">Puede aparecer un Comentario en cualquier parte de un archivo de código fuente de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="34368-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="34368-153">Comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="34368-153">Documentation Comments</span></span>

<span data-ttu-id="34368-154">Los comentarios que comienzan con tres barras diagonales, `///` , se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="34368-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="34368-155">En ese caso, su contenido se toma como documentación para el tipo definido por el usuario o al que se puede llamar, como en otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="34368-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="34368-156">Dentro de los `///` comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), donde se indican diferentes partes de la documentación con encabezados con el nombre especial.</span><span class="sxs-lookup"><span data-stu-id="34368-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="34368-157">Como extensión de Markdown, las referencias cruzadas a operaciones, funciones y tipos definidos por el usuario en Q # pueden incluirse mediante `@"<ref target>"` , donde `<ref target>` se reemplaza por el nombre completo del objeto de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="34368-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="34368-158">Opcionalmente, un motor de documentación también puede admitir extensiones de Markdown adicionales.</span><span class="sxs-lookup"><span data-stu-id="34368-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="34368-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="34368-159">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="34368-160">Los nombres siguientes se reconocen como encabezados de comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="34368-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="34368-161">**Summary**: un breve resumen del comportamiento de una función u operación, o del propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="34368-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="34368-162">El primer párrafo del resumen se usa para la información de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="34368-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="34368-163">Debe ser texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="34368-163">It should be plain text.</span></span>
- <span data-ttu-id="34368-164">**Descripción**: Descripción del comportamiento de una función u operación, o del propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="34368-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="34368-165">El Resumen y la descripción se concatenan para formar el archivo de documentación generado para la función, la operación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="34368-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="34368-166">La descripción puede contener símbolos y ecuaciones con formato LaTeX en línea.</span><span class="sxs-lookup"><span data-stu-id="34368-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="34368-167">**Input**: Descripción de la tupla de entrada para una operación o función.</span><span class="sxs-lookup"><span data-stu-id="34368-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="34368-168">Puede contener subsecciones de Markdown adicionales que indican cada elemento individual de la tupla de entrada.</span><span class="sxs-lookup"><span data-stu-id="34368-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="34368-169">**Output**: Descripción de la tupla devuelta por una operación o función.</span><span class="sxs-lookup"><span data-stu-id="34368-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="34368-170">**Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="34368-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="34368-171">**Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.</span><span class="sxs-lookup"><span data-stu-id="34368-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="34368-172">**Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.</span><span class="sxs-lookup"><span data-stu-id="34368-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="34368-173">**Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.</span><span class="sxs-lookup"><span data-stu-id="34368-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="34368-174">**Referencias**: una lista de referencias y citas para el elemento que se documenta.</span><span class="sxs-lookup"><span data-stu-id="34368-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34368-175">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="34368-175">Next steps</span></span>

<span data-ttu-id="34368-176">Obtenga información sobre [las operaciones y las funciones](xref:microsoft.quantum.guide.operationsfunctions) de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="34368-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>