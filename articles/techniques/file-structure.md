---
title: 'Información general del programa de preguntas y respuestas: técnicas de Q # | Microsoft Docs'
description: 'Información general del programa de preguntas y respuestas: técnicas de Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820834"
---
# <a name="q-program-overview"></a>Introducción a un programa en Q#

Q # es un lenguaje de programación escalable, de paradigma múltiple y específico del dominio para la informática Quantum. Q # es un lenguaje de programación Quantum en el que se puede usar para describir cómo se ejecutan las instrucciones en máquinas Quantum. Los equipos a los que se puede dirigir desde simuladores hasta hardware Quantum real. Q # es escalable: se puede usar para escribir programas de demostración sencillos, como teletranspórtate, que se ejecutan en unos pocos qubits, pero también admite la escritura de programas grandes y sofisticados, como simulaciones de moléculas complejas que requerirán máquinas grandes con millones de qubits. Aunque las máquinas físicas de gran tamaño siguen en el futuro, Q # permite a un programador programar algoritmos Quantum complejos ahora. Lo que es más, Q # admite varias tareas, como la depuración, la generación de perfiles, la estimación de recursos y ciertas simulaciones de propósito especial de una manera escalable. 

Desde una perspectiva técnica, un programa Quantum se puede considerar como un conjunto determinado de funciones clásicas que, cuando se llama, generan circuitos Quantum como efectos secundarios. Una consecuencia importante de esa vista es que un programa escrito en Q # no modela directamente qubits, sino que describe cómo interactúa un equipo de control clásico con esos qubits.
Por diseño, Q # no define los Estados Quantum u otras propiedades de la mecánica de Quantum directamente, sino que, en su lugar, indirectamente a través de la acción de las diversas subrutinas definidas en el lenguaje.
Por ejemplo, tenga en cuenta el estado $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ descrito en la guía de [conceptos de procesamiento de Quantum](xref:microsoft.quantum.concepts.intro) .
Para preparar este estado en Q #, usamos los hechos que los qubits se inicializan en $ \ket{0}$ State y que $ \ket{+} = H\ket{0}$, donde $H $ es la transformación Hadamard:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # transformaciones de Estados Quantum

Lo importante es que, al escribir el programa anterior, no nos referimos explícitamente al estado en Q #, sino que describimos cómo el programa *transformó* el estado.
Por lo tanto, de forma similar a cómo un programa del sombreador de gráficos acumula una descripción de las transformaciones en cada vértice, un programa Quantum en Q # acumula las transformaciones a los Estados de Quantum.
Esto nos permite ser totalmente independientes sobre lo que un estado de Quantum *tiene* incluso en cada máquina de destino, que podría tener interpretaciones diferentes en función del equipo. 

Desde la perspectiva de un programa de preguntas y respuestas, un qubit es una referencia totalmente opaca a la estructura interna de un equipo de destino.
Un programa de preguntas # no tiene capacidad para Introspect en el estado de un qubit, su representación en un equipo de destino o incluso si es el mismo qubit que cualquier otro qubit disponible para el programa.
En su lugar, un programa puede llamar a operaciones como `Measure` para obtener información de un qubit y llamar a operaciones como `X` y `H` para actuar en el estado de un qubit.
Estas operaciones no tienen ninguna definición intrínseca en el lenguaje y solo son específicas de la máquina de destino que se usa para ejecutar un programa de preguntas # determinado.
Un programa de preguntas # vuelve a combinar estas operaciones, tal y como se define en un equipo de destino para crear nuevas operaciones de nivel superior para expresar el cálculo de Quantum.
De esta manera, Q # facilita la rápida expresión de los algoritmos Quantum subyacentes de Quantum y Quantum-clásico de la lógica, a la vez que también es general con respecto a la estructura de un equipo de destino o simulador.

## <a name="q-operations-and-functions"></a>Operaciones y funciones de Q #

Concretamente, un programa de preguntas y respuestas se compone de una o más *operaciones*, una o varias *funciones*y tipos definidos por el usuario. Las operaciones se usan para describir las transformaciones del estado de una máquina Quantum y son el bloque de creación más básico de los programas de Q #. Cada operación definida en Q # puede llamar a cualquier número de operaciones, incluidas las operaciones *intrínsecas* integradas implementadas por un equipo de destino.
Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.

A diferencia de las operaciones, las funciones se usan para describir el comportamiento puramente clásico y no tienen ningún efecto además de calcular los valores de salida clásico. Q # es un lenguaje fuertemente tipado e incluye un conjunto de tipos primitivos integrados, así como compatibilidad con tipos definidos por el usuario. 

En el resto de esta guía, veremos cómo usar diferentes conceptos y construcciones del lenguaje para ayudarnos a definir programas Quantum complejos a través de los bloques de creación básicos de operaciones, funciones y tipos. 

## <a name="structure-of-q-source-files"></a>Estructura de los archivos de código fuente de Q #

Como mínimo, un archivo de código fuente de Q # consta de una *declaración de espacio de nombres*, que especifica un espacio de nombres de .net que contendrá las definiciones en el archivo de código fuente.
Las definiciones de otros archivos de código fuente y bibliotecas de preguntas y respuestas se pueden incluir con la instrucción `open`.
Por ejemplo, la mayoría de las operaciones que definen las puertas fundamentales se definen en el espacio de nombres <xref:microsoft.quantum.intrinsic>.
Para que esté disponible en nuestro código, simplemente `open` ese espacio de nombres en la parte superior de cada archivo:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

Dentro de un espacio de nombres, cada archivo de código fuente de Q # puede definir cualquier combinación de *operaciones*, *funciones*y *tipos definidos por el usuario*.
En el resto de esta sección, describiremos cada uno de ellos y proporcionaremos ejemplos de cómo se pueden usar en la práctica para crear programas Quantum útiles.
