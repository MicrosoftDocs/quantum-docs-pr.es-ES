---
title: Q# Conceptos básicos
description: Conceptos básicos de Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86f6538cf383f4e7c14255b38cfb1c141c8f991b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835526"
---
# <a name="no-locq-basics"></a>Q# Conceptos básicos

En este artículo se presenta una breve introducción a los bloques de creación básicos de Q# .

Para obtener información general sobre qué Q# es y dónde encaja como componente fundamental del kit de desarrollo de Quantum, vea [¿Qué es Q# ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>¿Qué es un programa Quantum?

Desde una perspectiva técnica, un programa Quantum es un conjunto determinado de subrutinas clásicas que, cuando se llama, realizan ciertas operaciones en un sistema Quantum.
Una consecuencia importante de esa vista es que un Q# programa no modela directamente qubits, sino que describe el modo en que un equipo controlado por clases interactúa con esos qubits.
Por diseño, no Q# define los Estados Quantum u otras propiedades de la mecánica de Quantum directamente.
Por ejemplo, tenga en cuenta el estado $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ descrito en la guía de [conceptos de procesamiento de Quantum](xref:microsoft.quantum.concepts.intro) .
Para preparar este estado en Q# , comience con los hechos que los qubits se inicializan en el estado $ \ket {0} $ y que $ \ket{+} = H\ket {0} $, donde $H $ es la [transformación Hadamard](xref:microsoft.quantum.glossary#hadamard), implementada por la [ `H` operación](xref:microsoft.quantum.intrinsic.h). El Q# código básico para inicializar y transformar un qubit, a continuación, tiene el siguiente aspecto:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Para obtener más información sobre cómo inicializar, o *asignar*, qubits, consulte [trabajar con qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Estados de Quantum en Q#

Lo importante es que el programa anterior no hace referencia explícitamente al estado en, Q# pero describe cómo el programa *transformó* el estado.
Con este enfoque, puede ser totalmente independiente de lo que *es* un estado de Quantum incluso en cada máquina de destino, lo que puede tener interpretaciones diferentes en función del equipo. 

Un Q# programa no puede Introspect en el estado de un qubit.
En su lugar, un programa puede llamar a operaciones como [`Measure`](xref:microsoft.quantum.intrinsic.measure) para obtener información de un qubit y llamar a operaciones como [`X`](xref:microsoft.quantum.intrinsic.x) y [`H`](xref:microsoft.quantum.intrinsic.h) para que actúen en el estado de un qubit.
Lo que realmente *hacen* estas operaciones solo se convierte en concreto por el equipo de destino que se usa para ejecutar el programa en particular Q# .
Por ejemplo, si se ejecuta el programa en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), el simulador realiza las operaciones matemáticas correspondientes en el sistema Quantum simulado.
Pero en el futuro, cuando el equipo de destino es un equipo Quantum real, llamar a tales operaciones en Q# dirige el equipo Quantum para realizar las operaciones *reales* correspondientes en el sistema Quantum *real* , por ejemplo, con precisión de impulsos de láser.

Un Q# programa vuelve a combinar estas operaciones definidas por un equipo de destino para crear nuevas operaciones de nivel superior para expresar el cálculo de Quantum.
De esta manera, facilita Q# la rápida expresión de Quantum subyacente de la lógica y los algoritmos de Quantum híbridos, mientras que también es general con respecto a la estructura de un equipo o simulador de destino.

## <a name="no-locq-operations-and-functions"></a>Q# operaciones y funciones

Concretamente, un Q# programa consta de *operaciones*, *funciones*y cualquier tipo definido por el usuario. 

Las operaciones se utilizan para describir las transformaciones de los sistemas Quantum y son el bloque de creación más importante de los Q# programas. Cada operación definida en Q# puede llamar a cualquier número de otras operaciones.

A diferencia de las operaciones, las funciones se usan para describir el comportamiento clásico puramente *determinista* y no tienen ningún efecto aparte de la informática de los valores clásico. Por ejemplo, supongamos que desea medir el qubits al final de un programa y agregar los resultados de la medida a una matriz.
En este caso, `Measure` es una *operación* que indica al equipo de destino que realice una medida en el qubits (real o simulado). Al mismo tiempo, *las funciones* controlan el proceso clásico de agregar los resultados devueltos a una matriz.

Juntas, las operaciones y las funciones se conocen como *Invocables*. La estructura y el comportamiento subyacentes se presentan y detallan en [operaciones y funciones en Q# ](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="no-locq-syntax-overview"></a>Q# Información general sobre la sintaxis

En la sintaxis de un lenguaje se describen las distintas combinaciones de símbolos que forman un programa sintácticamente correcto.
En Q# , los elementos de sintaxis se clasifican en tres grupos distintos: tipos, expresiones e instrucciones.

### <a name="types"></a>Tipos
Q# es un lenguaje fuertemente tipado, de modo que el uso cuidadoso de los tipos puede ayudar al compilador a proporcionar garantías seguras sobre los Q# programas en tiempo de compilación.
Además de los tipos primitivos estándar y específicos de Quantum, como, por ejemplo,,, `Int` `Bool` `Qubit` y `Result` , proporciona compatibilidad con los Q# tipos definidos por el usuario.

Para obtener descripciones de todos los tipos primitivos, detalles de tipos de matriz y tupla, y pasos para definir nuevos tipos dentro de un Q# archivo, vea [tipos en Q# ](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Expresiones
Una expresión en un lenguaje de programación es una combinación de una o más constantes, variables, operadores y funciones que el lenguaje de programación interpreta y evalúa como un valor específico.
En la mayoría de los tipos de un lenguaje, las expresiones de ese tipo pueden ser *literales* o símbolos enlazados a un valor de ese tipo.
Por ejemplo, `5` es un `Int` literal (por lo tanto, una expresión de tipo `Int` ) y si el símbolo `count` se enlaza al valor entero `5` , entonces `count` también es una expresión de tipo entero.

Además, una expresión puede constar de otras expresiones combinadas por ciertos operadores.
Por ejemplo, otra `Int` expresión que se evalúa como `5` es `2+3` .

Para obtener más información sobre las expresiones y los operadores compatibles en Q# , vea [expresiones de tipo en Q# ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instrucciones 
Una instrucción es una unidad sintáctica de un lenguaje de programación imperativo que expresa alguna acción que se va a llevar a cabo. Las instrucciones que contrastan con las expresiones en las instrucciones no devuelven resultados y se ejecutan únicamente para sus efectos secundarios. Sin embargo, las expresiones siempre devuelven un resultado y, a menudo, no tienen efectos secundarios. En Resumen, las Q# instrucciones se ejecutan, mientras que las expresiones se evalúan.

Un ejemplo sencillo de una instrucción en Q# es la asignación de un símbolo a una expresión:
```qsharp
let count = 5;
```

Un ejemplo más interesante es la `for` instrucción que admite la iteración e incluye un *bloque de instrucciones*.
Supongamos `qubits` que el símbolo se enlaza a un registro de qubits (técnicamente de tipo `Qubit[]` , o una matriz de `Qubit` tipos). Entonces
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
es una instrucción que recorre en iteración cada qubit del registro y realiza la `H` operación en cada uno de ellos. Tenga en cuenta que `H(qubit);` también es una instrucción propiamente dicha.

Puede usar cualquier expresión de llamada de tipo `Unit` (un `Unit` tipo no devuelve ninguna información) como una instrucción.
Este tipo de expresión es útil cuando se llama a operaciones en qubits que devuelven `Unit` porque el propósito de la instrucción es modificar el estado de Quantum implícito.
Las instrucciones de evaluación de expresiones requieren un punto y coma de finalización.

Las instrucciones se usan para compilar casi todos los aspectos de un Q# programa, y ninguna página única puede incluir toda la información relacionada con ellas.
Para obtener más información sobre la estructura léxica y el formato, vea [ Q# estructura de archivos](xref:microsoft.quantum.guide.filestructure); para obtener información sobre la asignación y el ámbito de los símbolos, vea [variables en Q# ](xref:microsoft.quantum.guide.variables)y, en el caso de bucles de flujo de control como `for` , vea [flujo de control en Q# ](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Pasos siguientes

Comience a obtener información sobre los [tipos en Q# ](xref:microsoft.quantum.guide.types).

Para obtener más información sobre las bases y la motivación Q# , consulte [¿por qué necesitamos Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
