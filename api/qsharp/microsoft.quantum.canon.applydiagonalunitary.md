---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: Operación ApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729628"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="420cf-102">Operación ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="420cf-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="420cf-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="420cf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="420cf-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="420cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="420cf-105">Aplica una matriz de fases complejas a Estados de base numéricos de un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="420cf-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="420cf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="420cf-106">Description</span></span>

<span data-ttu-id="420cf-107">Esta operación implementa una unitario diagonal que aplica una fase compleja $e ^ {i \ theta_j} $ en el $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="420cf-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="420cf-108">En concreto, esta operación se puede representar mediante la unitario</span><span class="sxs-lookup"><span data-stu-id="420cf-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="420cf-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="420cf-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="420cf-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="420cf-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="420cf-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="420cf-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="420cf-112">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="420cf-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="420cf-113">Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="420cf-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="420cf-114">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="420cf-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="420cf-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="420cf-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="420cf-116">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="420cf-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="420cf-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="420cf-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="420cf-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="420cf-118">Remarks</span></span>

<span data-ttu-id="420cf-119">`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="420cf-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="420cf-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="420cf-120">References</span></span>

- <span data-ttu-id="420cf-121">Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="420cf-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="420cf-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="420cf-122">See Also</span></span>

- [<span data-ttu-id="420cf-123">Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="420cf-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)