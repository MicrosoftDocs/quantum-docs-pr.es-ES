---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operación EvaluateOddPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731565"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="634e6-102">Operación EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="634e6-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="634e6-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="634e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="634e6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="634e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="634e6-105">Evalúa una polinómica impar en una representación de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="634e6-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="634e6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="634e6-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="634e6-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="634e6-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="634e6-108">Los coeficientes del polinomio impar como una matriz doble, es decir, la matriz $ [a_0, a_1,..., a_k] $ para la $P extraña (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="634e6-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="634e6-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="634e6-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="634e6-110">Número de punto fijo de entrada para el que se va a evaluar el polinomio.</span><span class="sxs-lookup"><span data-stu-id="634e6-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="634e6-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="634e6-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="634e6-112">Número de punto fijo de salida que contendrá P (x).</span><span class="sxs-lookup"><span data-stu-id="634e6-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="634e6-113">Debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="634e6-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="634e6-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="634e6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

