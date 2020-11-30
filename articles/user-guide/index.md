---
title: Guía de usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231764"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="227de-103">Guía de usuario de Q#</span><span class="sxs-lookup"><span data-stu-id="227de-103">The Q# User Guide</span></span>

<span data-ttu-id="227de-104">Le damos la bienvenida al manual del usuario de Q#.</span><span class="sxs-lookup"><span data-stu-id="227de-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="227de-105">En los distintos temas de esta guía, se presentan algunos de los aspectos básicos para desarrollar programas cuánticos con Q#.</span><span class="sxs-lookup"><span data-stu-id="227de-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="227de-106">Consulte la [guía del lenguaje de Q#](xref:microsoft.quantum.qsharp.index) para obtener la especificación y documentación completa del lenguaje de programación cuántica Q#.</span><span class="sxs-lookup"><span data-stu-id="227de-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="227de-107">Contenido del manual del usuario</span><span class="sxs-lookup"><span data-stu-id="227de-107">User Guide Contents</span></span>

- <span data-ttu-id="227de-108">[Programas de Q#](xref:microsoft.quantum.guide.programs): introducción rápida a los programas cuánticos de Q#.</span><span class="sxs-lookup"><span data-stu-id="227de-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="227de-109">[Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs): describe cómo se ejecuta un programa de Q# y proporciona información general sobre las distintas formas en que se puede llamar al programa; por ejemplo, desde la línea de comandos, en cuadernos en Q# de Jupyter Notebook o desde un programa de host clásico escrito en Python o en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="227de-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="227de-110">[Prueba y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="227de-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="227de-111">Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="227de-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="227de-112">Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas que los programadores conocen, así como otras que son específicas de la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="227de-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="227de-113">Entre ellas, se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y las probabilidades del código, y las funciones `Dump`, cuyo resultado es el estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="227de-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="227de-114">Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones de la computación cuántica, por ejemplo, el [teorema de no clonación](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="227de-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="227de-115">Simuladores cuánticos y calculadoras de recursos</span><span class="sxs-lookup"><span data-stu-id="227de-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="227de-116">[Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): introducción a los diferentes simuladores disponibles, y cómo trabajan juntos los programas host y las máquinas de destino para ejecutar programas de Q#.</span><span class="sxs-lookup"><span data-stu-id="227de-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="227de-117">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): equipo de destino que simula el estado cuántico completo.</span><span class="sxs-lookup"><span data-stu-id="227de-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="227de-118">Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cúbits).</span><span class="sxs-lookup"><span data-stu-id="227de-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="227de-119">[Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="227de-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="227de-120">[Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan miles de cúbits.</span><span class="sxs-lookup"><span data-stu-id="227de-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="227de-121">Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="227de-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="227de-122">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador cuántico con un uso específico que se puede usar con millones de cúbits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (X, CNOT y X con controles múltiples).</span><span class="sxs-lookup"><span data-stu-id="227de-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="227de-123">Páginas de referencia rápida</span><span class="sxs-lookup"><span data-stu-id="227de-123">Quick Reference Pages</span></span>

- <span data-ttu-id="227de-124">[Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de los comandos magic de IQ# en cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="227de-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
