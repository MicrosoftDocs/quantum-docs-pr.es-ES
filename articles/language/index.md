---
title: El lenguaje de programación Q# | Microsoft Docs
description: El lenguaje de programación Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035272"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="f3092-103">El lenguaje de programación Q#</span><span class="sxs-lookup"><span data-stu-id="f3092-103">The Q# Programming Language</span></span>

# <a name="introduction"></a><span data-ttu-id="f3092-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="f3092-104">Introduction</span></span>

<span data-ttu-id="f3092-105">Un modelo natural de computación cuántica consiste en tratar el equipo cuántico como un coprocesador, similar al que se usa para GPU, FPGA y otros procesadores complementarios.</span><span class="sxs-lookup"><span data-stu-id="f3092-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="f3092-106">La lógica de control principal ejecuta código clásico en un equipo "host" clásico.</span><span class="sxs-lookup"><span data-stu-id="f3092-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="f3092-107">Cuando es adecuado y necesario, el programa host puede invocar una subrutina que se ejecuta en el procesador complementario.</span><span class="sxs-lookup"><span data-stu-id="f3092-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="f3092-108">Cuando se completa la subrutina, el programa host obtiene acceso a los resultados de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="f3092-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="f3092-109">Q# (Q-Sharp) es un lenguaje de programación específico del dominio que se usa para expresar algoritmos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="f3092-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="f3092-110">Se usa para escribir subrutinas que se ejecutan en un procesador cuántico complementario, bajo el control de un equipo y un programa host clásico.</span><span class="sxs-lookup"><span data-stu-id="f3092-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="f3092-111">Hasta que los procesadores cuánticos estén disponibles de forma general, las subrutinas de Q# se ejecutan en un simulador.</span><span class="sxs-lookup"><span data-stu-id="f3092-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="f3092-112">Q# proporciona un pequeño conjunto de tipos primitivos y dos maneras (matrices y tuplas) de crear nuevos tipos estructurados.</span><span class="sxs-lookup"><span data-stu-id="f3092-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="f3092-113">Admite un modelo de procedimientos básico para escribir programas, con bucles e instrucciones if/then.</span><span class="sxs-lookup"><span data-stu-id="f3092-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="f3092-114">Las construcciones de nivel superior en Q# son tipos, operaciones y funciones definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f3092-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="f3092-115">En las secciones siguientes se detallan:</span><span class="sxs-lookup"><span data-stu-id="f3092-115">The following sections detail:</span></span>
- [<span data-ttu-id="f3092-116">Modelo de tipos</span><span class="sxs-lookup"><span data-stu-id="f3092-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="f3092-117">Expresiones</span><span class="sxs-lookup"><span data-stu-id="f3092-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="f3092-118">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="f3092-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="f3092-119">Estructura de archivos</span><span class="sxs-lookup"><span data-stu-id="f3092-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a><span data-ttu-id="f3092-120">Convenciones</span><span class="sxs-lookup"><span data-stu-id="f3092-120">Conventions</span></span>

<span data-ttu-id="f3092-121">Estamos trabajando para asegurarnos de que los signos de puntuación comunes se utilicen de forma coherente en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="f3092-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="f3092-122">Esperamos que esto facilite el aprendizaje y la lectura de Q#, porque estos signos significarán siempre lo mismo, y el mismo concepto se representa siempre de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="f3092-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="f3092-123">Concretamente:</span><span class="sxs-lookup"><span data-stu-id="f3092-123">Specifically:</span></span>

- <span data-ttu-id="f3092-124">El punto y coma, `;`, se usa para finalizar una instrucción o una directiva de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="f3092-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="f3092-125">No se usa para ningún otro fin.</span><span class="sxs-lookup"><span data-stu-id="f3092-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="f3092-126">La coma, `,`, se usa para separar los elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="f3092-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="f3092-127">Se utiliza para literales de tupla, literales de matriz, listas de argumentos, definiciones de tupla y listas de tipos.</span><span class="sxs-lookup"><span data-stu-id="f3092-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="f3092-128">**En un cambio con respecto a las versiones anteriores, ya no se admite `;` como separador de literales de matriz.**</span><span class="sxs-lookup"><span data-stu-id="f3092-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="f3092-129">Los dos puntos, `:`, se usan para introducir una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="f3092-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="f3092-130">Se utiliza principalmente en signaturas de llamada.</span><span class="sxs-lookup"><span data-stu-id="f3092-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="f3092-131">Como los dos puntos introducen siempre una signatura de tipo, el operador condicional ternario introducido en 0.3 usa una barra vertical, `|`, para separar los valores true y false; por lo tanto, Q# usa `cond ? tval | fval` en lugar de los dos puntos como separador como en C.</span><span class="sxs-lookup"><span data-stu-id="f3092-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
