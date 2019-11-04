---
title: 'Guía de estilo de Q # | Microsoft Docs'
description: Guía de estilo de preguntas y respuestas
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463313"
---
# <a name="q-style-guide"></a>Guía de estilo de preguntas y respuestas #
## <a name="general-conventions"></a>Convenciones generales ##

Las convenciones sugeridas en esta guía están pensadas para facilitar la lectura y comprensión de los programas y las bibliotecas escritos en preguntas y respuestas.

## <a name="guidance"></a>Guía

Sugerimos:

- No ignore nunca una Convención a menos que lo haga de forma intencionada con el fin de proporcionar código más legible y comprensible para los usuarios.

## <a name="naming-conventions"></a>Convenciones de nomenclatura ##

Al ofrecer el kit de desarrollo de Quantum, nos esforzamos por los nombres de función y de operación que ayudan a los desarrolladores de Quantum a escribir programas que son fáciles de leer y que minimizan la sorpresa.
Una parte importante de esto es que, cuando se eligen nombres para funciones, operaciones y tipos, se establece el *vocabulario* que los programadores usan para expresar los conceptos de Quantum. con nuestras opciones, nos ayudaremos o entorpeceremos su esfuerzo para comunicarse claramente.
Esto nos da la responsabilidad de asegurarse de que los nombres que presentamos ofrecen una claridad en lugar de la ocultación.
En esta sección, detallamos cómo se cumple esta obligación en términos de instrucciones explícitas que nos ayudan a hacer lo mejor en la comunidad de desarrollo de preguntas y respuestas.

### <a name="operations-and-functions"></a>Operaciones y funciones ###

Una de las primeras cosas que debe establecer un nombre es si un símbolo determinado representa una función o una operación.
La diferencia entre las funciones y las operaciones es fundamental para entender cómo se comporta un bloque de código.
Para comunicar la distinción entre las funciones y las operaciones con los usuarios, confiamos en que las operaciones de Quantum de los modelos Q # usan efectos secundarios.
Es decir, una operación *realiza* alguna acción.

Por el contrario, las funciones describen las relaciones matemáticas entre los datos.
La expresión `Sin(PI() / 2.0)` *es* `1.0`y no implica nada sobre el estado de un programa o de su qubits.

Resumen, las operaciones realizan cosas mientras que las funciones son cosas.
Esta distinción sugiere que denominamos operaciones como verbos y funciones como nombres.

> [!NOTE]
> Cuando se declara un tipo definido por el usuario, una nueva función que crea instancias de ese tipo se define implícitamente al mismo tiempo.
> Desde esa perspectiva, los tipos definidos por el usuario se deben denominar nombres para que el propio tipo y la función constructora tengan nombres coherentes.

Cuando sea razonable, asegúrese de que los nombres de operación comienzan por verbos que indican claramente el efecto que realiza la operación.
Por ejemplo:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Un caso que merece mención especial es cuando una operación toma otra operación como entrada y la llama.
En tales casos, la acción realizada por la operación de entrada no está clara cuando se define la operación externa, de modo que el verbo derecho no se borra inmediatamente.
Se recomienda el `Apply`de verbo, como en `ApplyIf`, `ApplyToEach`y `ApplyToFirst`.
Otros verbos también pueden resultar útiles en este caso, como en `IterateThroughCartesianPower`.

| Verbo | Efecto esperado |
| ---- | ------ |
| Solicitar | Se llama a una operación que se proporciona como entrada. |
| Assert | Un simulador comprueba una hipótesis sobre el resultado de una posible medida Quantum. |
| Presupuesto | Se devuelve un valor clásico que representa una estimación dibujada a partir de una o más medidas |
| Measure | Se realiza una medición de cuanto y el resultado se devuelve al usuario. |
| Preparativos | Un registro determinado de qubits se inicializa en un estado determinado. |
| Ejemplo | Un valor clásico se devuelve de forma aleatoria desde alguna distribución |

En el caso de las funciones, se recomienda evitar el uso de verbos en favor de los nombres comunes (vea las instrucciones sobre los nombres adecuados a continuación) o adjetivos:

- `ConstantArray`
- `Head`
- `LookupFunction`

En concreto, en casi todos los casos, se recomienda usar los participles anteriores, donde corresponda para indicar que un nombre de función está conectado fuertemente a una acción o efecto secundario en otro lugar de un programa Quantum.
Por ejemplo, `ControlledOnInt` usa el formulario participio de la parte del verbo "control" para indicar que la función actúa como adjetivo para modificar su argumento.
Este nombre tiene la ventaja adicional de buscar coincidencias con la semántica del functor integrada `Controlled`, como se describe más adelante.
Del mismo modo, los nombres de _agente_ se pueden usar para construir nombres de función y UDT a partir de los nombres de operación, como en el caso del nombre `Encoder` para un UDT que esté fuertemente asociado a `Encode`.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Usar verbos para nombres de operación.
- Utilice sustantivos o adjetivos para los nombres de función.
- Utilice sustantivos para los atributos y tipos definidos por el usuario.
- En el caso de todos los nombres a los que se puede llamar, use `CamelCase` en preferencias fuertes para `pascalCase`, `snake_case`o `ANGRY_CASE`. En concreto, asegúrese de que los nombres que se puedan llamar comienzan con letras mayúsculas.
- En el caso de todas las variables locales, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`. En concreto, asegúrese de que las variables locales comienzan con letras minúsculas.
- Evite el uso de subrayados `_` en los nombres de función y de operación; Cuando se necesiten niveles adicionales de jerarquía, use espacios de nombres y alias de espacio de nombres.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | name | description |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Desactive el uso de un verbo ("Reflect") para indicar el efecto de la operación. |
| ☒ | <s>`operation XRotation`</s> | El uso de la frase de nombre sugiere la función, en lugar de la operación. |
| ☒ | <s>`operation search_oracle`</s> | El uso de `snake_case` de la notación de Q #. |
| ☒ | <s>`operation Search_Oracle`</s> | El uso de un carácter de subrayado interno al nombre de la operación sirve de notación de Q #. |
| ☑ | `function StatePreparationOracle` | El uso de la frase de nombre sugiere que la función devuelve una operación. |
| ☑ | `function EqualityFact` | Desactive el uso de sustantivo ("Fact") para indicar que se trata de una función, mientras que el adjetivo. |
| ☒ | <s>`function GetRotationAngles`</s> | El uso de verbo ("Get") sugiere que se trata de una operación. |
| ☑ | `newtype GeneratorTerm` | El uso de la frase se refiere claramente al resultado de llamar al constructor UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | El uso de la frase verbal sugiere que el constructor UDT es una operación. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | El uso de nombre de frase comunica el uso del atributo. |

***

### <a name="shorthand-and-abbreviations"></a>Abreviaturas y abreviaturas ###

A pesar de los consejos anteriores, hay muchas formas de taquigrafía que ven un uso común y generalizado en la informática Quantum.
Se recomienda usar una abreviatura común y existente donde exista, especialmente para las operaciones que son intrínsecas al funcionamiento de un equipo de destino.
Por ejemplo, elegimos el nombre `X` en lugar de `ApplyX`y `Rz` en lugar de `RotateAboutZ`.
Cuando se usa esta forma abreviada, los nombres de operación deben estar en mayúsculas (por ejemplo: `MAJ`).

Es necesario tener cuidado al aplicar esta Convención en el caso de acrónimos de uso frecuente y siglas como "QFT" para "transformación de Fourier de Quantum".
Sugerimos las siguientes convenciones generales de .NET para el uso de acrónimos y siglas en nombres completos, lo que prescribe:

- los acrónimos de dos letras y siglas se denominan en mayúsculas (por ejemplo: `BE` para "Big-endian").
- todos los acrónimos más largos y siglas se denominan en `CamelCase` (por ejemplo: `Qft` para "transformación de Fourier de Quantum")

Por lo tanto, una operación que implementa QFT podría llamarse `QFT` como una abreviatura o escribirse como `ApplyQft`.

En el caso de las operaciones y funciones especialmente utilizadas, puede ser conveniente proporcionar un nombre abreviado como _alias_ para una forma más larga:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Considere la posibilidad de usar nombres abreviados comúnmente aceptados y ampliamente utilizados cuando corresponda.
- Use mayúsculas para abreviar.
- Use mayúsculas para acrónimos cortos (dos letras) y siglas.
- Use `CamelCase` para acrónimos más largos (tres o más letras) y siglas.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | name | description |
|---|------|-------------|
| ☑ | `X` | Abreviatura bien entendida para "aplicar una transformación de $X $" |
| ☑ | `CNOT` | Abreviatura bien entendida para "controlado" |
| ☒ | <s>`Cnot`</s> | La abreviatura no debe estar en `CamelCase`. |
| ☑ | `ApplyQft` | El inicio común "QFT" aparece como parte de un nombre de formato largo. |
| ☑ | `QFT` | El inicio común "QFT" aparece como parte de un nombre abreviado. |



***


### <a name="proper-nouns-in-names"></a>Nombres correctos en nombres ###

Mientras que en la física es habitual nombrar cosas después de que la primera persona publique sobre ellas, la mayoría de los Physicists no están familiarizados con los nombres de todos y el historial.
Confiar demasiado en las convenciones de nomenclatura de la física puede, por tanto, imponer una barrera importante a la entrada, ya que los usuarios de otros terrenos deben aprender un gran número de nombres aparentemente opacos con el fin de usar operaciones y conceptos comunes.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Por lo tanto, se recomienda que, siempre que sea razonable, los nombres comunes que describen un concepto se adopten en una buena preferencia con los nombres adecuados que describen el historial de publicaciones de un concepto.
Como ejemplo concreto, las operaciones de intercambio y control de subestado que se controlan a menudo se denominan "Fredkin" y "Toffoli" en la literatura académica, pero se identifican en Q # principalmente como `CSWAP` y `CCNOT`.
En ambos casos, los comentarios de la documentación de la API proporcionan nombres de sinónimos basados en nombres adecuados, junto con todas las citas adecuadas.

Esta preferencia es especialmente importante dado que el uso de los nombres adecuados siempre será necesario: Q # sigue la tradición establecida por muchos lenguajes clásico, por ejemplo, y hace referencia a `Bool` tipos en referencia a la lógica booleana, que a su vez se denomina en honor de George bool.
Unos pocos conceptos de Quantum se denominan de forma similar, incluido el tipo de `Pauli` integrado en el lenguaje de preguntas y respuestas.
Al minimizar el uso de los nombres adecuados en los casos en los que no es esencial, se reduce el impacto en el que no se pueden evitar razonablemente los nombres adecuados.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance) 

Sugerimos:

- Evite el uso de nombres propios en los nombres.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

***

### <a name="type-conversions"></a>Conversiones de tipos ###

Como Q # es un lenguaje fuertemente tipado y con tipos estáticos, un valor de un tipo solo se puede usar como un valor de otro tipo mediante una llamada explícita a una función de conversión de tipos.
Esto contrasta con los lenguajes que permiten a los valores cambiar tipos de forma implícita (por ejemplo: promoción de tipos) o a través de la conversión.
Como resultado, las funciones de conversión de tipos desempeñan un papel importante en el desarrollo de la biblioteca de Q # y constituyen una de las decisiones más frecuentes sobre la nomenclatura.
Sin embargo, tenemos en cuenta que, dado que las conversiones de tipo siempre son _deterministas_, se pueden escribir como funciones y, por lo tanto, se incluyen en el Consejo anterior.
En concreto, se recomienda que las funciones de conversión de tipos nunca se denominen como verbos (por ejemplo, `ConvertToX`) o frases de preposicional de adverbio (`ToX`), pero se deben denominar frases de preposicional de adjetivo que indiquen los tipos de origen y destino (`XAsY`).
Al enumerar los tipos de matriz en los nombres de funciones de conversión de tipos, se recomienda el `Arr`abreviado.
Salvo en circunstancias excepcionales, se recomienda asignar un nombre a todas las funciones de conversión de tipos mediante `As` para que se puedan identificar rápidamente.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Si una función convierte un valor de tipo `X` en un valor de tipo `Y`, use el nombre `AsY` o `XAsY`.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | name | description |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | La preposición "to" da como resultado una frase verbal, que indica una operación y no una función. |
| ☒ | <s>`AsDouble`</s> | El tipo de entrada no está claro en el nombre de la función. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Los tipos de entrada y salida aparecen en el orden equivocado. |
| ☑ | `ResultArrAsBoolArr` | Tanto los tipos de entrada como los de salida están claros. |

***

### <a name="private-or-internal-names"></a>Nombres privados o internos ###

En muchos casos, un nombre está pensado exclusivamente para usarse internamente en una biblioteca o proyecto y no es una parte garantizada de la API ofrecida por una biblioteca.
Resulta útil indicar claramente que este es el caso cuando se asignan nombres a funciones y operaciones para que las dependencias accidentales del código solo interno se hagan obvias.
Si una operación o función no está pensada para su uso directo, sino que debe ser usada por una función que admita la coincidencia que actúa por aplicación parcial, considere la posibilidad de usar un nombre que empiece por `_` para la que se puede llamar parcialmente.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Cuando una función, una operación o un tipo definido por el usuario no forma parte de la API pública para un programa o biblioteca de Q #, asegúrese de que su nombre comienza con un carácter de subrayado inicial (`_`).

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | name | description |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | El carácter de subrayado `_` no debe aparecer al final del nombre. |
| ☑ | `_ApplyDecomposedOperation` | El carácter de subrayado `_` al principio indica claramente que esta operación solo es para uso interno. |

***

### <a name="variants"></a>Las ###

Aunque es posible que esta limitación no se conserve en versiones futuras de Q #, es actualmente el caso de que a menudo existan grupos de operaciones o funciones relacionadas que se diferencian por los inconvenientes que admiten sus entradas, o por los tipos concretos de sus argumentos.
Estos grupos se pueden distinguir con el mismo nombre de raíz, seguido de una o dos letras que indican su variante.

| Sufijo | Significado |
|--------|---------|
| `A` | Se espera que la entrada sea compatible con `Adjoint` |
| `C` | Se espera que la entrada sea compatible con `Controlled` |
| `CA` | Se espera que la entrada admita `Controlled` y `Adjoint` |
| `I` | La entrada o las entradas son del tipo `Int` |
| `D` | La entrada o las entradas son del tipo `Double` |
| `L` | La entrada o las entradas son del tipo `BigInt` |

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Si una función u operación no está relacionada con funciones u operaciones similares por los tipos y la compatibilidad con las entradas de las entradas, no use un sufijo.
- Si una función u operación está relacionada con funciones u operaciones similares según los tipos y la compatibilidad con las entradas más inactivas, use los sufijos que se indican en la tabla anterior para distinguir las variantes.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumentos y variables ###

Un objetivo clave del código de preguntas y respuestas para una función u operación es que sea fácil de leer y comprender.
Del mismo modo, los nombres de las entradas y los argumentos de tipo deben comunicar cómo se usará una función o un argumento una vez proporcionado.


# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- En el caso de todos los nombres de variable y de entrada, use `pascalCase` en preferencias fuertes para `CamelCase`, `snake_case`o `ANGRY_CASE`.
- Los nombres de entrada deben ser descriptivos; Evite los nombres de uno o dos letras siempre que sea posible.
- Las operaciones y funciones que aceptan exactamente un argumento de tipo deben indicar que el argumento de tipo se `T` cuando su rol es obvio.
- Si una función u operación toma varios argumentos de tipo o si el rol de un solo argumento de tipo no es obvio, considere la posibilidad de usar una palabra corta en mayúsculas precedida por `T` (por ejemplo: `TOutput`) para cada tipo.
- No incluya nombres de tipo en los nombres de argumento y variable; Esta información puede ser proporcionada por el entorno de desarrollo.
- Denota los tipos escalares por sus nombres literales (`flagQubit`) y los tipos de matriz en plural (`measResults`).
  En el caso de las matrices de qubits en particular, considere la posibilidad de que estos tipos se denotan por `Register` donde el nombre hace referencia a una secuencia de qubits que están estrechamente relacionadas de algún modo.
- Las variables que se usan como índices en matrices deben comenzar con `idx` y deben ser singulares (por ejemplo: `things[idxThing]`).
  En concreto, evite fuertemente el uso de nombres de variable de una sola letra como índices; considere la posibilidad de usar `idx` como mínimo.
- Las variables que se usan para contener longitudes de matrices deben comenzar con `n` y deben ser plurales (por ejemplo: `nThings`).

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Tipo definido por el usuario denominado items ###

Los elementos con nombre de los tipos definidos por el usuario se deben denominar `CamelCase`, incluso en la entrada a constructores UDT.
Esto ayuda a tener claramente separados los elementos con nombre de las referencias a variables de ámbito local cuando se usa la notación de descriptor de acceso (por ejemplo, `callable::Apply`) o la notación de copia y actualización (`set arr w/= Data <- newData`).

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Los elementos con nombre de los constructores UDT deben tener el nombre `CamelCase`; es decir, deben comenzar con mayúsculas iniciales.
- Los elementos con nombre que se resuelven como operaciones se deben denominar fases de verbo.
- Los elementos con nombre que no se resuelven en las operaciones deben denominarse frases.
- En el caso de los UDT que ajustan las operaciones, se debe definir un único elemento con nombre denominado `Apply`.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | Snippet | description |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | El nombre `Apply` es una frase de verbo con formato `CamelCase`, lo que sugiere que el elemento con nombre es una operación. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Los elementos con nombre deben empezar con una letra mayúscula inicial. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Los elementos con nombre que se resuelven en funciones deben denominarse frases, no como frases verbales. |

***

## <a name="input-conventions"></a>Convenciones de entrada ##

Cuando un desarrollador llama a una operación o una función, las distintas entradas a esa operación o función deben especificarse en un orden determinado, lo que aumenta la carga cognitiva a la que se enfrenta un desarrollador para hacer uso de una biblioteca.
En particular, la tarea de recordar los pedidos de entrada suele ser una distracción de la tarea a mano: programación de una implementación de un algoritmo Quantum.
Aunque la compatibilidad con IDE enriquecida puede mitigar esto en gran medida, un buen diseño y adherencia a convenciones comunes también puede ayudar a minimizar la carga cognitiva impuesta por una API.

Siempre que sea posible, puede ser útil reducir el número de entradas que espera una operación o una función, de modo que el rol de cada entrada sea más evidente de inmediato para los desarrolladores que llaman a esa operación o función y a los desarrolladores que leen ese código más adelante.
Especialmente cuando no es posible o razonable reducir el número de argumentos para una operación o función, es importante tener una ordenación coherente que minimice la sorpresa que un usuario se enfrenta al predecir el orden de las entradas.

Se recomienda usar convenciones de ordenación de entrada que deriven en gran medida del pensamiento de la aplicación parcial como generalización de currificación f (x, y) ≡ f (x) (y).
Por lo tanto, la aplicación parcial de los primeros argumentos debe dar lugar a una invocable que sea útil en su propio derecho siempre que sea razonable.
Siguiendo este principio, considere la posibilidad de usar el siguiente orden de argumentos:

- Argumentos clásicos no Invocables como ángulos, vectores de potencias, etc.
- Argumentos a los que se puede llamar (funciones y argumentos).
  Si las funciones y las operaciones se toman como argumentos, considere la posibilidad de colocar las operaciones después de las funciones.
- Colecciones de las que actúan argumentos Invocables de una manera similar a `Map`, `Iter`, `Enumerate`y `Fold`.
- Argumentos de qubit usados como controles.
- Argumentos de qubit usados como destinos.

Considere una operación `ApplyPhaseEstimationIteration` para su uso en la estimación de fase que toma un ángulo y un Oracle, pasa el ángulo a `Rz` modificado por una matriz de factores de escala diferentes y, a continuación, controla las aplicaciones de Oracle.
Se deben ordenar las entradas a `ApplyPhaseEstimationIteration` de la siguiente manera:

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
Como caso especial de minimizar sorpresa, algunas funciones y operaciones imitan el comportamiento de los funcntes integrados `Adjoint` y `Controlled`.
Por ejemplo, `ControlledOnInt<'T>` tiene el tipo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, de modo que `ControlledOnInt<Qubit[]>(5, _)` actúa como el functor `Controlled`, pero en la condición de que el registro del control representa el estado $ \ket{5} = \ket{101}$.
Por lo tanto, un programador espera que las entradas en `ControlledOnInt` colocar el último que se puede transformar y que la operación resultante toma como su `(Qubit[], 'T)` de entrada---el mismo orden que el de la salida de `Controlled` functor.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Use pedidos de entrada coherentes con el uso de la aplicación parcial.
- Use órdenes de entrada coherentes con los funcdores integrados.
- Coloque todas las entradas clásicas antes de cualquier entrada de Quantum.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

***

## <a name="documentation-conventions"></a>Convenciones de documentación ##

El lenguaje de preguntas y respuestas permite adjuntar documentación a operaciones, funciones y tipos definidos por el usuario mediante el uso de comentarios de documentación con formato especial.
Los comentarios de la documentación, que se indican mediante barras diagonales triples (`///`), son pequeños documentos [de Markdown DocFXs](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que se pueden usar para describir el propósito de cada operación, función y tipo definido por el usuario, qué entradas esperan y así sucesivamente.
El compilador proporcionado con el kit de desarrollo de Quantum extrae estos comentarios y los usa para ayudar a compuestas documentación similar a la de https://docs.microsoft.com/quantum.
Del mismo modo, el servidor de lenguaje proporcionado con el kit de desarrollo de Quantum usa estos comentarios para proporcionar ayuda a los usuarios cuando se mantiene el mouse sobre los símbolos en su código de preguntas y respuestas.
El uso de los comentarios de la documentación puede ayudar a los usuarios a facilitar el código proporcionando una referencia útil para los detalles que no se expresan fácilmente mediante las demás convenciones de este documento.

<div class="nextstepaction">
    [Referencia](xref:microsoft.quantum.language.statements#documentation-comments) de la sintaxis de comentarios de documentación
</div>

Con el fin de usar esta funcionalidad de forma eficaz para ayudar a los usuarios, se recomienda tener presentes algunas cosas a la vez que escribe comentarios de documentación.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance)

Sugerimos:

- Cada función pública, operación y tipo definido por el usuario deben ir precedidos de un Comentario de documentación.
- Como mínimo, cada comentario de documentación debe incluir las siguientes secciones:
    - Resumen
    - Entrada
    - Salida (si es aplicable)
- Asegúrese de que todos los resúmenes son dos oraciones o menos. Si necesita más espacio, proporcione una `# Description` sección inmediatamente después de `# Summary` con detalles completos.
- Cuando sea razonable, no incluya cálculos matemáticos, ya que no todos los clientes admiten la notación TeX en resúmenes. Tenga en cuenta que al escribir documentos de Prose (por ejemplo, TeX o Markdown), puede ser preferible usar longitudes de línea más largas.
- Proporcione todas las expresiones matemáticas relevantes en la sección `# Description`.
- Al describir las entradas, no repita los tipos de cada entrada, ya que el compilador y el riesgo de introducir incoherencia pueden inferirlos.
- Proporcione ejemplos según corresponda, cada uno en su propia sección `# Example`.
- Describa brevemente cada ejemplo antes de enumerar el código.
- Cite todas las publicaciones académicas relevantes (por ejemplo, documentos, acciones, entradas de blog e implementaciones alternativas) en una `# References` sección como una lista de vínculos con viñetas.
- Asegúrese de que todos los vínculos de cita son identificadores permanentes e inmutables (DOIs o números de arXiv con control de versiones), siempre que sea posible.
- Cuando una operación o función está relacionada con otras operaciones o funciones mediante variantes de functor, enumere otras variantes como viñetas en la sección `# See Also`.
- Deje una línea de comentario en blanco entre las secciones de nivel 1 (`/// #`), pero no deje una línea en blanco entre las secciones de nivel 2 (`/// ##`).

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

#### <a name=""></a>☑ ####

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

## <a name="formatting-conventions"></a>Convenciones de formato ##

Además de las sugerencias anteriores, resulta útil ayudar a que el código sea lo más legible posible para usar reglas de formato coherentes.
Estas reglas de formato por naturaleza tienden a ser algo arbitrarias y muy sólidas a la estética personal.
No obstante, se recomienda mantener un conjunto coherente de convenciones de formato dentro de un grupo de colaboradores y, especialmente, en proyectos de preguntas y respuestas grandes, como el propio Kit de desarrollo de Quantum.
Estas reglas se pueden aplicar automáticamente mediante la herramienta de formato integrada con el compilador de preguntas y respuestas.

# <a name="guidancetabguidance"></a>[Guía](#tab/guidance) 

Sugerimos:

- Use cuatro espacios en lugar de pestañas para la portabilidad.
  Por ejemplo, en VS Code:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Ajuste de línea en 79 caracteres cuando sea razonable.
- Usar espacios alrededor de los operadores binarios.
- Use espacios a cada lado de los dos puntos usados para las anotaciones de tipo.
- Use un solo espacio después de las comas usadas en los literales de matriz y tupla (por ejemplo, en las entradas de funciones y operaciones).
- No use espacios después de la función, la operación o los nombres UDT, o después del `@` en las declaraciones de atributos.
- Cada declaración de atributo debe estar en su propia línea.

# <a name="examplestabexamples"></a>[Ejemplos](#tab/examples)

|   | Snippet | description |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Usar espacios alrededor de los operadores binarios. |
| ☒ | <s>`target:Qubit`</s> | Use espacios alrededor de los dos puntos de la anotación de tipo. |
| ☑ | `Example(a, b, c)` | Los elementos de la tupla de entrada se espacian correctamente para mejorar la legibilidad. |
| ☒ | <s>`Example (a, b, c)`</s> | Los espacios se deben suprimir después de los nombres de función, operación o UDT. |

***

