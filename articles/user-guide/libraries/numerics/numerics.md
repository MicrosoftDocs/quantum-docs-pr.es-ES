---
title: Usar la biblioteca de preguntas y respuestas de Microsoft
description: Obtenga información sobre los tipos y las operaciones disponibles en la biblioteca de valores numéricos de Microsoft Quantum.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276118"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="89434-103">Usar la biblioteca de valores numéricos</span><span class="sxs-lookup"><span data-stu-id="89434-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="89434-104">Información general</span><span class="sxs-lookup"><span data-stu-id="89434-104">Overview</span></span>

<span data-ttu-id="89434-105">La biblioteca de valores numéricos consta de tres componentes</span><span class="sxs-lookup"><span data-stu-id="89434-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="89434-106">**Aritmética de enteros básico** con agregadores y agregadores de enteros</span><span class="sxs-lookup"><span data-stu-id="89434-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="89434-107">**Funcionalidad de entero de alto nivel** que se basa en la funcionalidad básica; incluye multiplicación, división, inversión, etc.  para enteros con signo y sin signo.</span><span class="sxs-lookup"><span data-stu-id="89434-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="89434-108">**Funcionalidad aritmética de punto fijo** con inicialización de punto fijo, suma, multiplicación, mutua, evaluación polinómica y medición.</span><span class="sxs-lookup"><span data-stu-id="89434-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="89434-109">Se puede tener acceso a todos estos componentes mediante una sola `open` instrucción:</span><span class="sxs-lookup"><span data-stu-id="89434-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="89434-110">Tipos</span><span class="sxs-lookup"><span data-stu-id="89434-110">Types</span></span>

<span data-ttu-id="89434-111">La biblioteca de valores numéricos admite los siguientes tipos</span><span class="sxs-lookup"><span data-stu-id="89434-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="89434-112">**`LittleEndian`**: Una matriz de qubit `qArr : Qubit[]` que representa un entero en `qArr[0]` el que denota el bit menos significativo.</span><span class="sxs-lookup"><span data-stu-id="89434-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="89434-113">**`SignedLittleEndian`**: Igual que, `LittleEndian` salvo que representa un entero con signo almacenado en el complemento de dos.</span><span class="sxs-lookup"><span data-stu-id="89434-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="89434-114">**`FixedPoint`**: Representa un número real que consta de una matriz de qubit `qArr2 : Qubit[]` y una posición de punto binario `pos` , que cuenta el número de dígitos binarios a la izquierda del punto binario.</span><span class="sxs-lookup"><span data-stu-id="89434-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="89434-115">`qArr2`se almacena de la misma manera que `SignedLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="89434-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="89434-116">Operations</span><span class="sxs-lookup"><span data-stu-id="89434-116">Operations</span></span>

<span data-ttu-id="89434-117">Para cada uno de los tres tipos anteriores, hay disponible una variedad de operaciones:</span><span class="sxs-lookup"><span data-stu-id="89434-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="89434-118">Suma</span><span class="sxs-lookup"><span data-stu-id="89434-118">Addition</span></span>
    - <span data-ttu-id="89434-119">De comparación</span><span class="sxs-lookup"><span data-stu-id="89434-119">Comparison</span></span>
    - <span data-ttu-id="89434-120">Multiplicación</span><span class="sxs-lookup"><span data-stu-id="89434-120">Multiplication</span></span>
    - <span data-ttu-id="89434-121">Elevar</span><span class="sxs-lookup"><span data-stu-id="89434-121">Squaring</span></span>
    - <span data-ttu-id="89434-122">División (con resto)</span><span class="sxs-lookup"><span data-stu-id="89434-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="89434-123">Suma</span><span class="sxs-lookup"><span data-stu-id="89434-123">Addition</span></span>
    - <span data-ttu-id="89434-124">De comparación</span><span class="sxs-lookup"><span data-stu-id="89434-124">Comparison</span></span>
    - <span data-ttu-id="89434-125">Complemento del módulo de inversión 2</span><span class="sxs-lookup"><span data-stu-id="89434-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="89434-126">Multiplicación</span><span class="sxs-lookup"><span data-stu-id="89434-126">Multiplication</span></span>
    - <span data-ttu-id="89434-127">Elevar</span><span class="sxs-lookup"><span data-stu-id="89434-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="89434-128">Preparación/inicialización en un valor clásico</span><span class="sxs-lookup"><span data-stu-id="89434-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="89434-129">Suma (constante clásica u otro punto fijo Quantum)</span><span class="sxs-lookup"><span data-stu-id="89434-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="89434-130">De comparación</span><span class="sxs-lookup"><span data-stu-id="89434-130">Comparison</span></span>
    - <span data-ttu-id="89434-131">Multiplicación</span><span class="sxs-lookup"><span data-stu-id="89434-131">Multiplication</span></span>
    - <span data-ttu-id="89434-132">Elevar</span><span class="sxs-lookup"><span data-stu-id="89434-132">Squaring</span></span>
    - <span data-ttu-id="89434-133">Evaluación polinómica con especialización para las funciones pares e impares</span><span class="sxs-lookup"><span data-stu-id="89434-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="89434-134">Recíproco (1/x)</span><span class="sxs-lookup"><span data-stu-id="89434-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="89434-135">Medida (doble clásico)</span><span class="sxs-lookup"><span data-stu-id="89434-135">Measurement (classical Double)</span></span>

<span data-ttu-id="89434-136">Para obtener más información y documentación detallada sobre cada una de estas operaciones, vea los documentos de referencia de la biblioteca de Q # en [docs.Microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="89434-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="89434-137">Ejemplo: suma de enteros</span><span class="sxs-lookup"><span data-stu-id="89434-137">Sample: Integer addition</span></span>

<span data-ttu-id="89434-138">Como ejemplo básico, considere la operación $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ es decir, una operación que toma un entero n-qubit $x $ y un valor n-or (n + 1)-qubit registre $y $ como entrada, el último de los cuales se asigna a la suma $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="89434-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="89434-139">Tenga en cuenta que la suma es el módulo calculado $2 ^ n $ si $y $ está almacenado en un registro de $-bit $n.</span><span class="sxs-lookup"><span data-stu-id="89434-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="89434-140">Con el kit de desarrollo de Quantum, esta operación se puede aplicar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="89434-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="89434-141">Ejemplo: evaluar funciones fluidas</span><span class="sxs-lookup"><span data-stu-id="89434-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="89434-142">Para evaluar funciones fluidas como $ \sin (x) $ en un equipo Quantum, donde $x $ es un `FixedPoint` número Quantum, la biblioteca de valores numéricos del kit de desarrollo de Quantum proporciona las operaciones `EvaluatePolynomialFxP` y `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="89434-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="89434-143">La primera, `EvaluatePolynomialFxP` , permite evaluar un polinomio con el formato $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, donde $d $ denota el *grado*.</span><span class="sxs-lookup"><span data-stu-id="89434-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="89434-144">Para ello, lo único que se necesita son los coeficientes polinómicos `[a_0,..., a_d]` (de tipo `Double[]` ), la entrada `x : FixedPoint` y la salida `y : FixedPoint` (inicialmente cero):</span><span class="sxs-lookup"><span data-stu-id="89434-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="89434-145">El resultado, $P (x) = 1 + 2x $, se almacenará en `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="89434-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="89434-146">La segunda, `EvaluateEvenPolynomialFxP` y la tercera,, `EvaluateOddPolynomialFxP` son especializaciones para los casos de las funciones pares e impares, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="89434-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="89434-147">Es decir, para una función par/impar $f (x) $ y $ $ P_ {Even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ se aproxima bien mediante $P _ {Even} (x) $ o $P _ {impares} (x): = x\cdot P_ {Even} (x) $, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="89434-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="89434-148">En Q #, estos dos casos se pueden administrar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="89434-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="89434-149">que evalúa $P _ {Even} (x) = 1 + 2x ^ 2 $ y</span><span class="sxs-lookup"><span data-stu-id="89434-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="89434-150">que evalúa $P _ {impares} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="89434-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="89434-151">Más ejemplos</span><span class="sxs-lookup"><span data-stu-id="89434-151">More samples</span></span>

<span data-ttu-id="89434-152">Puede encontrar más ejemplos en el [repositorio principal de ejemplos](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="89434-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="89434-153">Para empezar, Clone el repositorio y abra la `Numerics` subcarpeta:</span><span class="sxs-lookup"><span data-stu-id="89434-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="89434-154">A continuación, `cd` en una de las carpetas de ejemplo y ejecute el ejemplo a través de</span><span class="sxs-lookup"><span data-stu-id="89434-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
