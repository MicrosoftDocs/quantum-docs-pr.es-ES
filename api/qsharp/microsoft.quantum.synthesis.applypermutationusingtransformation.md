---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Operación ApplyPermutationUsingTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858994"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="13c8d-102">Operación ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="13c8d-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="13c8d-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="13c8d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="13c8d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13c8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13c8d-105">Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la transformación.</span><span class="sxs-lookup"><span data-stu-id="13c8d-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="13c8d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="13c8d-106">Description</span></span>

<span data-ttu-id="13c8d-107">Este procedimiento implementa el enfoque de síntesis basado en la transformación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="13c8d-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="13c8d-108">La entrada es una permutación $ \pi $ sobre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, que representa una función booleana $n $-variable reversible.</span><span class="sxs-lookup"><span data-stu-id="13c8d-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="13c8d-109">El algoritmo realiza de forma iterativa los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="13c8d-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="13c8d-110">Busque la $x más pequeña, por ejemplo, $x \ne \pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="13c8d-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="13c8d-111">Buscar operaciones de Toffoli con control múltiple, que se aplican a las salidas make $ \pi (x) = x $ y no cambian $ \pi (x ') $ para todos los $x ' < x $</span><span class="sxs-lookup"><span data-stu-id="13c8d-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="13c8d-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="13c8d-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="13c8d-113">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="13c8d-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="13c8d-114">Una permutación de $2 ^ n $ elementos a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="13c8d-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="13c8d-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="13c8d-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="13c8d-116">Una lista de $n $ qubits a la que se aplica la permutación.</span><span class="sxs-lookup"><span data-stu-id="13c8d-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13c8d-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13c8d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="13c8d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13c8d-118">Example</span></span>

<span data-ttu-id="13c8d-119">Para sintetizar una `SWAP` operación:</span><span class="sxs-lookup"><span data-stu-id="13c8d-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="13c8d-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="13c8d-120">References</span></span>

- [<span data-ttu-id="13c8d-121">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, PP. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="13c8d-121">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="13c8d-122">*Dittrich Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, PP. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="13c8d-122">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="13c8d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13c8d-123">See Also</span></span>

- [<span data-ttu-id="13c8d-124">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="13c8d-124">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)