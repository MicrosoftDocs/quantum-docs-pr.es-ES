---
title: Manual del usuario de Q#
description: Información general sobre el propósito y el contenido del manual del usuario
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430618"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="9f2dd-103">Manual del usuario de Q#</span><span class="sxs-lookup"><span data-stu-id="9f2dd-103">The Q# User Guide</span></span>

<span data-ttu-id="9f2dd-104">Bienvenido al manual del usuario de Q#</span><span class="sxs-lookup"><span data-stu-id="9f2dd-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="9f2dd-105">En este manual se detallan los conceptos básicos del lenguaje Q#, así como toda la información necesaria para escribir programas de Quantum.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="9f2dd-106">Contenido del manual del usuario</span><span class="sxs-lookup"><span data-stu-id="9f2dd-106">User Guide Contents</span></span>

- <span data-ttu-id="9f2dd-107">[Conceptos básicos de Q#](xref:microsoft.quantum.guide.basics): información general que introduce la finalidad y funcionalidad del lenguaje de programación Q#.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="9f2dd-108">Lenguaje Q#</span><span class="sxs-lookup"><span data-stu-id="9f2dd-108">Q# Language</span></span>

- <span data-ttu-id="9f2dd-109">[Tipos en Q#](xref:microsoft.quantum.guide.types): compone el modelo de tipos de Q# y describe la sintaxis necesaria para especificar y trabajar con tipos.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="9f2dd-110">[Expresiones de tipo](xref:microsoft.quantum.guide.expressions): detalla cómo especificar, hacer referencia, combinar y operar en valores de cada tipo en Q#.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="9f2dd-111">Uso de Q#</span><span class="sxs-lookup"><span data-stu-id="9f2dd-111">Using Q#</span></span>

- <span data-ttu-id="9f2dd-112">[Estructura de archivos de Q#](xref:microsoft.quantum.guide.filestructure): describe la estructura y sintaxis de un archivo `*.qs` de Q#.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="9f2dd-113">[Operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions): se proporcionan detalles de los dos tipos a los que se puede llamar del lenguaje Q#: *operaciones*, que incluyen la realización de acciones en los registros de cubits, y *funciones*, que funcionan estrictamente con información clásica.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="9f2dd-114">Aquí se ve cómo definir y llamar a ambos tipo, los que incluye las versiones controlada y de adjoint de las operaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="9f2dd-115">[Variables](xref:microsoft.quantum.guide.variables): describe el rol de las variables en los programas de Q# y cómo usarlas de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="9f2dd-116">Por ejemplo, puede encontrar información sobre los ámbitos de enlace, así como la diferencia entre las variables inmutables y mutables, y cómo asignarlas o volver a asignarlas.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="9f2dd-117">[Uso de cubits](xref:microsoft.quantum.guide.qubits): describe las características de Q# que se usan para trabajar tanto con cubits individuales como con sistemas de cubits.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="9f2dd-118">En concreto, eso conlleva su asignación, la realización de operaciones en ellos y, en último término, su medición.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="9f2dd-119">[Flujo de control](xref:microsoft.quantum.guide.controlflow): detalla los patrones del flujo de control de programación disponibles en Q#, lo que incluye muchas técnicas estándar (ejecución condicional, bucles for, bucles while, etc.), así como el patrón "Repeat-Until-Success" específico de Quantum.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="9f2dd-120">[Pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging): detalla algunas técnicas que se usan para asegurarse de que el código hace lo que se supone que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="9f2dd-121">Dada la opacidad general de la información acerca de lo cuántico, la depuración de un programa cuántico puede requerir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="9f2dd-122">Afortunadamente, Q# admite muchas de las técnicas de depuración clásicas a las que están acostumbrados los programadores, así como otras que son específicas del mundo cuántico.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="9f2dd-123">Entre ellas se incluye la creación y ejecución de pruebas unitarias en Q#, la inserción de *aserciones* en los valores y probabilidades del código y las funciones `Dump` cuyo resultado es el estado de la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="9f2dd-124">Estas últimas se pueden usar junto con el simulador de estado completo para depurar ciertas partes de los cálculos, ya que se sortean algunas de las limitaciones del entorno cuántico (por ejemplo, el teorema de no clonación).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="9f2dd-125">Simuladores cuánticos y calculadoras de recursos</span><span class="sxs-lookup"><span data-stu-id="9f2dd-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="9f2dd-126">[Simuladores cuánticos y aplicaciones host](xref:microsoft.quantum.machines): información general de los diferentes simuladores disponibles, así como el modelo de ejecución general entre el programa host y las máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="9f2dd-127">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): el equipo de destino que simula el estado cuántico completo.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="9f2dd-128">Resulta útil para ejecutar o depurar programas de menor escala (menos de un par de docenas de cubits)</span><span class="sxs-lookup"><span data-stu-id="9f2dd-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="9f2dd-129">[Calculadora de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula los recursos necesarios para ejecutar una instancia dada de una operación de Q# en un equipo cuántico.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="9f2dd-130">[Simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro): ejecuta un programa cuántico sin simular realmente el estado de un equipo cuántico y, por consiguiente, puede ejecutar programas cuánticos que usan millares de cubits.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="9f2dd-131">Resulta útil para depurar código clásico en un programa cuántico, así como para calcular los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="9f2dd-132">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): un simulador cuántico con un uso especial que se puede usar con millones de cubits, pero solo para aquellos programas que tienen un conjunto restringido de operaciones cuánticas (a saber, X, CNOT y X con controles múltiples).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="9f2dd-133">Páginas de referencia rápida</span><span class="sxs-lookup"><span data-stu-id="9f2dd-133">Quick Reference Pages</span></span>

- <span data-ttu-id="9f2dd-134">[Comandos magic de IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referencia rápida de comandos magic de IQ # en cuadernos de Jupyter Notebook de Q#.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
