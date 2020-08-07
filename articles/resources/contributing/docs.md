---
title: Documentación de contribución a Microsoft QDK
description: Obtenga información sobre cómo aportar contenido conceptual o de API al conjunto de documentación de Microsoft Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1110f32a6486de1a346b115fa928a098749b6690
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866883"
---
# <a name="improving-documentation"></a><span data-ttu-id="bc552-103">Mejora de la documentación</span><span class="sxs-lookup"><span data-stu-id="bc552-103">Improving Documentation</span></span>

<span data-ttu-id="bc552-104">La documentación del kit de desarrollo de Quantum toma varias formas diferentes, de modo que la información esté disponible para los desarrolladores de Quantum.</span><span class="sxs-lookup"><span data-stu-id="bc552-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="bc552-105">Siguiendo los principios de [documentos como código](https://www.writethedocs.org/guide/docs-as-code/), toda la documentación del kit de desarrollo de Quantum se formatea como código y se administra mediante Git de la misma manera que el código fuente que se usa para crear el kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="bc552-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="bc552-106">En su mayor parte, la documentación de respaldo del código consta de varias formas de [Markdown](https://daringfireball.net/projects/markdown/), un lenguaje para escribir texto con formato enriquecido en un formato de texto sin formato que es fácil de usar en la línea de comandos, en IDE y con control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="bc552-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="bc552-107">De igual forma, adoptamos la biblioteca [MathJax](https://www.mathjax.org/) para permitir el formato de matemáticas en la documentación mediante el lenguaje latex, tal como se detalla más adelante.</span><span class="sxs-lookup"><span data-stu-id="bc552-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="bc552-108">Dicho esto, cada forma de documentación varía ligeramente en los detalles:</span><span class="sxs-lookup"><span data-stu-id="bc552-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="bc552-109">La **documentación conceptual** consta de un conjunto de artículos que se publican en https://docs.microsoft.com/quantum y que describen todo, desde los aspectos básicos de la informática Quantum hasta las especificaciones técnicas de los formatos de intercambio.</span><span class="sxs-lookup"><span data-stu-id="bc552-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="bc552-110">Estos artículos están escritos en [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), una variante de Markdown que se usa para crear conjuntos de documentación enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="bc552-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="bc552-111">La **referencia de API** es un conjunto de páginas para cada Q# función, operación y tipo definido por el usuario, publicadas en https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="bc552-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="bc552-112">Estas páginas documentan las entradas y operaciones en cada una de las llamadas, junto con ejemplos y vínculos a más información.</span><span class="sxs-lookup"><span data-stu-id="bc552-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="bc552-113">La referencia de la API se extrae automáticamente de los pequeños documentos de DFM en Q# el código fuente como parte de cada versión.</span><span class="sxs-lookup"><span data-stu-id="bc552-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="bc552-114">Los archivos **README <!----> . MD** incluidos en cada ejemplo y Kata describen cómo usar ese ejemplo o Kata se usa, lo que cubre y cómo se relaciona con el resto del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="bc552-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="bc552-115">Estos archivos se escriben mediante [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), una alternativa más ligera a DFM que es popular para adjuntar documentación directamente a los repositorios de código.</span><span class="sxs-lookup"><span data-stu-id="bc552-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="bc552-116">Contribución a la documentación conceptual</span><span class="sxs-lookup"><span data-stu-id="bc552-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="bc552-117">Para contribuir a la mejora de la documentación conceptual o del archivo Léame, comienza con una solicitud de incorporación de cambios en [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)o [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), como es adecuado.</span><span class="sxs-lookup"><span data-stu-id="bc552-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="bc552-118">Aquí describiremos más acerca de las solicitudes de incorporación de cambios, pero por ahora hay algunas cosas que es conveniente tener en cuenta a la vez que mejora la documentación:</span><span class="sxs-lookup"><span data-stu-id="bc552-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="bc552-119">Los lectores acuden a la documentación del kit de desarrollo de Quantum desde una amplia gama de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="bc552-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="bc552-120">Todo el mundo de los estudiantes de la escuela alta desea aprender algo nuevo y emocionante a través de un profesorado que realice una investigación de Quantum Computing, debería poder sacar algo de la documentación.</span><span class="sxs-lookup"><span data-stu-id="bc552-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="bc552-121">En la medida de lo posible, no asuma un conocimiento amplio de la parte de los lectores, ya que pueden empezar. Es más útil si puede proporcionar descripciones claras y accesibles, o puede proporcionar vínculos a otros recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bc552-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="bc552-122">Los conjuntos de documentación no se diseñan como libros o documentos, en los que los lectores llegarán a lo que podría parecer "intermedio".</span><span class="sxs-lookup"><span data-stu-id="bc552-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="bc552-123">Por ejemplo, es posible que los motores de búsqueda no sugieran el índice o que un amigo haya enviado un vínculo intentando ayudarlos. Intente ayudar a su lector proporcionando siempre un contexto claro, junto con los vínculos cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="bc552-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="bc552-124">Algunos lectores buscarán instrucciones y definiciones abstractas más útiles, mientras que otros sistemas de lectura funcionan mejor mediante la extrapolación de ejemplos concretos.</span><span class="sxs-lookup"><span data-stu-id="bc552-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="bc552-125">Proporcionar tanto el caso general como los ejemplos específicos pueden ayudar a ambos lectores a sacar el máximo partido de la programación de Quantum.</span><span class="sxs-lookup"><span data-stu-id="bc552-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="bc552-126">Especialmente si también ha escrito el código que se documenta, puede que le resulte obvio que no es evidente para el lector.</span><span class="sxs-lookup"><span data-stu-id="bc552-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="bc552-127">No hay una mejor manera de programar, por lo que, con independencia de lo inteligente o experimentado que sea un lector, no puede adivinar en qué modelos de diseño encontró lo más útil para expresar sus ideas en el código.</span><span class="sxs-lookup"><span data-stu-id="bc552-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="bc552-128">Saber cómo un lector puede esperar hacer uso del código puede ayudar a proporcionar ese contexto.</span><span class="sxs-lookup"><span data-stu-id="bc552-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="bc552-129">Muchos miembros de la comunidad de programación Quantum son investigadores académicos y se reconocen principalmente a través de citas para sus contribuciones a la comunidad.</span><span class="sxs-lookup"><span data-stu-id="bc552-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="bc552-130">Además de ayudar a los lectores a encontrar materiales adicionales, no se olvide de mencionar correctamente las salidas académicas, como documentos, conversaciones, entradas de blog y herramientas de software, que pueden ayudar a los colaboradores académicos a seguir llevando a cabo el mejor trabajo para mejorar la comunidad.</span><span class="sxs-lookup"><span data-stu-id="bc552-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="bc552-131">La comunidad de programación Quantum es una comunidad amplia y maravillosamente diversa.</span><span class="sxs-lookup"><span data-stu-id="bc552-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="bc552-132">El uso de pronombres de género en ejemplos de terceros (por ejemplo, "Si un usuario...,...") puede trabajar para excluir en lugar de incluirlos.</span><span class="sxs-lookup"><span data-stu-id="bc552-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="bc552-133">La Cognizant de los nombres de las personas en citas y vínculos, y de la inclusión correcta de caracteres que no sean ASCII, puede servir para la diversidad de la comunidad mostrando el respeto de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="bc552-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="bc552-134">Del mismo modo, muchas palabras del idioma inglés se usan a menudo de forma Hateful, de modo que su uso en la documentación técnica pueda causar daños tanto a lectores individuales como a la comunidad en gran medida.</span><span class="sxs-lookup"><span data-stu-id="bc552-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="bc552-135">Referencia al código de ejemplo de artículos conceptuales</span><span class="sxs-lookup"><span data-stu-id="bc552-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="bc552-136">Si desea incluir código del [repositorio de ejemplos](https://github.com/Microsoft/Quantum), puede hacerlo mediante un comando de Markdown especial DocFX:</span><span class="sxs-lookup"><span data-stu-id="bc552-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="bc552-137">Este comando importará las líneas 4 a 8 del [ `Game.qs` archivo del `chsh-game` ejemplo](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), y las marcará como Q# código con el fin de resaltar la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="bc552-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="bc552-138">Con este comando, puede evitar la duplicación de código entre los artículos conceptuales y el repositorio de ejemplos, de modo que el código de ejemplo de la documentación esté siempre tan actualizado como sea posible.</span><span class="sxs-lookup"><span data-stu-id="bc552-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="bc552-139">Contribución a las referencias de API</span><span class="sxs-lookup"><span data-stu-id="bc552-139">Contributing to the API References</span></span>

<span data-ttu-id="bc552-140">Para contribuir a una mejora en las referencias de API, es más útil abrir una solicitud de incorporación de cambios directamente en el código que se documenta.</span><span class="sxs-lookup"><span data-stu-id="bc552-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="bc552-141">Cada función, operación o tipo definido por el usuario admite un Comentario de documentación (indicado con `///` en lugar de `//` ).</span><span class="sxs-lookup"><span data-stu-id="bc552-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="bc552-142">Al compilar cada versión del kit de desarrollo de Quantum, estos comentarios se usan para generar la referencia de API en https://docs.microsoft.com/qsharp/api/ , incluidos los detalles sobre las entradas y salidas de cada una de las llamadas, las suposiciones que realiza cada una de ellas y ejemplos de cómo usarlas.</span><span class="sxs-lookup"><span data-stu-id="bc552-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc552-143">Asegúrese de no editar manualmente la documentación de API generada, ya que estos archivos se sobrescriben con cada nueva versión.</span><span class="sxs-lookup"><span data-stu-id="bc552-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="bc552-144">Le agradecemos su contribución a la comunidad y querrá asegurarse de que los cambios continúan para ayudar a los usuarios a publicarse después del lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="bc552-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="bc552-145">Por ejemplo, considere la función `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="bc552-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="bc552-146">Un Comentario de documentación debe ayudar a un usuario a obtener información sobre cómo interpretar `bits` y `oracle` y para qué sirve la función.</span><span class="sxs-lookup"><span data-stu-id="bc552-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="bc552-147">Cada una de estas partes de la información se puede proporcionar al Q# compilador mediante una sección de Markdown con el mismo nombre en el comentario de la documentación.</span><span class="sxs-lookup"><span data-stu-id="bc552-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="bc552-148">En el ejemplo de `ControlledOnBitString` , podríamos escribir algo parecido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc552-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="bc552-149">Puede ver la versión representada del código anterior en la [documentación de la API para la `ControlledOnBitString` función](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="bc552-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="bc552-150">Además de la práctica general de escritura de documentación, al escribir comentarios de documentación de API, le ayuda a tener presentes algunos aspectos:</span><span class="sxs-lookup"><span data-stu-id="bc552-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="bc552-151">El formato de cada comentario de documentación tiene que coincidir con lo que el Q# compilador espera para que la documentación aparezca correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc552-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="bc552-152">Algunas secciones, como `/// # Remarks` permitir contenido de forma libre, mientras que las secciones como la `/// # See Also` sección son más restrictivas.</span><span class="sxs-lookup"><span data-stu-id="bc552-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="bc552-153">Un lector puede leer la documentación de la API en el sitio principal de referencia de API, en el Resumen de cada espacio de nombres, o incluso desde dentro de su IDE mediante el uso de información de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="bc552-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="bc552-154">Asegurarse de que `/// # Summary` no sea más largo que una oración ayuda a su lector a ordenar rápidamente si es necesario leer más o buscar en otro lugar, y puede ayudar a realizar un análisis rápido a través de los resúmenes de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bc552-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="bc552-155">Es posible que la documentación se desenrede mucho más tiempo que el propio código, pero eso es correcto.</span><span class="sxs-lookup"><span data-stu-id="bc552-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="bc552-156">Incluso un pequeño fragmento de código puede tener efectos inesperados en los usuarios que no conocen el contexto en el que existe ese código.</span><span class="sxs-lookup"><span data-stu-id="bc552-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="bc552-157">Al proporcionar ejemplos concretos y explicaciones claras, puede ayudar a los usuarios a hacer el mejor uso del código que están a su disposición.</span><span class="sxs-lookup"><span data-stu-id="bc552-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
