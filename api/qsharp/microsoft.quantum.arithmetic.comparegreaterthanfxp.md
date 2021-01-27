---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operación CompareGreaterThanFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843320"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="4c501-102">Operación CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="4c501-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="4c501-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4c501-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4c501-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4c501-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4c501-105">Compara dos números de punto fijo almacenados en registros de Quantum y controla un volteo en el resultado.</span><span class="sxs-lookup"><span data-stu-id="4c501-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4c501-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4c501-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="4c501-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4c501-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4c501-108">Primer número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="4c501-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="4c501-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4c501-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4c501-110">Segundo número de punto fijo que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="4c501-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="4c501-111">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4c501-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4c501-112">Resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="4c501-112">Result of the comparison.</span></span> <span data-ttu-id="4c501-113">Se volteará si `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="4c501-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c501-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c501-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4c501-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c501-115">Remarks</span></span>

<span data-ttu-id="4c501-116">La implementación actual requiere que los dos números de punto fijo tengan la misma posición de punto y el mismo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="4c501-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>