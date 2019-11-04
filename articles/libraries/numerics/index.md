---
title: Introducción a la biblioteca de valores numéricos cuánticos | Microsoft Docs
description: Introducción a la biblioteca de valores numéricos cuánticos
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442440"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="02070-103">Introducción a la biblioteca de valores numéricos cuánticos</span><span class="sxs-lookup"><span data-stu-id="02070-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="02070-104">Muchos algoritmos cuánticos se basan en [cajas negras](xref:microsoft.quantum.concepts.oracles) que evalúan funciones matemáticas en una superposición de entradas.</span><span class="sxs-lookup"><span data-stu-id="02070-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="02070-105">El componente principal del algoritmo de Shor, por ejemplo, evalúa $f(x) = a^x\operatorname{mod} N$ para un $a$ fijo, el número que se va a factorizar $N$, y $x$, el entero $2n$-qubit en una superposición uniforme de las $2n$-bit cadenas.</span><span class="sxs-lookup"><span data-stu-id="02070-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="02070-106">Para ejecutar el algoritmo de Shor en un equipo cuántico real, esta función debe escribirse en función de las operaciones nativas del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="02070-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="02070-107">Usando la representación binaria de $x$, siendo $x _i$ el bit número $i$ contando desde el bit menos significativo, $f(x)$ se puede escribir como $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="02070-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="02070-108">A su vez, esto se puede escribir como un producto (mod N) de términos $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="02070-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="02070-109">Por lo tanto, la función $f(x)$ se puede implementar utilizando una secuencia de $2n$ multiplicaciones (modulares) por $a^{2^i}$, con la condición de que $x_i$ no sea cero.</span><span class="sxs-lookup"><span data-stu-id="02070-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="02070-110">Las constantes $a^{2^i}$ se pueden calcular previamente y reducir al módulo N antes de ejecutar el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="02070-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="02070-111">Esta secuencia de multiplicaciones modulares controladas se puede simplificar aún más: Cada multiplicación se puede realizar mediante una secuencia de adiciones modulares controladas por $n$; y cada adición modular se puede crear a partir de una suma normal y un comparador.</span><span class="sxs-lookup"><span data-stu-id="02070-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="02070-112">Como se necesitan muchos pasos para llegar a una implementación real, resultaría muy útil tener dicha funcionalidad disponible desde el principio.</span><span class="sxs-lookup"><span data-stu-id="02070-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="02070-113">Por este motivo, Quantum Development Kit proporciona compatibilidad con una amplia gama de funciones numéricas.</span><span class="sxs-lookup"><span data-stu-id="02070-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="02070-114">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="02070-114">Functionality</span></span>

<span data-ttu-id="02070-115">Además de la aritmética de enteros mencionada, la biblioteca de valores numéricos proporciona:</span><span class="sxs-lookup"><span data-stu-id="02070-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="02070-116">Funcionalidad de enteros con o sin signo (multiplicación, cuadrado, división con resto, inversión, etc.) con uno o dos números enteros cuánticos como entrada.</span><span class="sxs-lookup"><span data-stu-id="02070-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="02070-117">Funcionalidad de punto fijo (suma/resta, multiplicación, cuadrado, 1/x, evaluación polinómica) con uno o dos números de punto fijo cuánticos como entrada.</span><span class="sxs-lookup"><span data-stu-id="02070-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="02070-118">Introducción</span><span class="sxs-lookup"><span data-stu-id="02070-118">Getting started</span></span>

<span data-ttu-id="02070-119">Para empezar a trabajar con la biblioteca de valores numéricos, consulte la [guía de instalación](xref:microsoft.quantum.numerics.installation) y más información sobre [cómo usar la biblioteca de valores numéricos](xref:microsoft.quantum.numerics.usage).</span><span class="sxs-lookup"><span data-stu-id="02070-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
