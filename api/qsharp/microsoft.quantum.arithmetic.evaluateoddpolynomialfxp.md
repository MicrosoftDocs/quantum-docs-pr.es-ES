---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operación EvaluateOddPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846659"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="a6f5e-102">Operación EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="a6f5e-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="a6f5e-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a6f5e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a6f5e-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a6f5e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a6f5e-105">Evalúa una polinómica impar en una representación de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a6f5e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a6f5e-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a6f5e-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a6f5e-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a6f5e-108">Los coeficientes del polinomio impar como una matriz doble, es decir, la matriz $ [a_0, a_1,..., a_k] $ para la $P extraña (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="a6f5e-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a6f5e-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a6f5e-110">Número de punto fijo de entrada para el que se va a evaluar el polinomio.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a6f5e-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a6f5e-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a6f5e-112">Número de punto fijo de salida que contendrá P (x).</span><span class="sxs-lookup"><span data-stu-id="a6f5e-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="a6f5e-113">Debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6f5e-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6f5e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

