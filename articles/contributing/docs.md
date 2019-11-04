---
title: Documentación de contribución | Microsoft Docs
description: Documentación de contribución
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183682"
---
# <a name="improving-documentation"></a>Mejorar la documentación #

La documentación del kit de desarrollo de Quantum toma varias formas diferentes, de modo que la información esté disponible para los desarrolladores de Quantum.

Siguiendo los principios de [documentos como código](https://www.writethedocs.org/guide/docs-as-code/), toda la documentación del kit de desarrollo de Quantum se formatea como código y se administra mediante Git de la misma manera que el código fuente que se usa para crear el kit de desarrollo de Quantum.
En su mayor parte, la documentación de respaldo del código consta de varias formas de [Markdown](https://daringfireball.net/projects/markdown/), un lenguaje para escribir texto con formato enriquecido en un formato de texto sin formato que es fácil de usar en la línea de comandos, en IDE y con control de código fuente.
De igual forma, adoptamos la biblioteca [MathJax](https://www.mathjax.org/) para permitir el formato de matemáticas en la documentación mediante el lenguaje latex, tal como se detalla más adelante.


Dicho esto, cada forma de documentación varía ligeramente en los detalles:

- La **documentación conceptual** consta de un conjunto de artículos que se publican en https://docs.microsoft.com/quantum y que describen todo, desde los aspectos básicos de la informática Quantum hasta las especificaciones técnicas de los formatos de intercambio. Estos artículos están escritos en [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), una variante de Markdown que se usa para crear conjuntos de documentación enriquecidos.
- La **referencia de API** es un conjunto de páginas para cada función de Q #, operación y tipo definido por el usuario, publicadas en https://docs.microsoft.com/qsharp/api/. Estas páginas documentan las entradas y operaciones en cada una de las llamadas, junto con ejemplos y vínculos a más información. La referencia de la API se extrae automáticamente de los pequeños documentos de DFM en el código fuente de Q # como parte de cada versión.
- Los archivos **léame<!---->. MD** incluidos en cada ejemplo y Kata describen cómo usar ese ejemplo o Kata se usa, lo que cubre y cómo se relaciona con el resto del kit de desarrollo de Quantum. Estos archivos se escriben mediante [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), una alternativa más ligera a DFM que es popular para adjuntar documentación directamente a los repositorios de código.

## <a name="contributing-to-the-conceptual-documentation"></a>Contribución a la documentación conceptual ##

Para contribuir a la mejora de la documentación conceptual o del archivo Léame, comienza con una solicitud de incorporación de cambios en [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)o [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), como es adecuado.
Aquí describiremos más acerca de las solicitudes de incorporación de cambios, pero por ahora hay algunas cosas que es conveniente tener en cuenta a la vez que mejora la documentación:

- Los lectores acuden a la documentación del kit de desarrollo de Quantum desde una amplia gama de conocimientos. Todo el mundo de los estudiantes de la escuela alta desea aprender algo nuevo y emocionante a través de un profesorado que realice una investigación de Quantum Computing, debería poder sacar algo de la documentación. En la medida de lo posible, no asuma un conocimiento amplio de la parte de los lectores, ya que pueden empezar. Es más útil si puede proporcionar descripciones claras y accesibles, o puede proporcionar vínculos a otros recursos para obtener más información.
- Los conjuntos de documentación no se diseñan como libros o documentos, en los que los lectores llegarán a lo que podría parecer "intermedio". Por ejemplo, es posible que los motores de búsqueda no sugieran el índice o que un amigo haya enviado un vínculo intentando ayudarlos. Intente ayudar a su lector proporcionando siempre un contexto claro, junto con los vínculos cuando corresponda.
- Algunos lectores buscarán instrucciones y definiciones abstractas más útiles, mientras que otros sistemas de lectura funcionan mejor mediante la extrapolación de ejemplos concretos. Proporcionar tanto el caso general como los ejemplos específicos pueden ayudar a ambos lectores a sacar el máximo partido de la programación de Quantum.
- Especialmente si también ha escrito el código que se documenta, puede que le resulte obvio que no es evidente para el lector. No hay una mejor manera de programar, por lo que, con independencia de lo inteligente o experimentado que sea un lector, no puede adivinar en qué modelos de diseño encontró lo más útil para expresar sus ideas en el código. Saber cómo un lector puede esperar hacer uso del código puede ayudar a proporcionar ese contexto.
- Muchos miembros de la comunidad de programación Quantum son investigadores académicos y se reconocen principalmente a través de citas para sus contribuciones a la comunidad. Además de ayudar a los lectores a encontrar materiales adicionales, no se olvide de mencionar correctamente las salidas académicas, como documentos, conversaciones, entradas de blog y herramientas de software, que pueden ayudar a los colaboradores académicos a seguir llevando a cabo el mejor trabajo para mejorar la comunidad.
- La comunidad de programación Quantum es una comunidad amplia y maravillosamente diversa. El uso de pronombres de género en ejemplos de terceros (por ejemplo, "Si un usuario...,...") puede trabajar para excluir en lugar de incluirlos. La Cognizant de los nombres de las personas en citas y vínculos, y de la inclusión correcta de caracteres que no sean ASCII, puede servir para la diversidad de la comunidad mostrando el respeto de sus miembros. Del mismo modo, muchas palabras del idioma inglés se usan a menudo de forma Hateful, de modo que su uso en la documentación técnica pueda causar daños tanto a lectores individuales como a la comunidad en gran medida.

## <a name="contributing-to-the-api-references"></a>Contribución a las referencias de API ##

Para contribuir a una mejora en las referencias de API, es más útil abrir una solicitud de incorporación de cambios directamente en el código que se documenta.
Cada función, operación o tipo definido por el usuario admite un Comentario de documentación (indicado con `///` en lugar de `//`).
Al compilar cada versión del kit de desarrollo de Quantum, estos comentarios se usan para generar la referencia de API en https://docs.microsoft.com/qsharp/api/ , incluidos los detalles sobre las entradas y salidas de cada una de ellas, las suposiciones a las que se puede llamar y ejemplos de cómo usarlas.

> [!IMPORTANT]
> Asegúrese de no editar manualmente la documentación de API generada, ya que estos archivos se sobrescriben con cada nueva versión.
> Le agradecemos su contribución a la comunidad y querrá asegurarse de que los cambios continúan para ayudar a los usuarios a publicarse después del lanzamiento.

Por ejemplo, considere una operación `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
Un Comentario de documentación debe ayudar a un usuario a obtener información sobre cómo interpretar `angles`, lo que la operación presupone sobre el estado inicial de `register`, qué efecto tiene `register` y así sucesivamente.
Cada una de estas partes de la información se puede proporcionar al compilador de preguntas y respuestas con una sección de Markdown con un nombre especial en el comentario de la documentación.
En el ejemplo de `PrepareTrialState`, podríamos escribir algo parecido a lo siguiente:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Además de la práctica general de escritura de documentación, al escribir comentarios de documentación de API, le ayuda a tener presentes algunos aspectos:

- El formato de cada comentario de documentación tiene que coincidir con lo que el compilador de preguntas y respuestas espera para que la documentación aparezca correctamente. Algunas secciones, como `/// # Remarks` permiten el contenido de forma libre, mientras que las secciones como `/// # See Also` sección son más restrictivas.
- Un lector puede leer la documentación de la API en el sitio principal de referencia de API, en el Resumen de cada espacio de nombres, o incluso desde dentro de su IDE mediante el uso de información de desplazamiento. Asegurarse de que `/// # Summary` no es más que una oración ayuda a su lector a ordenar rápidamente si necesitan leer más o buscar en otro lugar, y puede ayudar a realizar un análisis rápido de los resúmenes de los espacios de nombres.
- Es posible que la documentación se desenrede mucho más tiempo que el propio código, pero eso es correcto. Incluso un pequeño fragmento de código puede tener efectos inesperados en los usuarios que no conocen el contexto en el que existe ese código. Al proporcionar ejemplos concretos y explicaciones claras, puede ayudar a los usuarios a hacer el mejor uso del código que están a su disposición.

<!-- ## LaTeX Formatting ##

**TODO** -->
