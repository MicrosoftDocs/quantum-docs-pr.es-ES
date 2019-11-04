---
title: 'Guía de estilo de Q # | Microsoft Docs'
description: Guía de estilo de preguntas y respuestas
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183852"
---
# <a name="q-style-guide"></a><span data-ttu-id="86b3c-103">Guía de estilo de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="86b3c-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="86b3c-104">Convenciones generales</span><span class="sxs-lookup"><span data-stu-id="86b3c-104">General Conventions</span></span> ##

<span data-ttu-id="86b3c-105">Las convenciones sugeridas en esta guía están pensadas para facilitar la lectura y comprensión de los programas y las bibliotecas escritos en preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-106">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-106">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-107">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-107">We suggest:</span></span>

- <span data-ttu-id="86b3c-108">No ignore nunca una Convención a menos que lo haga de forma intencionada con el fin de proporcionar código más legible y comprensible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="86b3c-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-109">Examples</span></span>](#tab/examples)

***

## <a name="naming-conventions"></a><span data-ttu-id="86b3c-110">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="86b3c-110">Naming Conventions</span></span> ##

<span data-ttu-id="86b3c-111">Al ofrecer el kit de desarrollo de Quantum, nos esforzamos por los nombres de función y de operación que ayudan a los desarrolladores de Quantum a escribir programas que son fáciles de leer y que minimizan la sorpresa.</span><span class="sxs-lookup"><span data-stu-id="86b3c-111">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="86b3c-112">Una parte importante de esto es que, cuando se eligen nombres para funciones, operaciones y tipos, se establece el *vocabulario* que los programadores usan para expresar los conceptos de Quantum. con nuestras opciones, nos ayudaremos o entorpeceremos su esfuerzo para comunicarse claramente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-112">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="86b3c-113">Esto nos da la responsabilidad de asegurarse de que los nombres que presentamos ofrecen una claridad en lugar de la ocultación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-113">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="86b3c-114">En esta sección, detallamos cómo se cumple esta obligación en términos de instrucciones explícitas que nos ayudan a hacer lo mejor en la comunidad de desarrollo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-114">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="86b3c-115">Operaciones y funciones</span><span class="sxs-lookup"><span data-stu-id="86b3c-115">Operations and Functions</span></span> ###

<span data-ttu-id="86b3c-116">Una de las primeras cosas que debe establecer un nombre es si un símbolo determinado representa una función o una operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-116">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="86b3c-117">La diferencia entre las funciones y las operaciones es fundamental para entender cómo se comporta un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="86b3c-117">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="86b3c-118">Para comunicar la distinción entre las funciones y las operaciones con los usuarios, confiamos en que las operaciones de Quantum de los modelos Q # usan efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="86b3c-118">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="86b3c-119">Es decir, una operación *realiza* alguna acción.</span><span class="sxs-lookup"><span data-stu-id="86b3c-119">That is, an operation *does* something.</span></span>

<span data-ttu-id="86b3c-120">Por el contrario, las funciones describen las relaciones matemáticas entre los datos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-120">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="86b3c-121">La expresión `Sin(PI() / 2.0)` *es* `1.0`y no implica nada sobre el estado de un programa o de su qubits.</span><span class="sxs-lookup"><span data-stu-id="86b3c-121">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="86b3c-122">Resumen, las operaciones realizan cosas mientras que las funciones son cosas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-122">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="86b3c-123">Esta distinción sugiere que denominamos operaciones como verbos y funciones como nombres.</span><span class="sxs-lookup"><span data-stu-id="86b3c-123">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="86b3c-124">Cuando se declara un tipo definido por el usuario, una nueva función que crea instancias de ese tipo se define implícitamente al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-124">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="86b3c-125">Desde esa perspectiva, los tipos definidos por el usuario se deben denominar nombres para que el propio tipo y la función constructora tengan nombres coherentes.</span><span class="sxs-lookup"><span data-stu-id="86b3c-125">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="86b3c-126">Cuando sea razonable, asegúrese de que los nombres de operación comienzan por verbos que indican claramente el efecto que realiza la operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-126">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="86b3c-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86b3c-127">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="86b3c-128">Un caso que merece mención especial es cuando una operación toma otra operación como entrada y la llama.</span><span class="sxs-lookup"><span data-stu-id="86b3c-128">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="86b3c-129">En tales casos, la acción realizada por la operación de entrada no está clara cuando se define la operación externa, de modo que el verbo derecho no se borra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-129">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="86b3c-130">Se recomienda el `Apply`de verbo, como en `ApplyIf`, `ApplyToEach`y `ApplyToFirst`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-130">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="86b3c-131">Otros verbos también pueden resultar útiles en este caso, como en `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-131">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="86b3c-132">Verbo</span><span class="sxs-lookup"><span data-stu-id="86b3c-132">Verb</span></span> | <span data-ttu-id="86b3c-133">Efecto esperado</span><span class="sxs-lookup"><span data-stu-id="86b3c-133">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="86b3c-134">Solicitar</span><span class="sxs-lookup"><span data-stu-id="86b3c-134">Apply</span></span> | <span data-ttu-id="86b3c-135">Se llama a una operación que se proporciona como entrada.</span><span class="sxs-lookup"><span data-stu-id="86b3c-135">An operation provided as input is called</span></span> |
| <span data-ttu-id="86b3c-136">Declarar</span><span class="sxs-lookup"><span data-stu-id="86b3c-136">Assert</span></span> | <span data-ttu-id="86b3c-137">Un simulador comprueba una hipótesis sobre el resultado de una posible medida Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-137">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="86b3c-138">Presupuesto</span><span class="sxs-lookup"><span data-stu-id="86b3c-138">Estimate</span></span> | <span data-ttu-id="86b3c-139">Se devuelve un valor clásico que representa una estimación dibujada a partir de una o más medidas</span><span class="sxs-lookup"><span data-stu-id="86b3c-139">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="86b3c-140">Measure</span><span class="sxs-lookup"><span data-stu-id="86b3c-140">Measure</span></span> | <span data-ttu-id="86b3c-141">Se realiza una medición de cuanto y el resultado se devuelve al usuario.</span><span class="sxs-lookup"><span data-stu-id="86b3c-141">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="86b3c-142">Preparativos</span><span class="sxs-lookup"><span data-stu-id="86b3c-142">Prepare</span></span> | <span data-ttu-id="86b3c-143">Un registro determinado de qubits se inicializa en un estado determinado.</span><span class="sxs-lookup"><span data-stu-id="86b3c-143">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="86b3c-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86b3c-144">Sample</span></span> | <span data-ttu-id="86b3c-145">Un valor clásico se devuelve de forma aleatoria desde alguna distribución</span><span class="sxs-lookup"><span data-stu-id="86b3c-145">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="86b3c-146">En el caso de las funciones, se recomienda evitar el uso de verbos en favor de los nombres comunes (vea las instrucciones sobre los nombres adecuados a continuación) o adjetivos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-146">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="86b3c-147">En concreto, en casi todos los casos, se recomienda usar los participles anteriores, donde corresponda para indicar que un nombre de función está conectado fuertemente a una acción o efecto secundario en otro lugar de un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-147">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="86b3c-148">Por ejemplo, `ControlledOnInt` usa el formulario participio de la parte del verbo "control" para indicar que la función actúa como adjetivo para modificar su argumento.</span><span class="sxs-lookup"><span data-stu-id="86b3c-148">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="86b3c-149">Este nombre tiene la ventaja adicional de buscar coincidencias con la semántica del functor integrada `Controlled`, como se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="86b3c-149">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="86b3c-150">Del mismo modo, los nombres de _agente_ se pueden usar para construir nombres de función y UDT a partir de los nombres de operación, como en el caso del nombre `Encoder` para un UDT que esté fuertemente asociado a `Encode`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-150">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-151">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-151">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-152">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-152">We suggest:</span></span>

- <span data-ttu-id="86b3c-153">Usar verbos para nombres de operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-153">Use verbs for operation names.</span></span>
- <span data-ttu-id="86b3c-154">Utilice sustantivos o adjetivos para los nombres de función.</span><span class="sxs-lookup"><span data-stu-id="86b3c-154">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="86b3c-155">Utilice sustantivos para los atributos y tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="86b3c-155">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="86b3c-156">En el caso de todos los nombres a los que se puede llamar, use `CamelCase` en preferencias fuertes para `pascalCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-156">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="86b3c-157">En concreto, asegúrese de que los nombres que se puedan llamar comienzan con letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-157">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="86b3c-158">En el caso de todas las variables locales, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-158">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="86b3c-159">En concreto, asegúrese de que las variables locales comienzan con letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-159">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="86b3c-160">Evite el uso de subrayados `_` en los nombres de función y de operación; Cuando se necesiten niveles adicionales de jerarquía, use espacios de nombres y alias de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="86b3c-160">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-161">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-162">name</span><span class="sxs-lookup"><span data-stu-id="86b3c-162">Name</span></span> | <span data-ttu-id="86b3c-163">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-163">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="86b3c-164">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-164">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="86b3c-165">Desactive el uso de un verbo ("Reflect") para indicar el efecto de la operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-165">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="86b3c-166">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-166">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="86b3c-167">El uso de la frase de nombre sugiere la función, en lugar de la operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-167">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="86b3c-168">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-168">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="86b3c-169">El uso de `snake_case` de la notación de Q #.</span><span class="sxs-lookup"><span data-stu-id="86b3c-169">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="86b3c-170">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-170">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="86b3c-171">El uso de un carácter de subrayado interno al nombre de la operación sirve de notación de Q #.</span><span class="sxs-lookup"><span data-stu-id="86b3c-171">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="86b3c-172">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-172">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="86b3c-173">El uso de la frase de nombre sugiere que la función devuelve una operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-173">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="86b3c-174">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-174">☑</span></span> | `function EqualityFact` | <span data-ttu-id="86b3c-175">Desactive el uso de sustantivo ("Fact") para indicar que se trata de una función, mientras que el adjetivo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-175">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="86b3c-176">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-176">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="86b3c-177">El uso de verbo ("Get") sugiere que se trata de una operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-177">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="86b3c-178">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-178">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="86b3c-179">El uso de la frase se refiere claramente al resultado de llamar al constructor UDT.</span><span class="sxs-lookup"><span data-stu-id="86b3c-179">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="86b3c-180">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-180">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="86b3c-181">El uso de la frase verbal sugiere que el constructor UDT es una operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-181">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="86b3c-182">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-182">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="86b3c-183">El uso de nombre de frase comunica el uso del atributo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-183">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="86b3c-184">Abreviaturas y abreviaturas</span><span class="sxs-lookup"><span data-stu-id="86b3c-184">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="86b3c-185">A pesar de los consejos anteriores, hay muchas formas de taquigrafía que ven un uso común y generalizado en la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-185">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="86b3c-186">Se recomienda usar una abreviatura común y existente donde exista, especialmente para las operaciones que son intrínsecas al funcionamiento de un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="86b3c-186">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="86b3c-187">Por ejemplo, elegimos el nombre `X` en lugar de `ApplyX`y `Rz` en lugar de `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-187">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="86b3c-188">Cuando se usa esta forma abreviada, los nombres de operación deben estar en mayúsculas (por ejemplo: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-188">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="86b3c-189">Es necesario tener cuidado al aplicar esta Convención en el caso de acrónimos de uso frecuente y siglas como "QFT" para "transformación de Fourier de Quantum".</span><span class="sxs-lookup"><span data-stu-id="86b3c-189">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="86b3c-190">Sugerimos las siguientes convenciones generales de .NET para el uso de acrónimos y siglas en nombres completos, lo que prescribe:</span><span class="sxs-lookup"><span data-stu-id="86b3c-190">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="86b3c-191">los acrónimos de dos letras y siglas se denominan en mayúsculas (por ejemplo: `BE` para "Big-endian").</span><span class="sxs-lookup"><span data-stu-id="86b3c-191">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="86b3c-192">todos los acrónimos más largos y siglas se denominan en `CamelCase` (por ejemplo: `Qft` para "transformación de Fourier de Quantum")</span><span class="sxs-lookup"><span data-stu-id="86b3c-192">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="86b3c-193">Por lo tanto, una operación que implementa QFT podría llamarse `QFT` como una abreviatura o escribirse como `ApplyQft`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-193">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="86b3c-194">En el caso de las operaciones y funciones especialmente utilizadas, puede ser conveniente proporcionar un nombre abreviado como _alias_ para una forma más larga:</span><span class="sxs-lookup"><span data-stu-id="86b3c-194">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-195">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-195">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-196">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-196">We suggest:</span></span>

- <span data-ttu-id="86b3c-197">Considere la posibilidad de usar nombres abreviados comúnmente aceptados y ampliamente utilizados cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="86b3c-197">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="86b3c-198">Use mayúsculas para abreviar.</span><span class="sxs-lookup"><span data-stu-id="86b3c-198">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="86b3c-199">Use mayúsculas para acrónimos cortos (dos letras) y siglas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-199">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="86b3c-200">Use `CamelCase` para acrónimos más largos (tres o más letras) y siglas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-200">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-201">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-201">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-202">name</span><span class="sxs-lookup"><span data-stu-id="86b3c-202">Name</span></span> | <span data-ttu-id="86b3c-203">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-203">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="86b3c-204">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-204">☑</span></span> | `X` | <span data-ttu-id="86b3c-205">Abreviatura bien entendida para "aplicar una transformación de $X $"</span><span class="sxs-lookup"><span data-stu-id="86b3c-205">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="86b3c-206">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-206">☑</span></span> | `CNOT` | <span data-ttu-id="86b3c-207">Abreviatura bien entendida para "controlado"</span><span class="sxs-lookup"><span data-stu-id="86b3c-207">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="86b3c-208">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-208">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="86b3c-209">La abreviatura no debe estar en `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-209">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="86b3c-210">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-210">☑</span></span> | `ApplyQft` | <span data-ttu-id="86b3c-211">El inicio común "QFT" aparece como parte de un nombre de formato largo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-211">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="86b3c-212">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-212">☑</span></span> | `QFT` | <span data-ttu-id="86b3c-213">El inicio común "QFT" aparece como parte de un nombre abreviado.</span><span class="sxs-lookup"><span data-stu-id="86b3c-213">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="86b3c-214">Nombres correctos en nombres</span><span class="sxs-lookup"><span data-stu-id="86b3c-214">Proper Nouns in Names</span></span> ###

<span data-ttu-id="86b3c-215">Mientras que en la física es habitual nombrar cosas después de que la primera persona publique sobre ellas, la mayoría de los Physicists no están familiarizados con los nombres de todos y el historial.</span><span class="sxs-lookup"><span data-stu-id="86b3c-215">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="86b3c-216">Confiar demasiado en las convenciones de nomenclatura de la física puede, por tanto, imponer una barrera importante a la entrada, ya que los usuarios de otros terrenos deben aprender un gran número de nombres aparentemente opacos con el fin de usar operaciones y conceptos comunes.</span><span class="sxs-lookup"><span data-stu-id="86b3c-216">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="86b3c-217">Por lo tanto, se recomienda que, siempre que sea razonable, los nombres comunes que describen un concepto se adopten en una buena preferencia con los nombres adecuados que describen el historial de publicaciones de un concepto.</span><span class="sxs-lookup"><span data-stu-id="86b3c-217">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="86b3c-218">Como ejemplo concreto, las operaciones de intercambio y control de subestado que se controlan a menudo se denominan "Fredkin" y "Toffoli" en la literatura académica, pero se identifican en Q # principalmente como `CSWAP` y `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-218">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="86b3c-219">En ambos casos, los comentarios de la documentación de la API proporcionan nombres de sinónimos basados en nombres adecuados, junto con todas las citas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-219">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="86b3c-220">Esta preferencia es especialmente importante dado que el uso de los nombres adecuados siempre será necesario: Q # sigue la tradición establecida por muchos lenguajes clásico, por ejemplo, y hace referencia a `Bool` tipos en referencia a la lógica booleana, que a su vez se denomina en honor de George bool.</span><span class="sxs-lookup"><span data-stu-id="86b3c-220">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="86b3c-221">Unos pocos conceptos de Quantum se denominan de forma similar, incluido el tipo de `Pauli` integrado en el lenguaje de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-221">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="86b3c-222">Al minimizar el uso de los nombres adecuados en los casos en los que no es esencial, se reduce el impacto en el que no se pueden evitar razonablemente los nombres adecuados.</span><span class="sxs-lookup"><span data-stu-id="86b3c-222">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-223">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-223">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="86b3c-224">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-224">We suggest:</span></span>

- <span data-ttu-id="86b3c-225">Evite el uso de nombres propios en los nombres.</span><span class="sxs-lookup"><span data-stu-id="86b3c-225">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-226">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-226">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="86b3c-227">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="86b3c-227">Type Conversions</span></span> ###

<span data-ttu-id="86b3c-228">Como Q # es un lenguaje fuertemente tipado y con tipos estáticos, un valor de un tipo solo se puede usar como un valor de otro tipo mediante una llamada explícita a una función de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-228">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="86b3c-229">Esto contrasta con los lenguajes que permiten a los valores cambiar tipos de forma implícita (por ejemplo: promoción de tipos) o a través de la conversión.</span><span class="sxs-lookup"><span data-stu-id="86b3c-229">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="86b3c-230">Como resultado, las funciones de conversión de tipos desempeñan un papel importante en el desarrollo de la biblioteca de Q # y constituyen una de las decisiones más frecuentes sobre la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="86b3c-230">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="86b3c-231">Sin embargo, tenemos en cuenta que, dado que las conversiones de tipo siempre son _deterministas_, se pueden escribir como funciones y, por lo tanto, se incluyen en el Consejo anterior.</span><span class="sxs-lookup"><span data-stu-id="86b3c-231">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="86b3c-232">En concreto, se recomienda que las funciones de conversión de tipos nunca se denominen como verbos (por ejemplo, `ConvertToX`) o frases de preposicional de adverbio (`ToX`), pero se deben denominar frases de preposicional de adjetivo que indiquen los tipos de origen y destino (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-232">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="86b3c-233">Al enumerar los tipos de matriz en los nombres de funciones de conversión de tipos, se recomienda el `Arr`abreviado.</span><span class="sxs-lookup"><span data-stu-id="86b3c-233">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="86b3c-234">Salvo en circunstancias excepcionales, se recomienda asignar un nombre a todas las funciones de conversión de tipos mediante `As` para que se puedan identificar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-234">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-235">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-235">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-236">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-236">We suggest:</span></span>

- <span data-ttu-id="86b3c-237">Si una función convierte un valor de tipo `X` en un valor de tipo `Y`, use el nombre `AsY` o `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-237">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-238">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-238">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-239">name</span><span class="sxs-lookup"><span data-stu-id="86b3c-239">Name</span></span> | <span data-ttu-id="86b3c-240">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-240">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="86b3c-241">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-241">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="86b3c-242">La preposición "to" da como resultado una frase verbal, que indica una operación y no una función.</span><span class="sxs-lookup"><span data-stu-id="86b3c-242">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="86b3c-243">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-243">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="86b3c-244">El tipo de entrada no está claro en el nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="86b3c-244">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="86b3c-245">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-245">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="86b3c-246">Los tipos de entrada y salida aparecen en el orden equivocado.</span><span class="sxs-lookup"><span data-stu-id="86b3c-246">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="86b3c-247">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-247">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="86b3c-248">Tanto los tipos de entrada como los de salida están claros.</span><span class="sxs-lookup"><span data-stu-id="86b3c-248">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="86b3c-249">Nombres privados o internos</span><span class="sxs-lookup"><span data-stu-id="86b3c-249">Private or Internal Names</span></span> ###

<span data-ttu-id="86b3c-250">En muchos casos, un nombre está pensado exclusivamente para usarse internamente en una biblioteca o proyecto y no es una parte garantizada de la API ofrecida por una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="86b3c-250">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="86b3c-251">Resulta útil indicar claramente que este es el caso cuando se asignan nombres a funciones y operaciones para que las dependencias accidentales del código solo interno se hagan obvias.</span><span class="sxs-lookup"><span data-stu-id="86b3c-251">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="86b3c-252">Si una operación o función no está pensada para su uso directo, sino que debe ser usada por una función que admita la coincidencia que actúa por aplicación parcial, considere la posibilidad de usar un nombre que empiece por `_` para la que se puede llamar parcialmente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-252">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-253">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-253">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-254">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-254">We suggest:</span></span>

- <span data-ttu-id="86b3c-255">Cuando una función, una operación o un tipo definido por el usuario no forma parte de la API pública para un programa o biblioteca de Q #, asegúrese de que su nombre comienza con un carácter de subrayado inicial (`_`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-255">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-256">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-256">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-257">name</span><span class="sxs-lookup"><span data-stu-id="86b3c-257">Name</span></span> | <span data-ttu-id="86b3c-258">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-258">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="86b3c-259">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-259">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="86b3c-260">El carácter de subrayado `_` no debe aparecer al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="86b3c-260">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="86b3c-261">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-261">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="86b3c-262">El carácter de subrayado `_` al principio indica claramente que esta operación solo es para uso interno.</span><span class="sxs-lookup"><span data-stu-id="86b3c-262">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="86b3c-263">Las</span><span class="sxs-lookup"><span data-stu-id="86b3c-263">Variants</span></span> ###

<span data-ttu-id="86b3c-264">Aunque es posible que esta limitación no se conserve en versiones futuras de Q #, es actualmente el caso de que a menudo existan grupos de operaciones o funciones relacionadas que se diferencian por los inconvenientes que admiten sus entradas, o por los tipos concretos de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-264">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="86b3c-265">Estos grupos se pueden distinguir con el mismo nombre de raíz, seguido de una o dos letras que indican su variante.</span><span class="sxs-lookup"><span data-stu-id="86b3c-265">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="86b3c-266">Sufijo</span><span class="sxs-lookup"><span data-stu-id="86b3c-266">Suffix</span></span> | <span data-ttu-id="86b3c-267">Significado</span><span class="sxs-lookup"><span data-stu-id="86b3c-267">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="86b3c-268">Se espera que la entrada sea compatible con `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="86b3c-268">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="86b3c-269">Se espera que la entrada sea compatible con `Controlled`</span><span class="sxs-lookup"><span data-stu-id="86b3c-269">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="86b3c-270">Se espera que la entrada admita `Controlled` y `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="86b3c-270">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="86b3c-271">La entrada o las entradas son del tipo `Int`</span><span class="sxs-lookup"><span data-stu-id="86b3c-271">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="86b3c-272">La entrada o las entradas son del tipo `Double`</span><span class="sxs-lookup"><span data-stu-id="86b3c-272">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="86b3c-273">La entrada o las entradas son del tipo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="86b3c-273">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-274">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-274">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-275">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-275">We suggest:</span></span>

- <span data-ttu-id="86b3c-276">Si una función u operación no está relacionada con funciones u operaciones similares por los tipos y la compatibilidad con las entradas de las entradas, no use un sufijo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-276">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="86b3c-277">Si una función u operación está relacionada con funciones u operaciones similares según los tipos y la compatibilidad con las entradas más inactivas, use los sufijos que se indican en la tabla anterior para distinguir las variantes.</span><span class="sxs-lookup"><span data-stu-id="86b3c-277">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-278">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-278">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="86b3c-279">Argumentos y variables</span><span class="sxs-lookup"><span data-stu-id="86b3c-279">Arguments and Variables</span></span> ###

<span data-ttu-id="86b3c-280">Un objetivo clave del código de preguntas y respuestas para una función u operación es que sea fácil de leer y comprender.</span><span class="sxs-lookup"><span data-stu-id="86b3c-280">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="86b3c-281">Del mismo modo, los nombres de las entradas y los argumentos de tipo deben comunicar cómo se usará una función o un argumento una vez proporcionado.</span><span class="sxs-lookup"><span data-stu-id="86b3c-281">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-282">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-282">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-283">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-283">We suggest:</span></span>

- <span data-ttu-id="86b3c-284">En el caso de todos los nombres de variable y de entrada, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-284">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="86b3c-285">Los nombres de entrada deben ser descriptivos; Evite los nombres de uno o dos letras siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="86b3c-285">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="86b3c-286">Las operaciones y funciones que aceptan exactamente un argumento de tipo deben indicar que el argumento de tipo se `T` cuando su rol es obvio.</span><span class="sxs-lookup"><span data-stu-id="86b3c-286">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="86b3c-287">Si una función u operación toma varios argumentos de tipo o si el rol de un solo argumento de tipo no es obvio, considere la posibilidad de usar una palabra corta en mayúsculas precedida por `T` (por ejemplo: `TOutput`) para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-287">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="86b3c-288">No incluya nombres de tipo en los nombres de argumento y variable; Esta información puede ser proporcionada por el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-288">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="86b3c-289">Denota los tipos escalares por sus nombres literales (`flagQubit`) y los tipos de matriz en plural (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-289">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="86b3c-290">En el caso de las matrices de qubits en particular, considere la posibilidad de que estos tipos se denotan por `Register` donde el nombre hace referencia a una secuencia de qubits que están estrechamente relacionadas de algún modo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-290">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="86b3c-291">Las variables que se usan como índices en matrices deben comenzar con `idx` y deben ser singulares (por ejemplo: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-291">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="86b3c-292">En concreto, evite fuertemente el uso de nombres de variable de una sola letra como índices; considere la posibilidad de usar `idx` como mínimo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-292">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="86b3c-293">Las variables que se usan para contener longitudes de matrices deben comenzar con `n` y deben ser plurales (por ejemplo: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-293">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-294">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-294">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="86b3c-295">Tipo definido por el usuario denominado items</span><span class="sxs-lookup"><span data-stu-id="86b3c-295">User Defined Type Named Items</span></span> ###

<span data-ttu-id="86b3c-296">Los elementos con nombre de los tipos definidos por el usuario se deben denominar `CamelCase`, incluso en la entrada a constructores UDT.</span><span class="sxs-lookup"><span data-stu-id="86b3c-296">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="86b3c-297">Esto ayuda a tener claramente separados los elementos con nombre de las referencias a variables de ámbito local cuando se usa la notación de descriptor de acceso (por ejemplo, `callable::Apply`) o la notación de copia y actualización (`set arr w/= Data <- newData`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-297">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-298">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-299">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-299">We suggest:</span></span>

- <span data-ttu-id="86b3c-300">Los elementos con nombre de los constructores UDT deben tener el nombre `CamelCase`; es decir, deben comenzar con mayúsculas iniciales.</span><span class="sxs-lookup"><span data-stu-id="86b3c-300">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="86b3c-301">Los elementos con nombre que se resuelven como operaciones se deben denominar fases de verbo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-301">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="86b3c-302">Los elementos con nombre que no se resuelven en las operaciones deben denominarse frases.</span><span class="sxs-lookup"><span data-stu-id="86b3c-302">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="86b3c-303">En el caso de los UDT que ajustan las operaciones, se debe definir un único elemento con nombre denominado `Apply`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-303">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-304">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-304">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-305">Snippet</span><span class="sxs-lookup"><span data-stu-id="86b3c-305">Snippet</span></span> | <span data-ttu-id="86b3c-306">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-306">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="86b3c-307">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-307">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="86b3c-308">El nombre `Apply` es una frase de verbo con formato `CamelCase`, lo que sugiere que el elemento con nombre es una operación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-308">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="86b3c-309">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-309">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="86b3c-310">Los elementos con nombre deben empezar con una letra mayúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="86b3c-310">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="86b3c-311">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-311">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="86b3c-312">Los elementos con nombre que se resuelven en funciones deben denominarse frases, no como frases verbales.</span><span class="sxs-lookup"><span data-stu-id="86b3c-312">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="86b3c-313">Convenciones de entrada</span><span class="sxs-lookup"><span data-stu-id="86b3c-313">Input Conventions</span></span> ##

<span data-ttu-id="86b3c-314">Cuando un desarrollador llama a una operación o una función, las distintas entradas a esa operación o función deben especificarse en un orden determinado, lo que aumenta la carga cognitiva a la que se enfrenta un desarrollador para hacer uso de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="86b3c-314">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="86b3c-315">En particular, la tarea de recordar los pedidos de entrada suele ser una distracción de la tarea a mano: programación de una implementación de un algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-315">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="86b3c-316">Aunque la compatibilidad con IDE enriquecida puede mitigar esto en gran medida, un buen diseño y adherencia a convenciones comunes también puede ayudar a minimizar la carga cognitiva impuesta por una API.</span><span class="sxs-lookup"><span data-stu-id="86b3c-316">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="86b3c-317">Siempre que sea posible, puede ser útil reducir el número de entradas que espera una operación o una función, de modo que el rol de cada entrada sea más evidente de inmediato para los desarrolladores que llaman a esa operación o función y a los desarrolladores que leen ese código más adelante.</span><span class="sxs-lookup"><span data-stu-id="86b3c-317">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="86b3c-318">Especialmente cuando no es posible o razonable reducir el número de argumentos para una operación o función, es importante tener una ordenación coherente que minimice la sorpresa que un usuario se enfrenta al predecir el orden de las entradas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-318">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="86b3c-319">Se recomienda usar convenciones de ordenación de entrada que deriven en gran medida del pensamiento de la aplicación parcial como generalización de currificación f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="86b3c-319">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="86b3c-320">Por lo tanto, la aplicación parcial de los primeros argumentos debe dar lugar a una invocable que sea útil en su propio derecho siempre que sea razonable.</span><span class="sxs-lookup"><span data-stu-id="86b3c-320">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="86b3c-321">Siguiendo este principio, considere la posibilidad de usar el siguiente orden de argumentos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-321">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="86b3c-322">Argumentos clásicos no Invocables como ángulos, vectores de potencias, etc.</span><span class="sxs-lookup"><span data-stu-id="86b3c-322">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="86b3c-323">Argumentos a los que se puede llamar (funciones y argumentos).</span><span class="sxs-lookup"><span data-stu-id="86b3c-323">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="86b3c-324">Si las funciones y las operaciones se toman como argumentos, considere la posibilidad de colocar las operaciones después de las funciones.</span><span class="sxs-lookup"><span data-stu-id="86b3c-324">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="86b3c-325">Colecciones de las que actúan argumentos Invocables de una manera similar a `Map`, `Iter`, `Enumerate`y `Fold`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-325">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="86b3c-326">Argumentos de qubit usados como controles.</span><span class="sxs-lookup"><span data-stu-id="86b3c-326">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="86b3c-327">Argumentos de qubit usados como destinos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-327">Qubit arguments used as targets.</span></span>

<span data-ttu-id="86b3c-328">Considere una operación `ApplyPhaseEstimationIteration` para su uso en la estimación de fase que toma un ángulo y un Oracle, pasa el ángulo a `Rz` modificado por una matriz de factores de escala diferentes y, a continuación, controla las aplicaciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="86b3c-328">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="86b3c-329">Se deben ordenar las entradas a `ApplyPhaseEstimationIteration` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="86b3c-329">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="86b3c-330">Como caso especial de minimizar sorpresa, algunas funciones y operaciones imitan el comportamiento de los funcntes integrados `Adjoint` y `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-330">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="86b3c-331">Por ejemplo, `ControlledOnInt<'T>` tiene el tipo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, de modo que `ControlledOnInt<Qubit[]>(5, _)` actúa como el functor `Controlled`, pero en la condición de que el registro del control representa el estado $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="86b3c-331">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="86b3c-332">Por lo tanto, un programador espera que las entradas en `ControlledOnInt` colocar el último que se puede transformar y que la operación resultante toma como su `(Qubit[], 'T)` de entrada---el mismo orden que el de la salida de `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-332">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-333">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-333">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-334">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-334">We suggest:</span></span>

- <span data-ttu-id="86b3c-335">Use pedidos de entrada coherentes con el uso de la aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="86b3c-335">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="86b3c-336">Use órdenes de entrada coherentes con los funcdores integrados.</span><span class="sxs-lookup"><span data-stu-id="86b3c-336">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="86b3c-337">Coloque todas las entradas clásicas antes de cualquier entrada de Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-337">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-338">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-338">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="86b3c-339">Convenciones de documentación</span><span class="sxs-lookup"><span data-stu-id="86b3c-339">Documentation Conventions</span></span> ##

<span data-ttu-id="86b3c-340">El lenguaje de preguntas y respuestas permite adjuntar documentación a operaciones, funciones y tipos definidos por el usuario mediante el uso de comentarios de documentación con formato especial.</span><span class="sxs-lookup"><span data-stu-id="86b3c-340">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="86b3c-341">Los comentarios de la documentación, que se indican mediante barras diagonales triples (`///`), son pequeños documentos [de Markdown DocFXs](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que se pueden usar para describir el propósito de cada operación, función y tipo definido por el usuario, qué entradas esperan y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-341">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="86b3c-342">El compilador proporcionado con el kit de desarrollo de Quantum extrae estos comentarios y los usa para ayudar a compuestas documentación similar a la de https://docs.microsoft.com/quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-342">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="86b3c-343">Del mismo modo, el servidor de lenguaje proporcionado con el kit de desarrollo de Quantum usa estos comentarios para proporcionar ayuda a los usuarios cuando se mantiene el mouse sobre los símbolos en su código de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-343">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="86b3c-344">El uso de los comentarios de la documentación puede ayudar a los usuarios a facilitar el código proporcionando una referencia útil para los detalles que no se expresan fácilmente mediante las demás convenciones de este documento.</span><span class="sxs-lookup"><span data-stu-id="86b3c-344">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="86b3c-345">
    [Referencia](xref:microsoft.quantum.language.statements#documentation-comments) de la sintaxis de comentarios de documentación
</span><span class="sxs-lookup"><span data-stu-id="86b3c-345">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="86b3c-346">Con el fin de usar esta funcionalidad de forma eficaz para ayudar a los usuarios, se recomienda tener presentes algunas cosas a la vez que escribe comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-346">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-347">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-347">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="86b3c-348">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-348">We suggest:</span></span>

- <span data-ttu-id="86b3c-349">Cada función pública, operación y tipo definido por el usuario deben ir precedidos de un Comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="86b3c-349">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="86b3c-350">Como mínimo, cada comentario de documentación debe incluir las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="86b3c-350">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="86b3c-351">Resumen</span><span class="sxs-lookup"><span data-stu-id="86b3c-351">Summary</span></span>
    - <span data-ttu-id="86b3c-352">Entrada</span><span class="sxs-lookup"><span data-stu-id="86b3c-352">Input</span></span>
    - <span data-ttu-id="86b3c-353">Salida (si es aplicable)</span><span class="sxs-lookup"><span data-stu-id="86b3c-353">Output (if applicable)</span></span>
- <span data-ttu-id="86b3c-354">Asegúrese de que todos los resúmenes son dos oraciones o menos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-354">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="86b3c-355">Si necesita más espacio, proporcione una `# Description` sección inmediatamente después de `# Summary` con detalles completos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-355">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="86b3c-356">Cuando sea razonable, no incluya cálculos matemáticos, ya que no todos los clientes admiten la notación TeX en resúmenes.</span><span class="sxs-lookup"><span data-stu-id="86b3c-356">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="86b3c-357">Tenga en cuenta que al escribir documentos de Prose (por ejemplo, TeX o Markdown), puede ser preferible usar longitudes de línea más largas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-357">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="86b3c-358">Proporcione todas las expresiones matemáticas relevantes en la sección `# Description`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-358">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="86b3c-359">Al describir las entradas, no repita los tipos de cada entrada, ya que el compilador y el riesgo de introducir incoherencia pueden inferirlos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-359">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="86b3c-360">Proporcione ejemplos según corresponda, cada uno en su propia sección `# Example`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-360">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="86b3c-361">Describa brevemente cada ejemplo antes de enumerar el código.</span><span class="sxs-lookup"><span data-stu-id="86b3c-361">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="86b3c-362">Cite todas las publicaciones académicas relevantes (por ejemplo, documentos, acciones, entradas de blog e implementaciones alternativas) en una `# References` sección como una lista de vínculos con viñetas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-362">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="86b3c-363">Asegúrese de que todos los vínculos de cita son identificadores permanentes e inmutables (DOIs o números de arXiv con control de versiones), siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="86b3c-363">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="86b3c-364">Cuando una operación o función está relacionada con otras operaciones o funciones mediante variantes de functor, enumere otras variantes como viñetas en la sección `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="86b3c-364">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="86b3c-365">Deje una línea de comentario en blanco entre las secciones de nivel 1 (`/// #`), pero no deje una línea en blanco entre las secciones de nivel 2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="86b3c-365">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-366">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-366">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="86b3c-367">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-367">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="86b3c-368">Convenciones de formato</span><span class="sxs-lookup"><span data-stu-id="86b3c-368">Formatting Conventions</span></span> ##

<span data-ttu-id="86b3c-369">Además de las sugerencias anteriores, resulta útil ayudar a que el código sea lo más legible posible para usar reglas de formato coherentes.</span><span class="sxs-lookup"><span data-stu-id="86b3c-369">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="86b3c-370">Estas reglas de formato por naturaleza tienden a ser algo arbitrarias y muy sólidas a la estética personal.</span><span class="sxs-lookup"><span data-stu-id="86b3c-370">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="86b3c-371">No obstante, se recomienda mantener un conjunto coherente de convenciones de formato dentro de un grupo de colaboradores y, especialmente, en proyectos de preguntas y respuestas grandes, como el propio Kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="86b3c-371">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="86b3c-372">Estas reglas se pueden aplicar automáticamente mediante la herramienta de formato integrada con el compilador de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="86b3c-372">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="86b3c-373">Guía</span><span class="sxs-lookup"><span data-stu-id="86b3c-373">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="86b3c-374">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="86b3c-374">We suggest:</span></span>

- <span data-ttu-id="86b3c-375">Use cuatro espacios en lugar de pestañas para la portabilidad.</span><span class="sxs-lookup"><span data-stu-id="86b3c-375">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="86b3c-376">Por ejemplo, en VS Code:</span><span class="sxs-lookup"><span data-stu-id="86b3c-376">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="86b3c-377">Ajuste de línea en 79 caracteres cuando sea razonable.</span><span class="sxs-lookup"><span data-stu-id="86b3c-377">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="86b3c-378">Usar espacios alrededor de los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="86b3c-378">Use spaces around binary operators.</span></span>
- <span data-ttu-id="86b3c-379">Use espacios a cada lado de los dos puntos usados para las anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-379">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="86b3c-380">Use un solo espacio después de las comas usadas en los literales de matriz y tupla (por ejemplo, en las entradas de funciones y operaciones).</span><span class="sxs-lookup"><span data-stu-id="86b3c-380">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="86b3c-381">No use espacios después de la función, la operación o los nombres UDT, o después del `@` en las declaraciones de atributos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-381">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="86b3c-382">Cada declaración de atributo debe estar en su propia línea.</span><span class="sxs-lookup"><span data-stu-id="86b3c-382">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="86b3c-383">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3c-383">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="86b3c-384">Snippet</span><span class="sxs-lookup"><span data-stu-id="86b3c-384">Snippet</span></span> | <span data-ttu-id="86b3c-385">description</span><span class="sxs-lookup"><span data-stu-id="86b3c-385">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="86b3c-386">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-386">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="86b3c-387">Usar espacios alrededor de los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="86b3c-387">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="86b3c-388">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-388">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="86b3c-389">Use espacios alrededor de los dos puntos de la anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-389">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="86b3c-390">☑</span><span class="sxs-lookup"><span data-stu-id="86b3c-390">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="86b3c-391">Los elementos de la tupla de entrada se espacian correctamente para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="86b3c-391">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="86b3c-392">☒</span><span class="sxs-lookup"><span data-stu-id="86b3c-392">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="86b3c-393">Los espacios se deben suprimir después de los nombres de función, operación o UDT.</span><span class="sxs-lookup"><span data-stu-id="86b3c-393">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

