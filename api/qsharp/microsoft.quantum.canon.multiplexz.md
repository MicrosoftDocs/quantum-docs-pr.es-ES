---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Operación MultiplexZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728534"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="79220-102">Operación MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="79220-102">MultiplexZ operation</span></span>

<span data-ttu-id="79220-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79220-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79220-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79220-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79220-105">Aplica una rotación de Pauli Z condicionada en una matriz de qubits.</span><span class="sxs-lookup"><span data-stu-id="79220-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="79220-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="79220-106">Description</span></span>

<span data-ttu-id="79220-107">De esta forma se aplica la operación de unitario controlada multiplicación que realiza rotaciones por ángulo $ \ theta_j $ sobre el operador Pauli de un solo qubit $Z $ cuando lo controla el $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="79220-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="79220-108">En concreto, esta operación se puede representar mediante la unitario</span><span class="sxs-lookup"><span data-stu-id="79220-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="79220-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="79220-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="79220-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="79220-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="79220-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="79220-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="79220-112">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="79220-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="79220-113">Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="79220-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="79220-114">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="79220-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="79220-115">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79220-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="79220-116">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="79220-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="79220-117">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="79220-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="79220-118">Registro de qubit único que gira $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="79220-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79220-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79220-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="79220-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="79220-120">Remarks</span></span>

<span data-ttu-id="79220-121">`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="79220-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="79220-122">Referencias</span><span class="sxs-lookup"><span data-stu-id="79220-122">References</span></span>

- <span data-ttu-id="79220-123">Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="79220-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="79220-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79220-124">See Also</span></span>

- [<span data-ttu-id="79220-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="79220-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)