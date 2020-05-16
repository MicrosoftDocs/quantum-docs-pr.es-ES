---
title: Conceptos básicos de preguntas y respuestas
description: 'Conceptos básicos de preguntas y respuestas #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431162"
---
# <a name="q-basics"></a>Conceptos básicos de preguntas y respuestas

En esta sección, presentamos una breve introducción a los bloques de creación básicos de preguntas y respuestas.

Para obtener una introducción rápida de lo que es Q # y de dónde encaja como componente fundamental del kit de desarrollo de Quantum, puede consultar [¿Qué es q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>¿Qué es un programa Quantum?

Desde una perspectiva técnica, un programa Quantum se puede considerar como un conjunto determinado de subrutinas clásicas que, cuando se llama, realizan ciertas operaciones en un sistema Quantum.
Una consecuencia importante de esa vista es que un programa escrito en Q # no modela directamente qubits, sino que describe cómo interactúa un equipo de control clásico con esos qubits.
Por diseño, Q #, por tanto, no define los Estados Quantum u otras propiedades de las mecánicas Quantum directamente.
Por ejemplo, tenga en cuenta el estado $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ descrito en la guía de [conceptos de procesamiento de Quantum](xref:microsoft.quantum.concepts.intro) .
Para preparar este estado en Q #, usamos los hechos que los qubits se inicializan en el estado $ \ket {0} $ y que $ \ket{+} = H\ket {0} $, donde $H $ es la transformación Hadamard, implementada por [ `H` Operation] (] (XREF: Microsoft. Quantum. Intrinsic. H):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Estados de Quantum en Q #

Lo importante es que, al escribir el programa anterior, no nos referimos explícitamente al estado en Q #, sino que describimos cómo el programa *transformó* el estado.
Esto nos permite ser totalmente independientes sobre lo que un estado de Quantum *tiene* incluso en cada máquina de destino, que podría tener interpretaciones diferentes en función del equipo. 

Un programa de preguntas # no tiene capacidad para Introspect en el estado de un qubit.
En su lugar, un programa puede llamar a operaciones como [`Measure`](xref:microsoft.quantum.intrinsic.measure) para obtener información de un qubit y llamar a operaciones como [`X`](xref:microsoft.quantum.intrinsic.x) y [`H`](xref:microsoft.quantum.intrinsic.h) para actuar en el estado de un qubit.
Lo que realmente *hacen* estas operaciones solo se convierte en concreto por el equipo de destino que se usa para ejecutar el programa de preguntas y respuestas determinado.
Por ejemplo, si ejecuta el programa en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), el simulador llevará a cabo las operaciones matemáticas correspondientes en el sistema Quantum simulado.
Pero en el futuro, cuando el equipo de destino es un equipo Quantum real, llamar a tales operaciones en Q # dirigirá el equipo Quantum para que realice las operaciones *reales* correspondientes en el sistema Quantum *real* (por ejemplo, con precisión de impulsos láser con tiempo).

Un programa de preguntas # vuelve a combinar estas operaciones, tal y como se define en un equipo de destino para crear nuevas operaciones de nivel superior para expresar el cálculo de Quantum.
De esta manera, Q # hace que sea fácil expresar el Quantum subyacente de la lógica y los algoritmos de Quantum híbridos, mientras que también son generales con respecto a la estructura de un equipo de destino o un simulador.

## <a name="q-operations-and-functions"></a>Operaciones y funciones de Q #

Concretamente, un programa de preguntas y respuestas se compone de *operaciones*, *funciones*y cualquier tipo definido por el usuario. 

Las operaciones se utilizan para describir las transformaciones de los sistemas Quantum y son el bloque de creación más básico de los programas de preguntas y respuestas. Cada operación definida en Q # puede llamar a cualquier número de otras operaciones.

A diferencia de las operaciones, las funciones se usan para describir el comportamiento clásico puramente *determinista* y no tienen ningún efecto aparte de la informática de los valores clásico. Por ejemplo, supongamos que nos gustaría medir el qubits al final de un programa y agregar los resultados de la medida a una matriz.
En este caso `Measure` , es una *operación* que indica al equipo de destino que realice una medida en el qubits (real o simulado) y que el proceso clásico de agregar los resultados devueltos a una matriz se controle mediante *funciones*.

En conjunto, las operaciones y las funciones se conocen como *Invocables*, y su estructura y comportamiento subyacentes se introducen en las [operaciones y las funciones en la página de preguntas y respuestas](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Información general sobre la sintaxis de Q #

En la sintaxis de un lenguaje se describen las distintas combinaciones de símbolos que forman un programa sintácticamente correcto.
En Q #, podemos clasificar los elementos de su sintaxis en tres grupos diferentes: tipos, expresiones e instrucciones.

### <a name="types"></a>Tipos
Q # es un lenguaje fuertemente tipado, de modo que el uso meticuloso de los tipos puede ayudar al compilador a proporcionar garantías seguras sobre los programas de Q # en tiempo de compilación.
Además de los tipos primitivos estándar y específicos de Quantum (por ejemplo,, `Int` , `Bool` `Qubit` y `Result` ), Q # proporciona compatibilidad con los tipos definidos por el usuario.
Todos los tipos primitivos de Q # se describen en los [tipos de la página de preguntas y respuestas](xref:microsoft.quantum.guide.types) , junto con los detalles sobre los tipos de matriz y tupla, así como la forma de definir nuevos tipos en un archivo de preguntas y respuestas.

### <a name="expressions"></a>Expresiones
Una expresión en un lenguaje de programación es una combinación de una o más constantes, variables, operadores y funciones que el lenguaje de programación interpreta y evalúa como un valor específico.
En la mayoría de los tipos de un lenguaje, las expresiones de ese tipo pueden ser *literales* o símbolos enlazados a un valor de ese tipo.
Por ejemplo, `5` es un `Int` literal (por lo tanto, una expresión de tipo `Int` ) y si el símbolo `count` se enlaza al valor entero `5` , entonces `count` también es una expresión de tipo entero.

Además, una expresión puede constar de otras expresiones combinadas con ciertos operadores.
Por lo tanto, otro ejemplo de una `Int` expresión que `5` se evalúa como es `2+3` .

Las posibles expresiones de tipos en Q #, así como los operadores compatibles que se pueden usar para formarlos, se detallan en las [expresiones de tipo en la página de Q #](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Instrucciones 
Una instrucción es una unidad sintáctica de un lenguaje de programación imperativo que expresa alguna acción que se va a llevar a cabo. Las instrucciones que contrastan con las expresiones en las instrucciones no devuelven resultados y se ejecutan únicamente para sus efectos secundarios, mientras que las expresiones siempre devuelven un resultado y, a menudo, no tienen efectos secundarios.
Esta distinción se observa con frecuencia en el texto: se evalúa una expresión, mientras que se ejecuta una instrucción.

Un ejemplo muy básico de una instrucción en Q # es la asignación de un símbolo a una expresión:
```qsharp
let count = 5;
```

Un ejemplo ligeramente más interesante es la `for` instrucción que admite la iteración e incluye un *bloque de instrucciones*.
Supongamos que `qubits` el símbolo está enlazado a un registro de qubits (técnicamente de tipo `Qubit[]` , es decir, una matriz de `Qubit` tipos). A continuación
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
es una instrucción que recorre en iteración cada qubit del registro y realiza la `H` operación en cada uno. Tenga en cuenta que `H(qubit);` también es una instrucción propiamente dicha.

De hecho, cualquier expresión de llamada de tipo `Unit` (aquellas llamadas que no devuelven información) se puede usar como una instrucción.
Esto se usa principalmente cuando se llama a operaciones en qubits que devuelven `Unit` porque el propósito de la instrucción es modificar el estado de Quantum implícito.
Las instrucciones de evaluación de expresiones requieren un punto y coma de finalización.

Casi todos los aspectos de un programa de preguntas y respuestas se compilan mediante instrucciones, por lo que ninguna página puede abarcar toda la información relacionada con ellos.
Sin embargo, su estructura léxica y su formato se describen en la página [estructura de archivo q #](xref:microsoft.quantum.guide.filestructure) , la asignación de enlace de símbolos y el ámbito en [las variables en q #](xref:microsoft.quantum.guide.variables), y los bucles de flujo de control, como `for` en el [flujo de control en Q #](xref:microsoft.quantum.guide.controlflow).


## <a name="whats-next"></a>Pasos adicionales
En el resto de esta guía, le mostraremos cómo usar Q # para construir programas Quantum complejos a través de los bloques de creación básicos de operaciones, funciones y tipos.

Para empezar, puede empezar a obtener información sobre los [tipos en preguntas y respuestas](xref:microsoft.quantum.guide.types).

Si está interesado en obtener más información sobre las bases y la motivación de preguntas y respuestas, consulte [¿por qué necesitamos q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
