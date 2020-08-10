---
title: Guía de usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869637"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="cb4cf-103">Guía de usuario de Q#</span><span class="sxs-lookup"><span data-stu-id="cb4cf-103">The Q# User Guide</span></span>

<span data-ttu-id="cb4cf-104">Le damos la bienvenida al manual del usuario de Q#.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="cb4cf-105">En los temas de esta guía se detallan los conceptos básicos del lenguaje Q#, así como toda la información necesaria para escribir programas cuánticos.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="cb4cf-106">Contenido del manual del usuario</span><span class="sxs-lookup"><span data-stu-id="cb4cf-106">User Guide Contents</span></span>

- <span data-ttu-id="cb4cf-107">[Conceptos básicos de Q#](xref:microsoft.quantum.guide.basics): introducción a la finalidad y funcionalidad del lenguaje de programación Q#.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="cb4cf-108">[Maneras de ejecutar un programa de Q#](xref:microsoft.quantum.guide.host-programs): describe cómo se ejecuta un programa de Q# y proporciona información general sobre las distintas formas en que se puede llamar al programa, por ejemplo, desde la línea de comandos, en cuadernos en Q# de Jupyter Notebook o desde un programa de host clásico escrito en Python o en un lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="cb4cf-109">Lenguaje Q#</span><span class="sxs-lookup"><span data-stu-id="cb4cf-109">Q# Language</span></span>

- <span data-ttu-id="cb4cf-110">[Tipos en Q#](xref:microsoft.quantum.guide.types): describe el modelo de tipos de Q# y la sintaxis necesaria para especificar tipos y trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="cb4cf-111">[Expresiones de tipo](xref:microsoft.quantum.guide.expressions): detalla cómo especificar los valores de cada tipo en Q# y cómo hacer referencia a ellos, combinarlos y operar con ellos.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="cb4cf-112">Usar Q#</span><span class="sxs-lookup"><span data-stu-id="cb4cf-112">Using Q#</span></span>

- <span data-ttu-id="cb4cf-113">[Estructura de archivos de Q#](xref:microsoft.quantum.guide.filestructure): describe la estructura y sintaxis de un archivo de `*.qs` Q#.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="cb4cf-114">[Operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions): detalla los dos tipos invocables del lenguaje Q#: *operaciones*, incluidas acciones en los registros de cúbits, y *funciones*, que funcionan estrictamente con información clásica.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="cb4cf-115">Aquí se ve cómo definir y llamar a ambos tipo, los que incluye las versiones controlada y de adjoint de las operaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="cb4cf-116">[Variables](xref:microsoft.quantum.guide.variables): describe el papel que juegan las variables en los programas de Q# y cómo usarlas de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="cb4cf-117">Por ejemplo, puede encontrar información sobre los ámbitos de enlace, así como la diferencia entre las variables inmutables y mutables, y cómo asignarlas o reasignarlas.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="cb4cf-118">[Trabajo con cúbits](xref:microsoft.quantum.guide.qubits): describe las características de Q# que se usan para trabajar con cúbits individuales y sistemas de cúbits, en concreto, asignarlos, ejecutar operaciones en ellos y medirlos.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="cb4cf-119">[Flujo de control](xref:microsoft.quantum.guide.controlflow): detalla los patrones del flujo de control de programación disponibles en Q#, incluidas numerosas técnicas estándar (ejecución condicional, bucles for, bucles while), así como el patrón "repetir hasta obtener un resultado correcto", específico de la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="cb4cf-120">[Prueba y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="cb4cf-121">Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="cb4cf-122">Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas que los programadores conocen, así como otras que son específicas de la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="cb4cf-123">Entre ellas, se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y las probabilidades del código, y las funciones `Dump`, cuyo resultado es el estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="cb4cf-124">Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones de la computación cuántica, por ejemplo, el [teorema de no clonación](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="cb4cf-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="cb4cf-125">Simuladores cuánticos y calculadoras de recursos</span><span class="sxs-lookup"><span data-stu-id="cb4cf-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="cb4cf-126">[Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): introducción a los diferentes simuladores disponibles, así como el modelo de ejecución general entre los programas host y las máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="cb4cf-127">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): equipo de destino que simula el estado cuántico completo.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="cb4cf-128">Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cúbits).</span><span class="sxs-lookup"><span data-stu-id="cb4cf-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="cb4cf-129">[Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="cb4cf-130">[Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan millares de cúbits.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="cb4cf-131">Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="cb4cf-132">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador cuántico con un uso específico que se puede usar con millones de cúbits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (X, CNOT y X con controles múltiples).</span><span class="sxs-lookup"><span data-stu-id="cb4cf-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="cb4cf-133">Páginas de referencia rápida</span><span class="sxs-lookup"><span data-stu-id="cb4cf-133">Quick Reference Pages</span></span>

- <span data-ttu-id="cb4cf-134">[Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de los comandos magic de IQ# en cuadernos en Q# de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="cb4cf-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
