---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Operación EvaluateEvenPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731572"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="54390-102">Operación EvaluateEvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="54390-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="54390-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="54390-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="54390-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54390-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54390-105">Evalúa una polinómica uniforme en una representación de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="54390-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="54390-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="54390-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="54390-107">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="54390-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="54390-108">Los coeficientes del polinomio uniforme como una matriz doble, es decir, la matriz $ [a_0, a_1,..., a_k] $ para la $P polinómica par (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2K} $.</span><span class="sxs-lookup"><span data-stu-id="54390-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="54390-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="54390-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="54390-110">Número de punto fijo de entrada para el que se va a evaluar el polinomio.</span><span class="sxs-lookup"><span data-stu-id="54390-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="54390-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="54390-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="54390-112">Número de punto fijo de salida que contendrá $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="54390-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="54390-113">Debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="54390-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54390-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54390-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
