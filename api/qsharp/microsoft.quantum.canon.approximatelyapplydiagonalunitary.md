---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operación ApproximatelyApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728979"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="f984b-102">Operación ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="f984b-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="f984b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f984b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f984b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f984b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f984b-105">Aplica una matriz de fases complejas a Estados de base numéricos de un registro de qubits, truncando ángulos de rotación pequeños según una tolerancia determinada.</span><span class="sxs-lookup"><span data-stu-id="f984b-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f984b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f984b-106">Description</span></span>

<span data-ttu-id="f984b-107">Esta operación implementa una unitario diagonal que aplica una fase compleja $e ^ {i \ theta_j} $ en el $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="f984b-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="f984b-108">En concreto, esta operación se puede representar mediante la unitario</span><span class="sxs-lookup"><span data-stu-id="f984b-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="f984b-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="f984b-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="f984b-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f984b-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f984b-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="f984b-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f984b-112">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f984b-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f984b-113">Tolerancia por debajo de la cual se truncan los coeficientes pequeños.</span><span class="sxs-lookup"><span data-stu-id="f984b-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f984b-114">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f984b-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f984b-115">Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="f984b-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="f984b-116">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f984b-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f984b-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f984b-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f984b-118">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f984b-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f984b-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f984b-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f984b-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f984b-120">Remarks</span></span>

<span data-ttu-id="f984b-121">`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="f984b-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f984b-122">Referencias</span><span class="sxs-lookup"><span data-stu-id="f984b-122">References</span></span>

- <span data-ttu-id="f984b-123">Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f984b-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="f984b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f984b-124">See Also</span></span>

- [<span data-ttu-id="f984b-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="f984b-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)