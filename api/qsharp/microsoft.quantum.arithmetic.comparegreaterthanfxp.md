---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operación CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731636"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="1ec1c-102">Operación CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="1ec1c-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="1ec1c-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1ec1c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ec1c-105">Compara dos números de punto fijo almacenados en registros de Quantum y controla un volteo en el resultado.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1ec1c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ec1c-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="1ec1c-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1ec1c-108">Primer número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="1ec1c-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1ec1c-110">Segundo número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="1ec1c-111">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1ec1c-112">Resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-112">Result of the comparison.</span></span> <span data-ttu-id="1ec1c-113">Se volteará si `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="1ec1c-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ec1c-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1ec1c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ec1c-115">Remarks</span></span>

<span data-ttu-id="1ec1c-116">La implementación actual requiere que los dos números de punto fijo tengan la misma posición de punto y el mismo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>