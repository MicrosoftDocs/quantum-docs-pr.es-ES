---
title: 'P # Introdution'
description: 'Introducción rápida a los programas Quantum en Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234322"
---
# <a name="q-quantum-programming-language"></a>Lenguaje de programación de Q # Quantum

Todo lo que necesita saber sobre el lenguaje de programación de Q # se detalla en la [Guía del lenguaje de preguntas y respuestas](xref:microsoft.quantum.qsharp.index). Al igual que cualquier otra cosa, nuestro [proceso de diseño del lenguaje](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) es código abierto y agradecemos sus contribuciones.
Para obtener más información sobre las bases y la motivación de preguntas y respuestas, consulte [¿por qué necesitamos q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
P # se incluye como parte del kit de desarrollo de Quantum (QDK) para obtener una introducción rápida, consulte [¿Qué es QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>¿Qué es un programa Quantum?

Un programa Quantum se puede considerar como un conjunto determinado de subrutinas clásicas que, cuando se llama, realizan un cálculo mediante la interacción con un sistema Quantum; un programa escrito en Q # no modela directamente el estado de Quantum, sino que describe el modo en que un equipo de control clásico interactúa con qubits.
Esto nos permite ser totalmente independientes sobre lo que un estado de Quantum *tiene* incluso en cada máquina de destino, que podría tener interpretaciones diferentes en función del equipo. 

Una consecuencia importante de esto es que Q # no tiene la capacidad de Introspect en el estado de una qubit u otras propiedades de la mecánica de Quantum directamente, lo que garantiza que se puede ejecutar físicamente un programa de preguntas y respuestas en un equipo Quantum.
En su lugar, un programa puede llamar a operaciones como [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) para extraer información clásica de un qubit.

Una vez asignada, se puede pasar un qubit a las operaciones y funciones, también denominadas *llamadas*. En cierto sentido, esto es todo lo que un programa de Q # puede hacer con un qubit; Todas las acciones directas en el estado de un qubit se definen mediante llamadas a *funciones intrínsecas* como [`X`](xref:Microsoft.Quantum.Intrinsic.X) y [`H`](xref:Microsoft.Quantum.Intrinsic.H) , es decir, Invocables cuyas implementaciones no se definen en Q #, sino que se definen en el equipo de destino. Lo que realmente *hacen* estas operaciones solo se convierte en concreto por el equipo de destino que se usa para ejecutar el programa de preguntas y respuestas determinado.

Por ejemplo, si se ejecuta el programa en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), el simulador realiza las operaciones matemáticas correspondientes en el sistema Quantum simulado.
Pero en el futuro, cuando el equipo de destino es un equipo Quantum real, llamar a tales operaciones en Q # dirigirá el equipo Quantum para que realice las operaciones *reales* correspondientes en el sistema Quantum *real* (por ejemplo, con precisión de impulsos láser con tiempo).

Un programa de preguntas # vuelve a combinar estas operaciones, tal y como se define en un equipo de destino para crear nuevas operaciones de nivel superior para expresar el cálculo de Quantum.
De esta manera, Q # hace que sea fácil expresar el Quantum subyacente de la lógica y los algoritmos de Quantum híbridos, mientras que también son generales con respecto a la estructura de un equipo de destino o un simulador.

Un ejemplo sencillo es el siguiente programa, que asigna un qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Nuestro [Quantum katas](https://github.com/microsoft/QuantumKatas#introduction) ofrece una buena introducción a los conceptos de la [informática Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , como las operaciones de Quantum comunes y cómo manipular qubits. También se pueden encontrar más ejemplos en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude).



