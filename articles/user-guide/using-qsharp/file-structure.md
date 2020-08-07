---
title: Q#Estructura de archivos
description: Describe la estructura y la sintaxis de un Q# archivo.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867937"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="2f709-103">Q#Estructura de archivos</span><span class="sxs-lookup"><span data-stu-id="2f709-103">Q# File Structure</span></span>

<span data-ttu-id="2f709-104">Un Q# archivo consta de una secuencia de *declaraciones de espacios de nombres*.</span><span class="sxs-lookup"><span data-stu-id="2f709-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="2f709-105">Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario, y puede contener cualquier número de cada tipo de declaración y en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="2f709-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="2f709-106">Para obtener más información sobre las declaraciones dentro de un espacio de nombres, vea [tipos definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types), [operaciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)y [funciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="2f709-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="2f709-107">El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.</span><span class="sxs-lookup"><span data-stu-id="2f709-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="2f709-108">En concreto, los comentarios de documentación para un espacio de nombres preceden a la declaración.</span><span class="sxs-lookup"><span data-stu-id="2f709-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="2f709-109">Para obtener más información, consulte los [comentarios de documentación](#documentation-comments) en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2f709-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="2f709-110">Declaraciones de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="2f709-110">Namespace Declarations</span></span>

<span data-ttu-id="2f709-111">Un Q# archivo normalmente tiene solo una declaración de espacio de nombres, pero podría tener ninguno (y estar vacío o contener solo comentarios) o podría contener varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="2f709-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="2f709-112">Las declaraciones de espacio de nombres no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="2f709-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="2f709-113">Puede declarar el mismo espacio de nombres en varios Q# archivos que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2f709-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="2f709-114">En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.</span><span class="sxs-lookup"><span data-stu-id="2f709-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="2f709-115">Una declaración de espacio de nombres consta de la palabra clave `namespace` , seguida del nombre del espacio de nombres y de las declaraciones contenidas en el espacio de nombres entre llaves `{ }` .</span><span class="sxs-lookup"><span data-stu-id="2f709-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="2f709-116">Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.` .</span><span class="sxs-lookup"><span data-stu-id="2f709-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="2f709-117">Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Intrinsic` son nombres de espacio de nombres válidos.</span><span class="sxs-lookup"><span data-stu-id="2f709-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="2f709-118">Por Convención, ponga en mayúsculas los símbolos en un nombre de espacio de nombres; sin embargo, esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="2f709-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="2f709-119">Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.</span><span class="sxs-lookup"><span data-stu-id="2f709-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="2f709-120">Directivas Open</span><span class="sxs-lookup"><span data-stu-id="2f709-120">Open Directives</span></span>

<span data-ttu-id="2f709-121">Dentro de un bloque de espacio de nombres, utilice la `open` Directiva para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.</span><span class="sxs-lookup"><span data-stu-id="2f709-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="2f709-122">Esta `open` Directiva se compone de la `open` palabra clave, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="2f709-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="2f709-123">Todas las `open` directivas deben aparecer antes `function` `operation` de cualquier declaración, o `newtype` en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2f709-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="2f709-124">Opcionalmente, puede definir un nombre corto para el espacio de nombres abierto.</span><span class="sxs-lookup"><span data-stu-id="2f709-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="2f709-125">Si se define un nombre corto, debe calificar todos los elementos de ese espacio de nombres por el nombre corto definido.</span><span class="sxs-lookup"><span data-stu-id="2f709-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="2f709-126">Por ejemplo, dada la siguiente declaración de espacio de nombres y las directivas Open,</span><span class="sxs-lookup"><span data-stu-id="2f709-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="2f709-127">Si una operación declarada utiliza una operación `Op` de `Microsoft.Quantum.Intrinsic` , se llama simplemente mediante `Op` .</span><span class="sxs-lookup"><span data-stu-id="2f709-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="2f709-128">Sin embargo, para llamar a una función determinada `Fn` desde `Microsoft.Quantum.Math` , debe llamarlo mediante `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="2f709-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="2f709-129">La `open` Directiva se aplica a todo el bloque de espacio de nombres dentro de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2f709-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="2f709-130">Por lo tanto, si define un espacio de nombres adicional en el mismo Q# archivo que `NS` antes, las operaciones, funciones o tipos definidos en el segundo espacio de nombres no tendrán acceso a nada desde `Microsoft.Quantum.Intrinsic` o `Microsoft.Quantum.Math` a menos que repita las directivas Open.</span><span class="sxs-lookup"><span data-stu-id="2f709-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="2f709-131">Para hacer referencia a un tipo o a invocable definido en otro espacio de nombres que *no* está abierto en el espacio de nombres actual, debe hacer referencia a él mediante su nombre completo.</span><span class="sxs-lookup"><span data-stu-id="2f709-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="2f709-132">Por ejemplo, dada una operación denominada `Op` del `X.Y` espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="2f709-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="2f709-133">Debe hacer referencia a él mediante su nombre completo `X.Y.Op` , a menos que el `X.Y` espacio de nombres se haya abierto anteriormente en el bloque actual.</span><span class="sxs-lookup"><span data-stu-id="2f709-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="2f709-134">Incluso si `X` se abre el espacio de nombres, no es posible hacer referencia a la operación como `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="2f709-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="2f709-135">Si ha definido el nombre corto `Z` de `X.Y` en ese espacio de nombres y archivo, debe hacer referencia a `Op` como `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="2f709-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="2f709-136">Normalmente es mejor incluir un espacio de nombres mediante una `open` Directiva.</span><span class="sxs-lookup"><span data-stu-id="2f709-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="2f709-137">Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.</span><span class="sxs-lookup"><span data-stu-id="2f709-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="2f709-138">Q#sigue las mismas reglas para asignar nombres a otros lenguajes de .NET.</span><span class="sxs-lookup"><span data-stu-id="2f709-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="2f709-139">Sin embargo, no Q# admite referencias relativas a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="2f709-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="2f709-140">Por ejemplo, si el espacio de nombres `a.b` está abierto, una referencia a una operación denominada no se `c.d` resuelve como una operación con el nombre completo *not* `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="2f709-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="2f709-141">Formato</span><span class="sxs-lookup"><span data-stu-id="2f709-141">Formatting</span></span>

<span data-ttu-id="2f709-142">La mayoría de las Q# instrucciones y directivas finalizan con un punto y coma de terminación, `;` .</span><span class="sxs-lookup"><span data-stu-id="2f709-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="2f709-143">Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones (vea la siguiente sección) no requieren un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="2f709-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="2f709-144">La descripción de cada instrucción indica si es necesario el punto y coma de terminación.</span><span class="sxs-lookup"><span data-stu-id="2f709-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="2f709-145">Las instrucciones, como las expresiones, las declaraciones y las directivas, se pueden dividir en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="2f709-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="2f709-146">Evite colocar varias instrucciones en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="2f709-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="2f709-147">Bloques de instrucciones</span><span class="sxs-lookup"><span data-stu-id="2f709-147">Statement Blocks</span></span>

<span data-ttu-id="2f709-148">Q#las instrucciones se agrupan en bloques de instrucciones, que se incluyen entre llaves `{ }` .</span><span class="sxs-lookup"><span data-stu-id="2f709-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="2f709-149">Un bloque de instrucciones comienza con una apertura `{` y termina con un cierre `}` .</span><span class="sxs-lookup"><span data-stu-id="2f709-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="2f709-150">Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.</span><span class="sxs-lookup"><span data-stu-id="2f709-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="2f709-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f709-151">Comments</span></span>

<span data-ttu-id="2f709-152">Los comentarios comienzan con dos barras diagonales, `//` y continúan hasta el final de la línea.</span><span class="sxs-lookup"><span data-stu-id="2f709-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="2f709-153">Un comentario puede aparecer en cualquier parte de un Q# archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="2f709-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="2f709-154">Comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="2f709-154">Documentation Comments</span></span>

<span data-ttu-id="2f709-155">Los comentarios que comienzan con tres barras diagonales, `///` , se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="2f709-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="2f709-156">En ese caso, el compilador los trata como documentación para el tipo definido por el usuario o al que se puede llamar, igual que otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="2f709-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="2f709-157">Dentro de `///` los comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), con distintas partes de la documentación indicada por encabezados con el nombre especial.</span><span class="sxs-lookup"><span data-stu-id="2f709-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="2f709-158">En Markdown, use la `@"<ref target>"` extensión para las operaciones de referencia cruzada, las funciones y los tipos definidos por el usuario en Q# .</span><span class="sxs-lookup"><span data-stu-id="2f709-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="2f709-159">Reemplazar `<ref target>` por el nombre completo del objeto de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2f709-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="2f709-160">Los diferentes motores de documentación también pueden admitir extensiones Markdown adicionales.</span><span class="sxs-lookup"><span data-stu-id="2f709-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="2f709-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f709-161">For example:</span></span>

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

<span data-ttu-id="2f709-162">Los nombres siguientes son válidos como encabezados de comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="2f709-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="2f709-163">**Summary**: un breve resumen del comportamiento de una función u operación, o el propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="2f709-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="2f709-164">El primer párrafo del resumen se usa para la información de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="2f709-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="2f709-165">Debe ser texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="2f709-165">It should be plain text.</span></span>
- <span data-ttu-id="2f709-166">**Descripción**: una descripción del comportamiento de una función u operación, o el propósito de un tipo.</span><span class="sxs-lookup"><span data-stu-id="2f709-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="2f709-167">Juntos, el Resumen y la descripción forman el archivo de documentación generado para la función, la operación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="2f709-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="2f709-168">La descripción admite símbolos y ecuaciones con formato LaTeX en línea.</span><span class="sxs-lookup"><span data-stu-id="2f709-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="2f709-169">**Input**: Descripción de la tupla de entrada para una operación o función.</span><span class="sxs-lookup"><span data-stu-id="2f709-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="2f709-170">Puede contener subsecciones de Markdown adicionales que indican cada elemento de la tupla de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f709-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="2f709-171">**Output**: Descripción de la tupla devuelta por una operación o función.</span><span class="sxs-lookup"><span data-stu-id="2f709-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="2f709-172">**Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2f709-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="2f709-173">**Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.</span><span class="sxs-lookup"><span data-stu-id="2f709-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="2f709-174">**Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.</span><span class="sxs-lookup"><span data-stu-id="2f709-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="2f709-175">**Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.</span><span class="sxs-lookup"><span data-stu-id="2f709-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="2f709-176">**Referencias**: una lista de referencias y citas para el elemento documentado.</span><span class="sxs-lookup"><span data-stu-id="2f709-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f709-177">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2f709-177">Next steps</span></span>

<span data-ttu-id="2f709-178">Obtenga información acerca de [las operaciones y las funciones](xref:microsoft.quantum.guide.operationsfunctions) de Q# .</span><span class="sxs-lookup"><span data-stu-id="2f709-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>