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
# <a name="q-file-structure"></a>Estructura de archivos de preguntas y respuestas

Cada operación Q #, función y tipo definido por el usuario se definen dentro de un espacio de nombres.

Un archivo de preguntas # consta de una secuencia de *declaraciones de espacios de nombres*.
Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario.
Una declaración de espacio de nombres puede contener cualquier número de cada tipo de declaración y en cualquier orden.
Siga estos vínculos para obtener más información sobre cómo declarar tipos, [operaciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)y [funciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types)dentro de un espacio de nombres.

El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.
En concreto, los comentarios de documentación (más detalles a continuación) para un espacio de nombres preceden a la declaración.

## <a name="namespace-declarations"></a>Declaraciones de espacios de nombres

Un archivo de preguntas # normalmente tendrá exactamente una declaración de espacio de nombres, pero puede tener ninguno (y estar vacío o contener solo comentarios) o puede contener varios espacios de nombres.
Las declaraciones de espacio de nombres no pueden estar anidadas.

El mismo espacio de nombres se puede declarar en varios archivos Q # que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.
En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.

Una declaración de espacio de nombres consta de la palabra clave `namespace` , seguida del nombre del espacio de nombres, una llave de apertura `{` , las declaraciones contenidas en el espacio de nombres y una llave de cierre `}` .
Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.` .
Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Intrinsic` son nombres de espacio de nombres válidos.
Por Convención, los símbolos de un nombre de espacio de nombres se escriben en mayúsculas, pero no es necesario.

Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.

## <a name="open-directives"></a>Directivas Open

Dentro de un bloque de espacio de nombres, la `open` Directiva se puede usar para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.
Esta `open` Directiva se compone de la `open` palabra clave, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.

> [!NOTE] 
> Todas las `open` directivas deben aparecer antes `function` `operation` de cualquier declaración, o `newtype` en el bloque de espacio de nombres.

Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido. Por ejemplo, dada la siguiente declaración de espacio de nombres y las directivas Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Si una operación declarada usa una operación `Op` de `Microsoft.Quantum.Intrinsic` , se llamaría simplemente mediante el uso de `Op` .
Sin embargo, si deseáramos llamar a una función determinada `Fn` de `Microsoft.Quantum.Math` , deberíamos llamarlo mediante `Math.Fn` .

La `open` Directiva se aplica a todo el bloque de espacio de nombres dentro de un archivo.
Por lo tanto, si fuera a definir un espacio de nombres adicional en el mismo archivo Q # que `NS` anteriormente, las operaciones, funciones o tipos definidos en el segundo espacio de nombres no tendrían acceso a nada desde `Microsoft.Quantum.Intrinsic` o `Microsoft.Quantum.Math` a menos que repetimos las directivas Open. 

Se debe hacer referencia a un tipo o al que se puede llamar en otro espacio de nombres que *no* esté abierto en el espacio de nombres actual mediante su nombre completo.
Por ejemplo, `Op` se debe hacer referencia a una operación denominada desde el `X.Y` espacio de nombres mediante su nombre completo `X.Y.Op` , a menos que el espacio de nombres se haya `X.Y` abierto anteriormente en el bloque actual. Como se mencionó anteriormente, incluso si se ha `X` abierto el espacio de nombres, no es posible hacer referencia a la operación como `Y.Op` .
Si se ha definido un nombre corto `Z` para `X.Y` en ese espacio de nombres y archivo, `Op` debe hacerse referencia a él como `Z.Op` . 

Normalmente es mejor incluir un espacio de nombres mediante una `open` Directiva.
Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.

Q # sigue las mismas reglas para asignar nombres a otros lenguajes .NET.
Sin embargo, Q # no admite referencias relativas a espacios de nombres.
Es decir, si se ha abierto el espacio de nombres `a.b` , una referencia a una operación denominada `c.d` *no* se resolverá en una operación con el nombre completo `a.b.c.d` .

## <a name="formatting"></a>Aplicación de formato

La mayoría de las instrucciones y directivas de Q # finalizan con un punto y coma de terminación, `;` .
Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones (vea a continuación) no requieren un punto y coma de finalización.
La descripción de cada instrucción indica si es necesario el punto y coma de terminación.

Las instrucciones, como las expresiones, las declaraciones y las directivas, pueden dividirse en varias líneas.
Se debe evitar tener varias instrucciones en una sola línea.

## <a name="statement-blocks"></a>Bloques de instrucciones

Las instrucciones Q # se agrupan en bloques de instrucciones.
Un bloque de instrucciones comienza con una apertura `{` y termina con un cierre `}` .

Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.

## <a name="comments"></a>Comentarios

Los comentarios comienzan con dos barras diagonales, `//` y continúan hasta el final de la línea.
Puede aparecer un Comentario en cualquier parte de un archivo de código fuente de preguntas y respuestas.

## <a name="documentation-comments"></a>Comentarios de documentación

Los comentarios que comienzan con tres barras diagonales, `///` , se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.
En ese caso, su contenido se toma como documentación para el tipo definido por el usuario o al que se puede llamar, como en otros lenguajes .NET.

Dentro de los `///` comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), donde se indican diferentes partes de la documentación con encabezados con el nombre especial.
Como extensión de Markdown, las referencias cruzadas a operaciones, funciones y tipos definidos por el usuario en Q # pueden incluirse mediante `@"<ref target>"` , donde `<ref target>` se reemplaza por el nombre completo del objeto de código al que se hace referencia.
Opcionalmente, un motor de documentación también puede admitir extensiones de Markdown adicionales.

Por ejemplo:

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

Los nombres siguientes se reconocen como encabezados de comentario de documentación.

- **Summary**: un breve resumen del comportamiento de una función u operación, o del propósito de un tipo. El primer párrafo del resumen se usa para la información de desplazamiento. Debe ser texto sin formato.
- **Descripción**: Descripción del comportamiento de una función u operación, o del propósito de un tipo. El Resumen y la descripción se concatenan para formar el archivo de documentación generado para la función, la operación o el tipo.
  La descripción puede contener símbolos y ecuaciones con formato LaTeX en línea.
- **Input**: Descripción de la tupla de entrada para una operación o función.
  Puede contener subsecciones de Markdown adicionales que indican cada elemento individual de la tupla de entrada.
- **Output**: Descripción de la tupla devuelta por una operación o función.
- **Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.
- **Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.
- **Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.
- **Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.
- **Referencias**: una lista de referencias y citas para el elemento que se documenta.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre [las operaciones y las funciones](xref:microsoft.quantum.guide.operationsfunctions) de preguntas y respuestas.