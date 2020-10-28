---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operación EvaluatePolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731557"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="44d46-102">Operación EvaluatePolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="44d46-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="44d46-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="44d46-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="44d46-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44d46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44d46-105">Evalúa una polinómica en una representación de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="44d46-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="44d46-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="44d46-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="44d46-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="44d46-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="44d46-108">Los coeficientes del polinomio como una matriz doble, es decir, la matriz $ [a_0, a_1,..., a_d] $ para la $P polinómica (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="44d46-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="44d46-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="44d46-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="44d46-110">Número de punto fijo de entrada para el que se va a evaluar el polinomio.</span><span class="sxs-lookup"><span data-stu-id="44d46-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="44d46-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="44d46-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="44d46-112">Número de punto fijo de salida que contendrá $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="44d46-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="44d46-113">Debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="44d46-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44d46-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44d46-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

