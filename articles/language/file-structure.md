---
title: Estructura del archivo | Microsoft Docs
description: Estructura de archivos de preguntas y respuestas
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821089"
---
# <a name="file-structure"></a><span data-ttu-id="1c94d-103">Estructura de archivos</span><span class="sxs-lookup"><span data-stu-id="1c94d-103">File Structure</span></span>

<span data-ttu-id="1c94d-104">Un archivo de preguntas # consta de una secuencia de declaraciones de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c94d-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="1c94d-105">Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="1c94d-106">Una declaración de espacio de nombres puede contener cualquier número de cada tipo de declaración y en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="1c94d-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="1c94d-107">El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.</span><span class="sxs-lookup"><span data-stu-id="1c94d-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="1c94d-108">En concreto, los comentarios de documentación para un espacio de nombres preceden a la declaración.</span><span class="sxs-lookup"><span data-stu-id="1c94d-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="1c94d-109">Declaraciones de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="1c94d-109">Namespace Declarations</span></span>

<span data-ttu-id="1c94d-110">Un archivo de preguntas # normalmente tendrá exactamente una declaración de espacio de nombres, pero puede tener ninguno (y estar vacío o contener solo comentarios) o puede contener varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c94d-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="1c94d-111">Las declaraciones de espacio de nombres no pueden estar anidadas.</span><span class="sxs-lookup"><span data-stu-id="1c94d-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="1c94d-112">El mismo espacio de nombres se puede declarar en varios archivos Q # que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1c94d-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="1c94d-113">En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.</span><span class="sxs-lookup"><span data-stu-id="1c94d-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="1c94d-114">Una declaración de espacio de nombres consta de la palabra clave `namespace`, seguida del nombre del espacio de nombres, una llave de apertura `{`, las declaraciones contenidas en el espacio de nombres y una llave de cierre `}`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="1c94d-115">Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="1c94d-116">Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Canon` son nombres de espacio de nombres válidos.</span><span class="sxs-lookup"><span data-stu-id="1c94d-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="1c94d-117">Por Convención, los símbolos de un nombre de espacio de nombres se escriben en mayúsculas, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="1c94d-118">Las declaraciones pueden aparecer en cualquier orden en una declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c94d-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="1c94d-119">Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.</span><span class="sxs-lookup"><span data-stu-id="1c94d-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="1c94d-120">Directivas Open</span><span class="sxs-lookup"><span data-stu-id="1c94d-120">Open Directives</span></span>

<span data-ttu-id="1c94d-121">Dentro de un bloque de espacio de nombres, la Directiva `open` se puede usar para importar todos los tipos e Invocables definidos en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.</span><span class="sxs-lookup"><span data-stu-id="1c94d-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="1c94d-122">Tal `open` Directiva consta de la palabra clave `open`, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="1c94d-123">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="1c94d-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="1c94d-124">Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido.</span><span class="sxs-lookup"><span data-stu-id="1c94d-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="1c94d-125">Este nombre corto se define agregando la palabra clave `as` seguido del nombre corto deseado delante del punto y coma en una directiva `open`:</span><span class="sxs-lookup"><span data-stu-id="1c94d-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="1c94d-126">Todas las directivas de `open` deben aparecer antes de cualquier declaración de `function`, `operation`o `newtype` en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c94d-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="1c94d-127">La Directiva `open` se aplica a todo el bloque de espacio de nombres dentro de un archivo.</span><span class="sxs-lookup"><span data-stu-id="1c94d-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="1c94d-128">Declaraciones de tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="1c94d-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="1c94d-129">Q # proporciona una manera para que los usuarios declaren nuevos tipos definidos por el usuario, como se describe en la sección [modelo de Q # type](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="1c94d-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="1c94d-130">Los tipos definidos por el usuario son distintos aunque los tipos base sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="1c94d-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="1c94d-131">En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="1c94d-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="1c94d-132">Una declaración de tipos definidos por el usuario consta de la palabra clave `newtype`, seguida del nombre del tipo definido por el usuario, un `=`, una especificación de tipo válida y un punto y coma de finalización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="1c94d-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1c94d-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="1c94d-134">Cada archivo de código fuente de Q # puede declarar cualquier número de tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="1c94d-135">Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.</span><span class="sxs-lookup"><span data-stu-id="1c94d-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="1c94d-136">No es posible definir dependencias circulares entre tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="1c94d-137">Por lo tanto, los tipos recursivos no son posibles en Q #.</span><span class="sxs-lookup"><span data-stu-id="1c94d-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="1c94d-138">Declaraciones de operación</span><span class="sxs-lookup"><span data-stu-id="1c94d-138">Operation Declarations</span></span>

<span data-ttu-id="1c94d-139">Las operaciones son el núcleo de Q #, aproximadamente análogos a las funciones de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="1c94d-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="1c94d-140">Cada archivo de código fuente de Q # puede definir cualquier número de operaciones.</span><span class="sxs-lookup"><span data-stu-id="1c94d-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="1c94d-141">Los nombres de operación deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de función y tipo.</span><span class="sxs-lookup"><span data-stu-id="1c94d-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="1c94d-142">Las declaraciones de operación se componen de la palabra clave `operation`, seguido del símbolo que es el nombre de la operación, una tupla de identificador con tipo que define los argumentos de la operación, un signo de dos puntos `:`, una anotación de tipo que describe el tipo de resultado de la operación, opcionalmente una anotación con las características de la operación, una llave de apertura `{`, el cuerpo de la declaración de la operación y una llave de cierre final `}`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="1c94d-143">El cuerpo de la declaración de operación se compone de la implementación predeterminada o de una lista de especializaciones.</span><span class="sxs-lookup"><span data-stu-id="1c94d-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="1c94d-144">La implementación predeterminada se puede especificar directamente dentro de la declaración si solo es necesario especificar explícitamente la implementación de la especialización del cuerpo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1c94d-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="1c94d-145">En este caso, una anotación con las características de la operación en la declaración es útil para asegurarse de que el compilador genera automáticamente otras especializaciones basadas en la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="1c94d-146">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c94d-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="1c94d-147">Las características de la operación definen qué tipos de funcs se pueden aplicar a la operación declarada y qué efecto tienen.</span><span class="sxs-lookup"><span data-stu-id="1c94d-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="1c94d-148">Si una operación implementa una transformación unitario, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*.</span><span class="sxs-lookup"><span data-stu-id="1c94d-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="1c94d-149">La existencia de estas especializaciones se puede declarar como parte de la firma de la operación.</span><span class="sxs-lookup"><span data-stu-id="1c94d-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="1c94d-150">El compilador genera la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente.</span><span class="sxs-lookup"><span data-stu-id="1c94d-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="1c94d-151">En el ejemplo anterior, el compilador genera un contiguo, un control y una especialización contigua controlada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="1c94d-152">En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="1c94d-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="1c94d-153">Estas declaraciones de especialización explícita pueden constar de una directiva de generación adecuada que aclare cómo se va a compilar una especialización determinada o una implementación definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="1c94d-154">El código de `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas:</span><span class="sxs-lookup"><span data-stu-id="1c94d-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="1c94d-155">La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="1c94d-156">Si el compilador no puede generar la implementación para una especialización determinada sin instrucciones adicionales, como una directiva de generación más precisa, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.</span><span class="sxs-lookup"><span data-stu-id="1c94d-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="1c94d-157">En el ejemplo anterior, `adjoint invert;` indica que la especialización de la instancia contigua se va a generar invirtiendo la implementación del cuerpo y `controlled adjoint invert;` indica que la especialización contigua controlada se generará invirtiendo la implementación dada de la especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="1c94d-158">Para que una operación admita la aplicación del `Adjoint` o del functor `Controlled`, es necesario `Unit`su tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="1c94d-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="1c94d-159">Declaraciones de especialización explícitas</span><span class="sxs-lookup"><span data-stu-id="1c94d-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="1c94d-160">Las operaciones de Q # pueden contener las siguientes declaraciones de especialización explícita:</span><span class="sxs-lookup"><span data-stu-id="1c94d-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="1c94d-161">La especialización `body` especifica la implementación de la operación sin ningún funcón aplicado.</span><span class="sxs-lookup"><span data-stu-id="1c94d-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="1c94d-162">La especialización `adjoint` especifica la implementación de la operación con la `Adjoint` funcda aplicada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="1c94d-163">La especialización `controlled` especifica la implementación de la operación con la `Controlled` funcda aplicada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="1c94d-164">La especialización de `controlled adjoint` especifica la implementación de la operación con los funcdores `Adjoint` y `Controlled` aplicados.</span><span class="sxs-lookup"><span data-stu-id="1c94d-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="1c94d-165">Esta especialización también puede denominarse `adjoint controlled`, ya que los dos funcs se desactivan.</span><span class="sxs-lookup"><span data-stu-id="1c94d-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="1c94d-166">Una especialización de operación consta de la etiqueta de especialización (por ejemplo, `body`, o `adjoint`, etc.) seguida de una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c94d-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="1c94d-167">Una declaración explícita tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="1c94d-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="1c94d-168">Una directiva que indica al compilador cómo generar la especialización, una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c94d-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="1c94d-169">`intrinsic`, que indica que la especialización la proporciona la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="1c94d-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="1c94d-170">`distribute`, que se puede usar con las especializaciones `controlled` y `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="1c94d-171">Cuando se usa con `controlled`, indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la `body`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="1c94d-172">Cuando se usa con `controlled adjoint`, indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la especialización de `adjoint`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="1c94d-173">`invert`, que indica que el compilador debe calcular la `adjoint` especialización invirtiendo el `body`, es decir, invertir el orden de las operaciones y aplicar el objeto contiguo a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="1c94d-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="1c94d-174">Cuando se usa con `adjoint controlled`, esto indica que el compilador debe calcular la especialización invirtiendo la `controlled` especialización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="1c94d-175">`self`, para indicar que la especialización contigua es igual que la especialización `body`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="1c94d-176">Esto es válido para las especializaciones `adjoint` y `adjoint controlled`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="1c94d-177">Por `adjoint controlled`, `self` implica que la especialización de `adjoint controlled` es igual que la especialización de `controlled`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="1c94d-178">`auto`, para indicar que el compilador debe seleccionar la Directiva adecuada que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="1c94d-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="1c94d-179">no se puede usar `auto` para la especialización de `body`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="1c94d-180">Las directivas y `auto` requieren un `;`de punto y coma de cierre.</span><span class="sxs-lookup"><span data-stu-id="1c94d-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="1c94d-181">La Directiva `auto` se resuelve como la Directiva de generación siguiente si se proporciona una declaración explícita de la `body`:</span><span class="sxs-lookup"><span data-stu-id="1c94d-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="1c94d-182">La especialización de `adjoint` se genera de acuerdo con la Directiva `invert`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="1c94d-183">La especialización de `controlled` se genera de acuerdo con la Directiva `distribute`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="1c94d-184">La especialización de `adjoint controlled` se genera de acuerdo con la Directiva `invert` si se proporciona una declaración explícita para `controlled`, pero no una para `adjoint`, y `distribute` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="1c94d-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="1c94d-185">Si una operación es autocontiguo, especifique explícitamente el o la especialización de la instancia de la instancia de la Directiva de generación `self` para permitir que el compilador haga uso de esa información con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="1c94d-186">Una declaración de especialización que contiene una implementación definida por el usuario consta de una tupla de argumento seguida de un bloque de instrucciones con el código de Q # que implementa la especialización.</span><span class="sxs-lookup"><span data-stu-id="1c94d-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="1c94d-187">En la lista de argumentos, `...` se utiliza para representar los argumentos declarados para la operación en su conjunto.</span><span class="sxs-lookup"><span data-stu-id="1c94d-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="1c94d-188">Por `body` y `adjoint`, la lista de argumentos siempre debe estar `(...)`; por `controlled` y `adjoint controlled`, la lista de argumentos debe ser un símbolo que represente la matriz de qubits de control, seguida de `...`, entre paréntesis. por ejemplo, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="1c94d-189">Si es necesario declarar explícitamente una o más especializaciones además del cuerpo predeterminado, la implementación del cuerpo predeterminado debe ajustarse también en una declaración de especialización adecuada:</span><span class="sxs-lookup"><span data-stu-id="1c94d-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="1c94d-190">Contiguo</span><span class="sxs-lookup"><span data-stu-id="1c94d-190">Adjoint</span></span>

<span data-ttu-id="1c94d-191">El método contiguo de una operación especifica cómo se implementa la transposición de conjugada compleja de la operación, es decir, cómo actúa la operación cuando se ejecuta en modo inverso.</span><span class="sxs-lookup"><span data-stu-id="1c94d-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="1c94d-192">Es válido especificar una operación sin el anexado. por ejemplo, las operaciones de medición no tienen ningún operador contiguo porque no se pueden invertir.</span><span class="sxs-lookup"><span data-stu-id="1c94d-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="1c94d-193">Una operación es compatible con el `Adjoint` functor si su declaración contiene una declaración implícita o explícita de una especialización de unjoin.</span><span class="sxs-lookup"><span data-stu-id="1c94d-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="1c94d-194">Una especialización contigua controlada explícitamente declarada implica la existencia de una especialización del mismo.</span><span class="sxs-lookup"><span data-stu-id="1c94d-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="1c94d-195">En el caso de una operación cuyo cuerpo contenga bucles de repetición hasta la correcta, instrucciones SET, medidas, instrucciones Return o llamadas a otras operaciones que no admiten el `Adjoint` functor, no es posible generar automáticamente una especialización de la función de `invert` o `auto`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="1c94d-196">Regula</span><span class="sxs-lookup"><span data-stu-id="1c94d-196">Controlled</span></span>

<span data-ttu-id="1c94d-197">La versión controlada de una operación especifica cómo se implementa una versión controlada por Quantum de la operación, es decir, cómo actúa una operación cuando se aplica en el estado de un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="1c94d-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="1c94d-198">En la sección [controlada](xref:microsoft.quantum.language.type-model#controlled) se proporciona una descripción más completa.</span><span class="sxs-lookup"><span data-stu-id="1c94d-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="1c94d-199">Es válido especificar una operación sin ninguna versión controlada; por ejemplo, las operaciones de medición no tienen ninguna versión controlada porque no se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="1c94d-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="1c94d-200">Una operación admite el `Controlled` functor si y solo si su declaración contiene una declaración implícita o explícita de una especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="1c94d-201">Una especialización contigua controlada explícitamente declarada implica la existencia de una especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="1c94d-202">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no admitan el `Controlled` functor, no es posible generar automáticamente una especialización controlada después de la Directiva `distribute` o `auto`.</span><span class="sxs-lookup"><span data-stu-id="1c94d-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="1c94d-203">Contiguo controlado</span><span class="sxs-lookup"><span data-stu-id="1c94d-203">Controlled Adjoint</span></span>

<span data-ttu-id="1c94d-204">La versión de la contigua controlada de una operación especifica cómo se implementa una versión controlada por Quantum del método contiguo de la operación.</span><span class="sxs-lookup"><span data-stu-id="1c94d-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="1c94d-205">Es válido especificar una operación sin ninguna versión contigua controlada; por ejemplo, las operaciones de medición no tienen ninguna versión contigua controlada porque no se pueden controlar ni invertir.</span><span class="sxs-lookup"><span data-stu-id="1c94d-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="1c94d-206">Es necesario que exista una especialización del mismo bajo controlada para una operación si y solo si hay un Join y una especialización controlada.</span><span class="sxs-lookup"><span data-stu-id="1c94d-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="1c94d-207">En ese caso, se infiere la existencia de la especialización contigua controlada y el compilador genera una especialización adecuada si no se ha definido explícitamente ninguna implementación.</span><span class="sxs-lookup"><span data-stu-id="1c94d-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="1c94d-208">En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no tienen una versión de contigua controlada, la generación automática de una especialización de la función de `invert`, `distribute` o `auto` no es posible.</span><span class="sxs-lookup"><span data-stu-id="1c94d-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="1c94d-209">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1c94d-209">Examples</span></span>

<span data-ttu-id="1c94d-210">Una declaración de operación podría ser tan simple como la siguiente, que define la operación Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="1c94d-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="1c94d-211">A continuación se define la operación de teletransportar.</span><span class="sxs-lookup"><span data-stu-id="1c94d-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="1c94d-212">Declaraciones de función</span><span class="sxs-lookup"><span data-stu-id="1c94d-212">Function Declarations</span></span>

<span data-ttu-id="1c94d-213">Las funciones son rutinas meramente clásicas en Q #.</span><span class="sxs-lookup"><span data-stu-id="1c94d-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="1c94d-214">Cada archivo de código fuente de Q # puede definir cualquier número de funciones.</span><span class="sxs-lookup"><span data-stu-id="1c94d-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="1c94d-215">Una declaración de función consta de la palabra clave `function`, seguida del símbolo que es el nombre de la función, una tupla de identificador con tipo, una anotación de tipo que describe el tipo de valor devuelto de la función y un bloque de instrucciones que describe la implementación de la función.</span><span class="sxs-lookup"><span data-stu-id="1c94d-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="1c94d-216">El bloque de instrucciones que define una función debe incluirse en `{` y `}` como cualquier otro bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c94d-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="1c94d-217">Los nombres de función deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y tipo.</span><span class="sxs-lookup"><span data-stu-id="1c94d-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="1c94d-218">Las funciones no pueden asignar o tomar prestado qubits ni llamar a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="1c94d-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="1c94d-219">La aplicación parcial de las operaciones o el paso de los valores con tipo de operación es correcta.</span><span class="sxs-lookup"><span data-stu-id="1c94d-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="1c94d-220">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="1c94d-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
