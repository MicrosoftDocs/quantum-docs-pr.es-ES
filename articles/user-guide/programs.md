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
# <a name="q-quantum-programming-language"></a><span data-ttu-id="3ec51-103">Lenguaje de programación de Q # Quantum</span><span class="sxs-lookup"><span data-stu-id="3ec51-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="3ec51-104">Todo lo que necesita saber sobre el lenguaje de programación de Q # se detalla en la [Guía del lenguaje de preguntas y respuestas](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="3ec51-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="3ec51-105">Al igual que cualquier otra cosa, nuestro [proceso de diseño del lenguaje](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) es código abierto y agradecemos sus contribuciones.</span><span class="sxs-lookup"><span data-stu-id="3ec51-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="3ec51-106">Para obtener más información sobre las bases y la motivación de preguntas y respuestas, consulte [¿por qué necesitamos q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="3ec51-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="3ec51-107">P # se incluye como parte del kit de desarrollo de Quantum (QDK) para obtener una introducción rápida, consulte [¿Qué es QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="3ec51-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="3ec51-108">¿Qué es un programa Quantum?</span><span class="sxs-lookup"><span data-stu-id="3ec51-108">What is a quantum program?</span></span>

<span data-ttu-id="3ec51-109">Un programa Quantum se puede considerar como un conjunto determinado de subrutinas clásicas que, cuando se llama, realizan un cálculo mediante la interacción con un sistema Quantum; un programa escrito en Q # no modela directamente el estado de Quantum, sino que describe el modo en que un equipo de control clásico interactúa con qubits.</span><span class="sxs-lookup"><span data-stu-id="3ec51-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="3ec51-110">Esto nos permite ser totalmente independientes sobre lo que un estado de Quantum *tiene* incluso en cada máquina de destino, que podría tener interpretaciones diferentes en función del equipo.</span><span class="sxs-lookup"><span data-stu-id="3ec51-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="3ec51-111">Una consecuencia importante de esto es que Q # no tiene la capacidad de Introspect en el estado de una qubit u otras propiedades de la mecánica de Quantum directamente, lo que garantiza que se puede ejecutar físicamente un programa de preguntas y respuestas en un equipo Quantum.</span><span class="sxs-lookup"><span data-stu-id="3ec51-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="3ec51-112">En su lugar, un programa puede llamar a operaciones como [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) para extraer información clásica de un qubit.</span><span class="sxs-lookup"><span data-stu-id="3ec51-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="3ec51-113">Una vez asignada, se puede pasar un qubit a las operaciones y funciones, también denominadas *llamadas*.</span><span class="sxs-lookup"><span data-stu-id="3ec51-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="3ec51-114">En cierto sentido, esto es todo lo que un programa de Q # puede hacer con un qubit; Todas las acciones directas en el estado de un qubit se definen mediante llamadas a *funciones intrínsecas* como [`X`](xref:Microsoft.Quantum.Intrinsic.X) y [`H`](xref:Microsoft.Quantum.Intrinsic.H) , es decir, Invocables cuyas implementaciones no se definen en Q #, sino que se definen en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="3ec51-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="3ec51-115">Lo que realmente *hacen* estas operaciones solo se convierte en concreto por el equipo de destino que se usa para ejecutar el programa de preguntas y respuestas determinado.</span><span class="sxs-lookup"><span data-stu-id="3ec51-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="3ec51-116">Por ejemplo, si se ejecuta el programa en el [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), el simulador realiza las operaciones matemáticas correspondientes en el sistema Quantum simulado.</span><span class="sxs-lookup"><span data-stu-id="3ec51-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="3ec51-117">Pero en el futuro, cuando el equipo de destino es un equipo Quantum real, llamar a tales operaciones en Q # dirigirá el equipo Quantum para que realice las operaciones *reales* correspondientes en el sistema Quantum *real* (por ejemplo, con precisión de impulsos láser con tiempo).</span><span class="sxs-lookup"><span data-stu-id="3ec51-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="3ec51-118">Un programa de preguntas # vuelve a combinar estas operaciones, tal y como se define en un equipo de destino para crear nuevas operaciones de nivel superior para expresar el cálculo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="3ec51-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="3ec51-119">De esta manera, Q # hace que sea fácil expresar el Quantum subyacente de la lógica y los algoritmos de Quantum híbridos, mientras que también son generales con respecto a la estructura de un equipo de destino o un simulador.</span><span class="sxs-lookup"><span data-stu-id="3ec51-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="3ec51-120">Un ejemplo sencillo es el siguiente programa, que asigna un qubit en el estado $ \ket {0} $, después le aplica una operación Hadamard `H` y mide el resultado de la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="3ec51-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="3ec51-121">Nuestro [Quantum katas](https://github.com/microsoft/QuantumKatas#introduction) ofrece una buena introducción a los conceptos de la [informática Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , como las operaciones de Quantum comunes y cómo manipular qubits.</span><span class="sxs-lookup"><span data-stu-id="3ec51-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="3ec51-122">También se pueden encontrar más ejemplos en [operaciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="3ec51-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



