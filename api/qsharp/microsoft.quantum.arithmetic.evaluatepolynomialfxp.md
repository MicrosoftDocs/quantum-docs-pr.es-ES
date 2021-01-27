---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operación EvaluatePolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843226"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="41d44-102">Operación EvaluatePolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="41d44-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="41d44-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="41d44-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="41d44-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="41d44-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="41d44-105">Evalúa una polinómica en una representación de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="41d44-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41d44-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="41d44-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="41d44-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="41d44-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="41d44-108">Los coeficientes del polinomio como una matriz doble, es decir, la matriz $ [a_0, a_1,..., a_d] $ para la $P polinómica (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="41d44-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="41d44-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="41d44-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="41d44-110">Número de punto fijo de entrada para el que se va a evaluar el polinomio.</span><span class="sxs-lookup"><span data-stu-id="41d44-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="41d44-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="41d44-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="41d44-112">Número de punto fijo de salida que contendrá $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="41d44-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="41d44-113">Debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="41d44-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41d44-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41d44-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

