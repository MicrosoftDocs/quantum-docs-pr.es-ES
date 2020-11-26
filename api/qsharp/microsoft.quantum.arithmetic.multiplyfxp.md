---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operación MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222616"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="901c5-102">Operación MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="901c5-102">MultiplyFxP operation</span></span>

<span data-ttu-id="901c5-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="901c5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="901c5-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="901c5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="901c5-105">Multiplica dos números de punto fijo en registros de Quantum.</span><span class="sxs-lookup"><span data-stu-id="901c5-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="901c5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="901c5-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="901c5-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="901c5-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="901c5-108">Primer número de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="901c5-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="901c5-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="901c5-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="901c5-110">Segundo número de punto fijo.</span><span class="sxs-lookup"><span data-stu-id="901c5-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="901c5-111">resultado: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="901c5-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="901c5-112">El número de punto fijo resultante debe tener el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="901c5-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="901c5-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="901c5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="901c5-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="901c5-114">Remarks</span></span>

<span data-ttu-id="901c5-115">La implementación actual requiere que los tres números de punto fijo tengan la misma posición de punto y el mismo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="901c5-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>