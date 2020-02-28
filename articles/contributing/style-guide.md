---
title: 'Guía de estilo de Microsoft Q #'
description: Obtenga información sobre las convenciones de nomenclatura, entrada, documentación y formato para programas y bibliotecas de preguntas y respuestas.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3c8e432378ec563a197a5b87000c3e90cadb8e18
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907450"
---
# <a name="q-style-guide"></a><span data-ttu-id="97aa1-103">Guía de estilo de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="97aa1-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="97aa1-104">Convenciones generales</span><span class="sxs-lookup"><span data-stu-id="97aa1-104">General Conventions</span></span> ##

<span data-ttu-id="97aa1-105">Las convenciones sugeridas en esta guía están pensadas para facilitar la lectura y comprensión de los programas y las bibliotecas escritos en preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="97aa1-106">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-106">Guidance</span></span>

<span data-ttu-id="97aa1-107">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-107">We suggest:</span></span>

- <span data-ttu-id="97aa1-108">No ignore nunca una Convención a menos que lo haga de forma intencionada con el fin de proporcionar código más legible y comprensible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="97aa1-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="97aa1-109">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="97aa1-109">Naming Conventions</span></span> ##

<span data-ttu-id="97aa1-110">Al ofrecer el kit de desarrollo de Quantum, nos esforzamos por los nombres de función y de operación que ayudan a los desarrolladores de Quantum a escribir programas que son fáciles de leer y que minimizan la sorpresa.</span><span class="sxs-lookup"><span data-stu-id="97aa1-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="97aa1-111">Una parte importante de esto es que, cuando se eligen nombres para funciones, operaciones y tipos, se establece el *vocabulario* que los programadores usan para expresar los conceptos de Quantum. con nuestras opciones, nos ayudaremos o entorpeceremos su esfuerzo para comunicarse claramente.</span><span class="sxs-lookup"><span data-stu-id="97aa1-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="97aa1-112">Esto nos da la responsabilidad de asegurarse de que los nombres que presentamos ofrecen una claridad en lugar de la ocultación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="97aa1-113">En esta sección, detallamos cómo se cumple esta obligación en términos de instrucciones explícitas que nos ayudan a hacer lo mejor en la comunidad de desarrollo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="97aa1-114">Operaciones y funciones</span><span class="sxs-lookup"><span data-stu-id="97aa1-114">Operations and Functions</span></span> ###

<span data-ttu-id="97aa1-115">Una de las primeras cosas que debe establecer un nombre es si un símbolo determinado representa una función o una operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="97aa1-116">La diferencia entre las funciones y las operaciones es fundamental para entender cómo se comporta un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="97aa1-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="97aa1-117">Para comunicar la distinción entre las funciones y las operaciones con los usuarios, confiamos en que las operaciones de Quantum de los modelos Q # usan efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="97aa1-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="97aa1-118">Es decir, una operación *realiza* alguna acción.</span><span class="sxs-lookup"><span data-stu-id="97aa1-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="97aa1-119">Por el contrario, las funciones describen las relaciones matemáticas entre los datos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="97aa1-120">La expresión `Sin(PI() / 2.0)` *es* `1.0`y no implica nada sobre el estado de un programa o de su qubits.</span><span class="sxs-lookup"><span data-stu-id="97aa1-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="97aa1-121">Resumen, las operaciones realizan cosas mientras que las funciones son cosas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="97aa1-122">Esta distinción sugiere que denominamos operaciones como verbos y funciones como nombres.</span><span class="sxs-lookup"><span data-stu-id="97aa1-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="97aa1-123">Cuando se declara un tipo definido por el usuario, una nueva función que crea instancias de ese tipo se define implícitamente al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="97aa1-124">Desde esa perspectiva, los tipos definidos por el usuario se deben denominar nombres para que el propio tipo y la función constructora tengan nombres coherentes.</span><span class="sxs-lookup"><span data-stu-id="97aa1-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="97aa1-125">Cuando sea razonable, asegúrese de que los nombres de operación comienzan por verbos que indican claramente el efecto que realiza la operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="97aa1-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="97aa1-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="97aa1-127">Un caso que merece mención especial es cuando una operación toma otra operación como entrada y la llama.</span><span class="sxs-lookup"><span data-stu-id="97aa1-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="97aa1-128">En tales casos, la acción realizada por la operación de entrada no está clara cuando se define la operación externa, de modo que el verbo derecho no se borra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="97aa1-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="97aa1-129">Se recomienda el `Apply`de verbo, como en `ApplyIf`, `ApplyToEach`y `ApplyToFirst`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="97aa1-130">Otros verbos también pueden resultar útiles en este caso, como en `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="97aa1-131">Verbo</span><span class="sxs-lookup"><span data-stu-id="97aa1-131">Verb</span></span> | <span data-ttu-id="97aa1-132">Efecto esperado</span><span class="sxs-lookup"><span data-stu-id="97aa1-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="97aa1-133">Aplicar</span><span class="sxs-lookup"><span data-stu-id="97aa1-133">Apply</span></span> | <span data-ttu-id="97aa1-134">Se llama a una operación que se proporciona como entrada.</span><span class="sxs-lookup"><span data-stu-id="97aa1-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="97aa1-135">Assert</span><span class="sxs-lookup"><span data-stu-id="97aa1-135">Assert</span></span> | <span data-ttu-id="97aa1-136">Un simulador comprueba una hipótesis sobre el resultado de una posible medida Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="97aa1-137">Presupuesto</span><span class="sxs-lookup"><span data-stu-id="97aa1-137">Estimate</span></span> | <span data-ttu-id="97aa1-138">Se devuelve un valor clásico que representa una estimación dibujada a partir de una o más medidas</span><span class="sxs-lookup"><span data-stu-id="97aa1-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="97aa1-139">Measure</span><span class="sxs-lookup"><span data-stu-id="97aa1-139">Measure</span></span> | <span data-ttu-id="97aa1-140">Se realiza una medición de cuanto y el resultado se devuelve al usuario.</span><span class="sxs-lookup"><span data-stu-id="97aa1-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="97aa1-141">Preparación</span><span class="sxs-lookup"><span data-stu-id="97aa1-141">Prepare</span></span> | <span data-ttu-id="97aa1-142">Un registro determinado de qubits se inicializa en un estado determinado.</span><span class="sxs-lookup"><span data-stu-id="97aa1-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="97aa1-143">Muestra</span><span class="sxs-lookup"><span data-stu-id="97aa1-143">Sample</span></span> | <span data-ttu-id="97aa1-144">Un valor clásico se devuelve de forma aleatoria desde alguna distribución</span><span class="sxs-lookup"><span data-stu-id="97aa1-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="97aa1-145">En el caso de las funciones, se recomienda evitar el uso de verbos en favor de los nombres comunes (vea las instrucciones sobre los nombres adecuados a continuación) o adjetivos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="97aa1-146">En concreto, en casi todos los casos, se recomienda usar los participles anteriores, donde corresponda para indicar que un nombre de función está conectado fuertemente a una acción o efecto secundario en otro lugar de un programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="97aa1-147">Por ejemplo, `ControlledOnInt` usa el formulario participio de la parte del verbo "control" para indicar que la función actúa como adjetivo para modificar su argumento.</span><span class="sxs-lookup"><span data-stu-id="97aa1-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="97aa1-148">Este nombre tiene la ventaja adicional de buscar coincidencias con la semántica del functor integrada `Controlled`, como se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="97aa1-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="97aa1-149">Del mismo modo, los nombres de _agente_ se pueden usar para construir nombres de función y UDT a partir de los nombres de operación, como en el caso del nombre `Encoder` para un UDT que esté fuertemente asociado a `Encode`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-150">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-151">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-151">We suggest:</span></span>

- <span data-ttu-id="97aa1-152">Usar verbos para nombres de operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="97aa1-153">Utilice sustantivos o adjetivos para los nombres de función.</span><span class="sxs-lookup"><span data-stu-id="97aa1-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="97aa1-154">Utilice sustantivos para los atributos y tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="97aa1-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="97aa1-155">En el caso de todos los nombres a los que se puede llamar, use `CamelCase` en preferencias fuertes para `pascalCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="97aa1-156">En concreto, asegúrese de que los nombres que se puedan llamar comienzan con letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="97aa1-157">En el caso de todas las variables locales, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="97aa1-158">En concreto, asegúrese de que las variables locales comienzan con letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="97aa1-159">Evite el uso de subrayados `_` en los nombres de función y de operación; Cuando se necesiten niveles adicionales de jerarquía, use espacios de nombres y alias de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="97aa1-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-160">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="97aa1-161">Name</span></span> | <span data-ttu-id="97aa1-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="97aa1-163">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="97aa1-164">Desactive el uso de un verbo ("Reflect") para indicar el efecto de la operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="97aa1-165">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="97aa1-166">El uso de la frase de nombre sugiere la función, en lugar de la operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="97aa1-167">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="97aa1-168">El uso de `snake_case` de la notación de Q #.</span><span class="sxs-lookup"><span data-stu-id="97aa1-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="97aa1-169">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="97aa1-170">El uso de un carácter de subrayado interno al nombre de la operación sirve de notación de Q #.</span><span class="sxs-lookup"><span data-stu-id="97aa1-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="97aa1-171">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="97aa1-172">El uso de la frase de nombre sugiere que la función devuelve una operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="97aa1-173">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="97aa1-174">Desactive el uso de sustantivo ("Fact") para indicar que se trata de una función, mientras que el adjetivo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="97aa1-175">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="97aa1-176">El uso de verbo ("Get") sugiere que se trata de una operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="97aa1-177">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="97aa1-178">El uso de la frase se refiere claramente al resultado de llamar al constructor UDT.</span><span class="sxs-lookup"><span data-stu-id="97aa1-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="97aa1-179">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="97aa1-180">El uso de la frase verbal sugiere que el constructor UDT es una operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="97aa1-181">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="97aa1-182">El uso de nombre de frase comunica el uso del atributo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="97aa1-183">Abreviaturas y abreviaturas</span><span class="sxs-lookup"><span data-stu-id="97aa1-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="97aa1-184">A pesar de los consejos anteriores, hay muchas formas de taquigrafía que ven un uso común y generalizado en la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="97aa1-185">Se recomienda usar una abreviatura común y existente donde exista, especialmente para las operaciones que son intrínsecas al funcionamiento de un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="97aa1-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="97aa1-186">Por ejemplo, elegimos el nombre `X` en lugar de `ApplyX`y `Rz` en lugar de `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="97aa1-187">Cuando se usa esta forma abreviada, los nombres de operación deben estar en mayúsculas (por ejemplo: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="97aa1-188">Es necesario tener cuidado al aplicar esta Convención en el caso de acrónimos de uso frecuente y siglas como "QFT" para "transformación de Fourier de Quantum".</span><span class="sxs-lookup"><span data-stu-id="97aa1-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="97aa1-189">Sugerimos las siguientes convenciones generales de .NET para el uso de acrónimos y siglas en nombres completos, lo que prescribe:</span><span class="sxs-lookup"><span data-stu-id="97aa1-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="97aa1-190">los acrónimos de dos letras y siglas se denominan en mayúsculas (por ejemplo: `BE` para "Big-endian").</span><span class="sxs-lookup"><span data-stu-id="97aa1-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="97aa1-191">todos los acrónimos más largos y siglas se denominan en `CamelCase` (por ejemplo: `Qft` para "transformación de Fourier de Quantum")</span><span class="sxs-lookup"><span data-stu-id="97aa1-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="97aa1-192">Por lo tanto, una operación que implementa QFT podría llamarse `QFT` como una abreviatura o escribirse como `ApplyQft`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="97aa1-193">En el caso de las operaciones y funciones especialmente utilizadas, puede ser conveniente proporcionar un nombre abreviado como _alias_ para una forma más larga:</span><span class="sxs-lookup"><span data-stu-id="97aa1-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="97aa1-194">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-195">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-195">We suggest:</span></span>

- <span data-ttu-id="97aa1-196">Considere la posibilidad de usar nombres abreviados comúnmente aceptados y ampliamente utilizados cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="97aa1-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="97aa1-197">Use mayúsculas para abreviar.</span><span class="sxs-lookup"><span data-stu-id="97aa1-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="97aa1-198">Use mayúsculas para acrónimos cortos (dos letras) y siglas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="97aa1-199">Use `CamelCase` para acrónimos más largos (tres o más letras) y siglas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-200">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-201">Nombre</span><span class="sxs-lookup"><span data-stu-id="97aa1-201">Name</span></span> | <span data-ttu-id="97aa1-202">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="97aa1-203">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-203">☑</span></span> | `X` | <span data-ttu-id="97aa1-204">Abreviatura bien entendida para "aplicar una transformación de $X $"</span><span class="sxs-lookup"><span data-stu-id="97aa1-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="97aa1-205">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-205">☑</span></span> | `CNOT` | <span data-ttu-id="97aa1-206">Abreviatura bien entendida para "controlado"</span><span class="sxs-lookup"><span data-stu-id="97aa1-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="97aa1-207">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="97aa1-208">La abreviatura no debe estar en `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="97aa1-209">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="97aa1-210">El inicio común "QFT" aparece como parte de un nombre de formato largo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="97aa1-211">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-211">☑</span></span> | `QFT` | <span data-ttu-id="97aa1-212">El inicio común "QFT" aparece como parte de un nombre abreviado.</span><span class="sxs-lookup"><span data-stu-id="97aa1-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="97aa1-213">Nombres correctos en nombres</span><span class="sxs-lookup"><span data-stu-id="97aa1-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="97aa1-214">Mientras que en la física es habitual nombrar cosas después de que la primera persona publique sobre ellas, la mayoría de los Physicists no están familiarizados con los nombres de todos y el historial.</span><span class="sxs-lookup"><span data-stu-id="97aa1-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="97aa1-215">Confiar demasiado en las convenciones de nomenclatura de la física puede, por tanto, imponer una barrera importante a la entrada, ya que los usuarios de otros terrenos deben aprender un gran número de nombres aparentemente opacos con el fin de usar operaciones y conceptos comunes.</span><span class="sxs-lookup"><span data-stu-id="97aa1-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="97aa1-216">Por lo tanto, se recomienda que, siempre que sea razonable, los nombres comunes que describen un concepto se adopten en una buena preferencia con los nombres adecuados que describen el historial de publicaciones de un concepto.</span><span class="sxs-lookup"><span data-stu-id="97aa1-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="97aa1-217">Como ejemplo concreto, las operaciones de intercambio y control de subestado que se controlan a menudo se denominan "Fredkin" y "Toffoli" en la literatura académica, pero se identifican en Q # principalmente como `CSWAP` y `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="97aa1-218">En ambos casos, los comentarios de la documentación de la API proporcionan nombres de sinónimos basados en nombres adecuados, junto con todas las citas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="97aa1-219">Esta preferencia es especialmente importante dado que el uso de los nombres adecuados siempre será necesario: Q # sigue la tradición establecida por muchos lenguajes clásico, por ejemplo, y hace referencia a `Bool` tipos en referencia a la lógica booleana, que a su vez se denomina en el honor George bool.</span><span class="sxs-lookup"><span data-stu-id="97aa1-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="97aa1-220">Unos pocos conceptos de Quantum se denominan de forma similar, incluido el tipo de `Pauli` integrado en el lenguaje de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="97aa1-221">Al minimizar el uso de los nombres adecuados en los casos en los que no es esencial, se reduce el impacto en el que no se pueden evitar razonablemente los nombres adecuados.</span><span class="sxs-lookup"><span data-stu-id="97aa1-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-222">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="97aa1-223">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-223">We suggest:</span></span>

- <span data-ttu-id="97aa1-224">Evite el uso de nombres propios en los nombres.</span><span class="sxs-lookup"><span data-stu-id="97aa1-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-225">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="97aa1-226">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="97aa1-226">Type Conversions</span></span> ###

<span data-ttu-id="97aa1-227">Como Q # es un lenguaje fuertemente tipado y con tipos estáticos, un valor de un tipo solo se puede usar como un valor de otro tipo mediante una llamada explícita a una función de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="97aa1-228">Esto contrasta con los lenguajes que permiten a los valores cambiar tipos de forma implícita (por ejemplo: promoción de tipos) o a través de la conversión.</span><span class="sxs-lookup"><span data-stu-id="97aa1-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="97aa1-229">Como resultado, las funciones de conversión de tipos desempeñan un papel importante en el desarrollo de la biblioteca de Q # y constituyen una de las decisiones más frecuentes sobre la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="97aa1-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="97aa1-230">Sin embargo, tenemos en cuenta que, dado que las conversiones de tipo siempre son _deterministas_, se pueden escribir como funciones y, por lo tanto, se incluyen en el Consejo anterior.</span><span class="sxs-lookup"><span data-stu-id="97aa1-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="97aa1-231">En concreto, se recomienda que las funciones de conversión de tipos nunca se denominen como verbos (por ejemplo, `ConvertToX`) o frases de preposicional (`ToX`) de adverbio, pero se deben denominar frases de preposicional de adjetivo que indiquen los tipos de origen y destino (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="97aa1-232">Al enumerar los tipos de matriz en los nombres de funciones de conversión de tipos, se recomienda el `Arr`abreviado.</span><span class="sxs-lookup"><span data-stu-id="97aa1-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="97aa1-233">Salvo en circunstancias excepcionales, se recomienda asignar un nombre a todas las funciones de conversión de tipos mediante `As` para que se puedan identificar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="97aa1-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-234">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-235">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-235">We suggest:</span></span>

- <span data-ttu-id="97aa1-236">Si una función convierte un valor de tipo `X` en un valor de tipo `Y`, use el nombre `AsY` o `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-237">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-238">Nombre</span><span class="sxs-lookup"><span data-stu-id="97aa1-238">Name</span></span> | <span data-ttu-id="97aa1-239">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="97aa1-240">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="97aa1-241">La preposición "to" da como resultado una frase verbal, que indica una operación y no una función.</span><span class="sxs-lookup"><span data-stu-id="97aa1-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="97aa1-242">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="97aa1-243">El tipo de entrada no está claro en el nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="97aa1-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="97aa1-244">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="97aa1-245">Los tipos de entrada y salida aparecen en el orden equivocado.</span><span class="sxs-lookup"><span data-stu-id="97aa1-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="97aa1-246">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="97aa1-247">Tanto los tipos de entrada como los de salida están claros.</span><span class="sxs-lookup"><span data-stu-id="97aa1-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="97aa1-248">Nombres privados o internos</span><span class="sxs-lookup"><span data-stu-id="97aa1-248">Private or Internal Names</span></span> ###

<span data-ttu-id="97aa1-249">En muchos casos, un nombre está pensado exclusivamente para usarse internamente en una biblioteca o proyecto y no es una parte garantizada de la API ofrecida por una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="97aa1-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="97aa1-250">Resulta útil indicar claramente que este es el caso cuando se asignan nombres a funciones y operaciones para que las dependencias accidentales del código solo interno se hagan obvias.</span><span class="sxs-lookup"><span data-stu-id="97aa1-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="97aa1-251">Si una operación o función no está pensada para su uso directo, sino que debe ser usada por una función que admita la coincidencia que actúa por aplicación parcial, considere la posibilidad de usar un nombre que empiece por `_` para la que se puede llamar parcialmente.</span><span class="sxs-lookup"><span data-stu-id="97aa1-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-252">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-253">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-253">We suggest:</span></span>

- <span data-ttu-id="97aa1-254">Cuando una función, una operación o un tipo definido por el usuario no forma parte de la API pública para un programa o biblioteca de Q #, asegúrese de que su nombre comienza con un carácter de subrayado inicial (`_`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-255">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-256">Nombre</span><span class="sxs-lookup"><span data-stu-id="97aa1-256">Name</span></span> | <span data-ttu-id="97aa1-257">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="97aa1-258">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="97aa1-259">El carácter de subrayado `_` no debe aparecer al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="97aa1-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="97aa1-260">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="97aa1-261">El carácter de subrayado `_` al principio indica claramente que esta operación solo es para uso interno.</span><span class="sxs-lookup"><span data-stu-id="97aa1-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="97aa1-262">Variantes</span><span class="sxs-lookup"><span data-stu-id="97aa1-262">Variants</span></span> ###

<span data-ttu-id="97aa1-263">Aunque es posible que esta limitación no se conserve en versiones futuras de Q #, es actualmente el caso de que a menudo existan grupos de operaciones o funciones relacionadas que se diferencian por los inconvenientes que admiten sus entradas, o por los tipos concretos de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="97aa1-264">Estos grupos se pueden distinguir con el mismo nombre de raíz, seguido de una o dos letras que indican su variante.</span><span class="sxs-lookup"><span data-stu-id="97aa1-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="97aa1-265">Sufijo</span><span class="sxs-lookup"><span data-stu-id="97aa1-265">Suffix</span></span> | <span data-ttu-id="97aa1-266">Significado</span><span class="sxs-lookup"><span data-stu-id="97aa1-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="97aa1-267">Se espera que la entrada sea compatible con `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="97aa1-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="97aa1-268">Se espera que la entrada sea compatible con `Controlled`</span><span class="sxs-lookup"><span data-stu-id="97aa1-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="97aa1-269">Se espera que la entrada admita `Controlled` y `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="97aa1-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="97aa1-270">La entrada o las entradas son del tipo `Int`</span><span class="sxs-lookup"><span data-stu-id="97aa1-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="97aa1-271">La entrada o las entradas son del tipo `Double`</span><span class="sxs-lookup"><span data-stu-id="97aa1-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="97aa1-272">La entrada o las entradas son del tipo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="97aa1-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="97aa1-273">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-274">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-274">We suggest:</span></span>

- <span data-ttu-id="97aa1-275">Si una función u operación no está relacionada con funciones u operaciones similares por los tipos y la compatibilidad con las entradas de las entradas, no use un sufijo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="97aa1-276">Si una función u operación está relacionada con funciones u operaciones similares según los tipos y la compatibilidad con las entradas más inactivas, use los sufijos que se indican en la tabla anterior para distinguir las variantes.</span><span class="sxs-lookup"><span data-stu-id="97aa1-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-277">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="97aa1-278">Argumentos y variables</span><span class="sxs-lookup"><span data-stu-id="97aa1-278">Arguments and Variables</span></span> ###

<span data-ttu-id="97aa1-279">Un objetivo clave del código de preguntas y respuestas para una función u operación es que sea fácil de leer y comprender.</span><span class="sxs-lookup"><span data-stu-id="97aa1-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="97aa1-280">Del mismo modo, los nombres de las entradas y los argumentos de tipo deben comunicar cómo se usará una función o un argumento una vez proporcionado.</span><span class="sxs-lookup"><span data-stu-id="97aa1-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="97aa1-281">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-282">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-282">We suggest:</span></span>

- <span data-ttu-id="97aa1-283">En el caso de todos los nombres de variable y de entrada, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="97aa1-284">Los nombres de entrada deben ser descriptivos; Evite los nombres de uno o dos letras siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="97aa1-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="97aa1-285">Las operaciones y funciones que aceptan exactamente un argumento de tipo deben indicar que el argumento de tipo se `T` cuando su rol es obvio.</span><span class="sxs-lookup"><span data-stu-id="97aa1-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="97aa1-286">Si una función u operación toma varios argumentos de tipo o si el rol de un solo argumento de tipo no es obvio, considere la posibilidad de usar una palabra corta en mayúsculas precedida por `T` (por ejemplo: `TOutput`) para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="97aa1-287">No incluya nombres de tipo en los nombres de argumento y variable; Esta información puede ser proporcionada por el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="97aa1-288">Denota los tipos escalares por sus nombres literales (`flagQubit`) y los tipos de matriz en plural (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="97aa1-289">En el caso de las matrices de qubits en particular, considere la posibilidad de que estos tipos se denotan por `Register` donde el nombre hace referencia a una secuencia de qubits que están estrechamente relacionadas de algún modo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="97aa1-290">Las variables que se usan como índices en matrices deben comenzar con `idx` y deben ser singulares (por ejemplo: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="97aa1-291">En concreto, evite fuertemente el uso de nombres de variable de una sola letra como índices; considere la posibilidad de usar `idx` como mínimo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="97aa1-292">Las variables que se usan para contener longitudes de matrices deben comenzar con `n` y deben ser plurales (por ejemplo: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-293">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="97aa1-294">Tipo definido por el usuario denominado items</span><span class="sxs-lookup"><span data-stu-id="97aa1-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="97aa1-295">Los elementos con nombre de los tipos definidos por el usuario se deben denominar `CamelCase`, incluso en la entrada a constructores UDT.</span><span class="sxs-lookup"><span data-stu-id="97aa1-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="97aa1-296">Esto ayuda a tener claramente separados los elementos con nombre de las referencias a variables de ámbito local cuando se usa la notación de descriptor de acceso (por ejemplo, `callable::Apply`) o la notación de copia y actualización (`set arr w/= Data <- newData`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-297">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-298">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-298">We suggest:</span></span>

- <span data-ttu-id="97aa1-299">Los elementos con nombre de los constructores UDT deben tener el nombre `CamelCase`; es decir, deben comenzar con mayúsculas iniciales.</span><span class="sxs-lookup"><span data-stu-id="97aa1-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="97aa1-300">Los elementos con nombre que se resuelven como operaciones se deben denominar fases de verbo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="97aa1-301">Los elementos con nombre que no se resuelven en las operaciones deben denominarse frases.</span><span class="sxs-lookup"><span data-stu-id="97aa1-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="97aa1-302">En el caso de los UDT que ajustan las operaciones, se debe definir un único elemento con nombre denominado `Apply`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-303">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-304">Snippet</span><span class="sxs-lookup"><span data-stu-id="97aa1-304">Snippet</span></span> | <span data-ttu-id="97aa1-305">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="97aa1-306">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="97aa1-307">El nombre `Apply` es una frase de verbo con formato `CamelCase`, lo que sugiere que el elemento con nombre es una operación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="97aa1-308">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="97aa1-309">Los elementos con nombre deben empezar con una letra mayúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="97aa1-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="97aa1-310">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="97aa1-311">Los elementos con nombre que se resuelven en funciones deben denominarse frases, no como frases verbales.</span><span class="sxs-lookup"><span data-stu-id="97aa1-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="97aa1-312">Convenciones de entrada</span><span class="sxs-lookup"><span data-stu-id="97aa1-312">Input Conventions</span></span> ##

<span data-ttu-id="97aa1-313">Cuando un desarrollador llama a una operación o una función, las distintas entradas a esa operación o función deben especificarse en un orden determinado, lo que aumenta la carga cognitiva a la que se enfrenta un desarrollador para hacer uso de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="97aa1-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="97aa1-314">En particular, la tarea de recordar los pedidos de entrada suele ser una distracción de la tarea a mano: programación de una implementación de un algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="97aa1-315">Aunque la compatibilidad con IDE enriquecida puede mitigar esto en gran medida, un buen diseño y adherencia a convenciones comunes también puede ayudar a minimizar la carga cognitiva impuesta por una API.</span><span class="sxs-lookup"><span data-stu-id="97aa1-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="97aa1-316">Siempre que sea posible, puede ser útil reducir el número de entradas que espera una operación o una función, de modo que el rol de cada entrada sea más evidente de inmediato para los desarrolladores que llaman a esa operación o función y a los desarrolladores que leen ese código más adelante.</span><span class="sxs-lookup"><span data-stu-id="97aa1-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="97aa1-317">Especialmente cuando no es posible o razonable reducir el número de argumentos para una operación o función, es importante tener una ordenación coherente que minimice la sorpresa que un usuario se enfrenta al predecir el orden de las entradas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="97aa1-318">Se recomienda usar convenciones de ordenación de entrada que deriven en gran medida del pensamiento de la aplicación parcial como generalización de currificación f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="97aa1-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="97aa1-319">Por lo tanto, la aplicación parcial de los primeros argumentos debe dar lugar a una invocable que sea útil en su propio derecho siempre que sea razonable.</span><span class="sxs-lookup"><span data-stu-id="97aa1-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="97aa1-320">Siguiendo este principio, considere la posibilidad de usar el siguiente orden de argumentos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="97aa1-321">Argumentos clásicos no Invocables como ángulos, vectores de potencias, etc.</span><span class="sxs-lookup"><span data-stu-id="97aa1-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="97aa1-322">Argumentos a los que se puede llamar (funciones y argumentos).</span><span class="sxs-lookup"><span data-stu-id="97aa1-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="97aa1-323">Si las funciones y las operaciones se toman como argumentos, considere la posibilidad de colocar las operaciones después de las funciones.</span><span class="sxs-lookup"><span data-stu-id="97aa1-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="97aa1-324">Colecciones de las que actúan argumentos Invocables de una manera similar a `Map`, `Iter`, `Enumerate`y `Fold`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="97aa1-325">Argumentos de qubit usados como controles.</span><span class="sxs-lookup"><span data-stu-id="97aa1-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="97aa1-326">Argumentos de qubit usados como destinos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="97aa1-327">Considere una operación `ApplyPhaseEstimationIteration` para su uso en la estimación de fase que toma un ángulo y un Oracle, pasa el ángulo a `Rz` modificado por una matriz de factores de escala diferentes y, a continuación, controla las aplicaciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="97aa1-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="97aa1-328">Se deben ordenar las entradas a `ApplyPhaseEstimationIteration` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="97aa1-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="97aa1-329">Como caso especial de minimizar sorpresa, algunas funciones y operaciones imitan el comportamiento de los funcntes integrados `Adjoint` y `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="97aa1-330">Por ejemplo, `ControlledOnInt<'T>` tiene el tipo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, de modo que `ControlledOnInt<Qubit[]>(5, _)` actúa como el functor `Controlled`, pero en la condición de que el registro del control representa el estado $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="97aa1-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="97aa1-331">Por lo tanto, un programador espera que las entradas en `ControlledOnInt` colocar el último que se puede transformar y que la operación resultante toma como su `(Qubit[], 'T)` de entrada---el mismo orden que el de la salida de `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="97aa1-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-332">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-333">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-333">We suggest:</span></span>

- <span data-ttu-id="97aa1-334">Use pedidos de entrada coherentes con el uso de la aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="97aa1-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="97aa1-335">Use órdenes de entrada coherentes con los funcdores integrados.</span><span class="sxs-lookup"><span data-stu-id="97aa1-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="97aa1-336">Coloque todas las entradas clásicas antes de cualquier entrada de Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-337">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="97aa1-338">Convenciones de documentación</span><span class="sxs-lookup"><span data-stu-id="97aa1-338">Documentation Conventions</span></span> ##

<span data-ttu-id="97aa1-339">El lenguaje de preguntas y respuestas permite adjuntar documentación a operaciones, funciones y tipos definidos por el usuario mediante el uso de comentarios de documentación con formato especial.</span><span class="sxs-lookup"><span data-stu-id="97aa1-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="97aa1-340">Los comentarios de la documentación, que se indican mediante barras diagonales triples (`///`), son pequeños documentos [de Markdown DocFXs](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que se pueden usar para describir el propósito de cada operación, función y tipo definido por el usuario, qué entradas esperan y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="97aa1-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="97aa1-341">El compilador proporcionado con el kit de desarrollo de Quantum extrae estos comentarios y los usa para ayudar a compuestas documentación similar a la de https://docs.microsoft.com/quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="97aa1-342">Del mismo modo, el servidor de lenguaje proporcionado con el kit de desarrollo de Quantum usa estos comentarios para proporcionar ayuda a los usuarios cuando se mantiene el mouse sobre los símbolos en su código de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="97aa1-343">El uso de los comentarios de la documentación puede ayudar a los usuarios a facilitar el código proporcionando una referencia útil para los detalles que no se expresan fácilmente mediante las demás convenciones de este documento.</span><span class="sxs-lookup"><span data-stu-id="97aa1-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="97aa1-344">
    [Referencia](xref:microsoft.quantum.language.statements#documentation-comments) de la sintaxis de comentarios de documentación
</span><span class="sxs-lookup"><span data-stu-id="97aa1-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="97aa1-345">Con el fin de usar esta funcionalidad de forma eficaz para ayudar a los usuarios, se recomienda tener presentes algunas cosas a la vez que escribe comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-346">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="97aa1-347">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-347">We suggest:</span></span>

- <span data-ttu-id="97aa1-348">Cada función pública, operación y tipo definido por el usuario deben ir precedidos de un Comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="97aa1-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="97aa1-349">Como mínimo, cada comentario de documentación debe incluir las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="97aa1-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="97aa1-350">Resumen</span><span class="sxs-lookup"><span data-stu-id="97aa1-350">Summary</span></span>
    - <span data-ttu-id="97aa1-351">Entrada</span><span class="sxs-lookup"><span data-stu-id="97aa1-351">Input</span></span>
    - <span data-ttu-id="97aa1-352">Salida (si es aplicable)</span><span class="sxs-lookup"><span data-stu-id="97aa1-352">Output (if applicable)</span></span>
- <span data-ttu-id="97aa1-353">Asegúrese de que todos los resúmenes son dos oraciones o menos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="97aa1-354">Si necesita más espacio, proporcione una `# Description` sección inmediatamente después de `# Summary` con detalles completos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="97aa1-355">Cuando sea razonable, no incluya cálculos matemáticos, ya que no todos los clientes admiten la notación TeX en resúmenes.</span><span class="sxs-lookup"><span data-stu-id="97aa1-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="97aa1-356">Tenga en cuenta que al escribir documentos de Prose (por ejemplo, TeX o Markdown), puede ser preferible usar longitudes de línea más largas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="97aa1-357">Proporcione todas las expresiones matemáticas relevantes en la sección `# Description`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="97aa1-358">Al describir las entradas, no repita los tipos de cada entrada, ya que el compilador y el riesgo de introducir incoherencia pueden inferirlos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="97aa1-359">Proporcione ejemplos según corresponda, cada uno en su propia sección `# Example`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="97aa1-360">Describa brevemente cada ejemplo antes de enumerar el código.</span><span class="sxs-lookup"><span data-stu-id="97aa1-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="97aa1-361">Cite todas las publicaciones académicas relevantes (por ejemplo, documentos, acciones, entradas de blog e implementaciones alternativas) en una `# References` sección como una lista de vínculos con viñetas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="97aa1-362">Asegúrese de que todos los vínculos de cita son identificadores permanentes e inmutables (DOIs o números de arXiv con control de versiones), siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="97aa1-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="97aa1-363">Cuando una operación o función está relacionada con otras operaciones o funciones mediante variantes de functor, enumere otras variantes como viñetas en la sección `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="97aa1-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="97aa1-364">Deje una línea de comentario en blanco entre las secciones de nivel 1 (`/// #`), pero no deje una línea en blanco entre las secciones de nivel 2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="97aa1-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-365">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="97aa1-366">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="97aa1-367">Convenciones de formato</span><span class="sxs-lookup"><span data-stu-id="97aa1-367">Formatting Conventions</span></span> ##

<span data-ttu-id="97aa1-368">Además de las sugerencias anteriores, resulta útil ayudar a que el código sea lo más legible posible para usar reglas de formato coherentes.</span><span class="sxs-lookup"><span data-stu-id="97aa1-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="97aa1-369">Estas reglas de formato por naturaleza tienden a ser algo arbitrarias y muy sólidas a la estética personal.</span><span class="sxs-lookup"><span data-stu-id="97aa1-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="97aa1-370">No obstante, se recomienda mantener un conjunto coherente de convenciones de formato dentro de un grupo de colaboradores y, especialmente, en proyectos de preguntas y respuestas grandes, como el propio Kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="97aa1-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="97aa1-371">Estas reglas se pueden aplicar automáticamente mediante la herramienta de formato integrada con el compilador de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="97aa1-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="97aa1-372">Guía</span><span class="sxs-lookup"><span data-stu-id="97aa1-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="97aa1-373">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="97aa1-373">We suggest:</span></span>

- <span data-ttu-id="97aa1-374">Use cuatro espacios en lugar de pestañas para la portabilidad.</span><span class="sxs-lookup"><span data-stu-id="97aa1-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="97aa1-375">Por ejemplo, en VS Code:</span><span class="sxs-lookup"><span data-stu-id="97aa1-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="97aa1-376">Ajuste de línea en 79 caracteres cuando sea razonable.</span><span class="sxs-lookup"><span data-stu-id="97aa1-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="97aa1-377">Usar espacios alrededor de los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="97aa1-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="97aa1-378">Use espacios a cada lado de los dos puntos usados para las anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="97aa1-379">Use un solo espacio después de las comas usadas en los literales de matriz y tupla (por ejemplo, en las entradas de funciones y operaciones).</span><span class="sxs-lookup"><span data-stu-id="97aa1-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="97aa1-380">No use espacios después de la función, la operación o los nombres UDT, o después del `@` en las declaraciones de atributos.</span><span class="sxs-lookup"><span data-stu-id="97aa1-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="97aa1-381">Cada declaración de atributo debe estar en su propia línea.</span><span class="sxs-lookup"><span data-stu-id="97aa1-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="97aa1-382">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97aa1-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="97aa1-383">Snippet</span><span class="sxs-lookup"><span data-stu-id="97aa1-383">Snippet</span></span> | <span data-ttu-id="97aa1-384">Descripción</span><span class="sxs-lookup"><span data-stu-id="97aa1-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="97aa1-385">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="97aa1-386">Usar espacios alrededor de los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="97aa1-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="97aa1-387">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="97aa1-388">Use espacios alrededor de los dos puntos de la anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="97aa1-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="97aa1-389">☑</span><span class="sxs-lookup"><span data-stu-id="97aa1-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="97aa1-390">Los elementos de la tupla de entrada se espacian correctamente para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="97aa1-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="97aa1-391">☒</span><span class="sxs-lookup"><span data-stu-id="97aa1-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="97aa1-392">Los espacios se deben suprimir después de los nombres de función, operación o UDT.</span><span class="sxs-lookup"><span data-stu-id="97aa1-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

