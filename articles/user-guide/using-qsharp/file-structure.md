---
title: Q# Estructura de archivos
description: Describe la estructura y la sintaxis de un Q# archivo.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833307"
---
# <a name="no-locq-file-structure"></a>Q# Estructura de archivos

Un Q# archivo consta de una secuencia de *declaraciones de espacios de nombres*.
Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario, y puede contener cualquier número de cada tipo de declaración y en cualquier orden.
Para obtener más información sobre las declaraciones dentro de un espacio de nombres, vea [tipos definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types), [operaciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)y [funciones](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.
En concreto, los comentarios de documentación para un espacio de nombres preceden a la declaración. Para obtener más información, consulte los [comentarios de documentación](#documentation-comments) en este artículo. 

## <a name="namespace-declarations"></a>Declaraciones de espacios de nombres

Un Q# archivo normalmente tiene solo una declaración de espacio de nombres, pero podría tener ninguno (y estar vacío o contener solo comentarios) o podría contener varios espacios de nombres.
Las declaraciones de espacio de nombres no se pueden anidar.

Puede declarar el mismo espacio de nombres en varios Q# archivos que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.
En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.

Una declaración de espacio de nombres consta de la palabra clave `namespace` , seguida del nombre del espacio de nombres y de las declaraciones contenidas en el espacio de nombres entre llaves `{ }` .
Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.` .
Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Intrinsic` son nombres de espacio de nombres válidos.
Por Convención, ponga en mayúsculas los símbolos en un nombre de espacio de nombres; sin embargo, esto no es necesario.

Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.

## <a name="open-directives"></a>Directivas Open

Dentro de un bloque de espacio de nombres, utilice la `open` Directiva para importar todos los tipos e Invocables declarados en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo.
Esta `open` Directiva se compone de la `open` palabra clave, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.

> [!NOTE] 
> Todas las `open` directivas deben aparecer antes `function` `operation` de cualquier declaración, o `newtype` en el bloque de espacio de nombres.

Opcionalmente, puede definir un nombre corto para el espacio de nombres abierto. Si se define un nombre corto, debe calificar todos los elementos de ese espacio de nombres por el nombre corto definido. Por ejemplo, dada la siguiente declaración de espacio de nombres y las directivas Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Si una operación declarada utiliza una operación `Op` de `Microsoft.Quantum.Intrinsic` , se llama simplemente mediante `Op` .
Sin embargo, para llamar a una función determinada `Fn` desde `Microsoft.Quantum.Math` , debe llamarlo mediante `Math.Fn` .

La `open` Directiva se aplica a todo el bloque de espacio de nombres dentro de un archivo.
Por lo tanto, si define un espacio de nombres adicional en el mismo Q# archivo que `NS` antes, las operaciones, funciones o tipos definidos en el segundo espacio de nombres no tendrán acceso a nada desde `Microsoft.Quantum.Intrinsic` o `Microsoft.Quantum.Math` a menos que repita las directivas Open. 

Para hacer referencia a un tipo o a invocable definido en otro espacio de nombres que *no* está abierto en el espacio de nombres actual, debe hacer referencia a él mediante su nombre completo.
Por ejemplo, dada una operación denominada `Op` del `X.Y` espacio de nombres:

* Debe hacer referencia a él mediante su nombre completo `X.Y.Op` , a menos que el `X.Y` espacio de nombres se haya abierto anteriormente en el bloque actual. 
* Incluso si `X` se abre el espacio de nombres, no es posible hacer referencia a la operación como `Y.Op` .
* Si ha definido el nombre corto `Z` de `X.Y` en ese espacio de nombres y archivo, debe hacer referencia a `Op` como `Z.Op` . 

Normalmente es mejor incluir un espacio de nombres mediante una `open` Directiva.
Se requiere el uso de un nombre completo si dos espacios de nombres definen construcciones con el mismo nombre y el origen actual utiliza construcciones de ambos.

Q# sigue las mismas reglas para asignar nombres a otros lenguajes de .NET.
Sin embargo, no Q# admite referencias relativas a espacios de nombres.
Por ejemplo, si el espacio de nombres `a.b` está abierto, una referencia a una operación denominada no se `c.d` resuelve como una operación con el nombre completo *not* `a.b.c.d` .

## <a name="formatting"></a>Formato

La mayoría de las Q# instrucciones y directivas finalizan con un punto y coma de terminación, `;` .
Las instrucciones y declaraciones como `for` y `operation` que finalizan con un bloque de instrucciones (vea la siguiente sección) no requieren un punto y coma de finalización.
La descripción de cada instrucción indica si es necesario el punto y coma de terminación.

Las instrucciones, como las expresiones, las declaraciones y las directivas, se pueden dividir en varias líneas.
Evite colocar varias instrucciones en una sola línea.

## <a name="statement-blocks"></a>Bloques de instrucciones

Q# las instrucciones se agrupan en bloques de instrucciones, que se incluyen entre llaves `{ }` . Un bloque de instrucciones comienza con una apertura `{` y termina con un cierre `}` .

Un bloque de instrucciones que se adjunta léxicamente dentro de otro bloque se considera un subbloque del bloque contenedor; los bloques que contienen y también se denominan bloques externos e internos.

## <a name="comments"></a>Comentarios

Los comentarios comienzan con dos barras diagonales, `//` y continúan hasta el final de la línea.
Un comentario puede aparecer en cualquier parte de un Q# archivo de código fuente.

## <a name="documentation-comments"></a>Comentarios de documentación

Los comentarios que comienzan con tres barras diagonales, `///` , se tratan de forma especial por el compilador cuando aparecen inmediatamente antes de un espacio de nombres, una operación, una especialización, una función o una definición de tipo.
En ese caso, el compilador los trata como documentación para el tipo definido por el usuario o al que se puede llamar, igual que otros lenguajes .NET.

Dentro de `///` los comentarios, el texto que se va a mostrar como parte de la documentación de la API tiene el formato [Markdown](https://daringfireball.net/projects/markdown/syntax), con distintas partes de la documentación indicada por encabezados con el nombre especial.
En Markdown, use la `@"<ref target>"` extensión para las operaciones de referencia cruzada, las funciones y los tipos definidos por el usuario en Q# . Reemplazar `<ref target>` por el nombre completo del objeto de código al que se hace referencia.
Los diferentes motores de documentación también pueden admitir extensiones Markdown adicionales.

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

Los nombres siguientes son válidos como encabezados de comentario de documentación.

- **Summary**: un breve resumen del comportamiento de una función u operación, o el propósito de un tipo. El primer párrafo del resumen se usa para la información de desplazamiento. Debe ser texto sin formato.
- **Descripción**: una descripción del comportamiento de una función u operación, o el propósito de un tipo. Juntos, el Resumen y la descripción forman el archivo de documentación generado para la función, la operación o el tipo.
  La descripción admite símbolos y ecuaciones con formato LaTeX en línea.
- **Input**: Descripción de la tupla de entrada para una operación o función.
  Puede contener subsecciones de Markdown adicionales que indican cada elemento de la tupla de entrada.
- **Output**: Descripción de la tupla devuelta por una operación o función.
- **Parámetros de tipo**: una sección vacía que contiene una subsección adicional para cada parámetro de tipo genérico.
- **Ejemplo**: un breve ejemplo de la operación, la función o el tipo en uso.
- **Comentarios**: varios Prose que describen algún aspecto de la operación, la función o el tipo.
- **Vea también**: una lista de nombres completos que indican funciones, operaciones o tipos definidos por el usuario relacionados.
- **Referencias**: una lista de referencias y citas para el elemento documentado.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información acerca de [las operaciones y las funciones](xref:microsoft.quantum.guide.operationsfunctions) de Q# .