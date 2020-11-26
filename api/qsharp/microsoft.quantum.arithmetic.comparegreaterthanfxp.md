---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operación CompareGreaterThanFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223534"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="6b0e2-102">Operación CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="6b0e2-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="6b0e2-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6b0e2-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="6b0e2-105">Compara dos números de punto fijo almacenados en registros de Quantum y controla un volteo en el resultado.</span><span class="sxs-lookup"><span data-stu-id="6b0e2-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6b0e2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b0e2-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="6b0e2-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6b0e2-108">Primer número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="6b0e2-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="6b0e2-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6b0e2-110">Segundo número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="6b0e2-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="6b0e2-111">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6b0e2-112">Resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="6b0e2-112">Result of the comparison.</span></span> <span data-ttu-id="6b0e2-113">Se volteará si `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="6b0e2-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b0e2-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b0e2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b0e2-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b0e2-115">Remarks</span></span>

<span data-ttu-id="6b0e2-116">La implementación actual requiere que los dos números de punto fijo tengan la misma posición de punto y el mismo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="6b0e2-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>