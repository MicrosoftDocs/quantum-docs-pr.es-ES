---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operación ApplyPermutationUsingDecomposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733972"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="99285-102">Operación ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="99285-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="99285-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="99285-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="99285-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99285-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99285-105">Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la descomposición.</span><span class="sxs-lookup"><span data-stu-id="99285-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="99285-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="99285-106">Description</span></span>

<span data-ttu-id="99285-107">Este procedimiento implementa el enfoque de síntesis basado en la descomposición.</span><span class="sxs-lookup"><span data-stu-id="99285-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="99285-108">La entrada es una permutación $ \pi $ sobre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, que representa una función booleana $n $-variable reversible.</span><span class="sxs-lookup"><span data-stu-id="99285-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="99285-109">El algoritmo realiza de forma iterativa los pasos siguientes para cada índice de variable $i $:</span><span class="sxs-lookup"><span data-stu-id="99285-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="99285-110">Compute $ ((\ pi_l, \ pi_r), \pi ') $ tal que las imágenes de $ \ pi_l $ y $ \ pi_r $ no cambian los bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambian el bit $i $ en sus elementos.</span><span class="sxs-lookup"><span data-stu-id="99285-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="99285-111">Establezca $ \pi \leftarrow \pi $ y derive las tablas de verdad de $ \ pi_l $ y $ \ pi_r $ basándose en elementos que no son de puntos fijos.</span><span class="sxs-lookup"><span data-stu-id="99285-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="99285-112">Después de aplicar estos pasos para todos los índices de variables, la permutación restante $ \pi $ será la identidad y, en función de los índices y las tablas reales recopilados, puede aplicar operaciones controladas por la tabla de verdad @"microsoft.quantum.intrinsic.x" mediante la @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operación.</span><span class="sxs-lookup"><span data-stu-id="99285-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="99285-113">El orden de las variables es $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="99285-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="99285-114">Se puede especificar un orden de variable personalizado en la operación @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="99285-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="99285-115">Entrada</span><span class="sxs-lookup"><span data-stu-id="99285-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="99285-116">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="99285-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="99285-117">Una permutación de $2 ^ n $ elementos a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="99285-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="99285-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="99285-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="99285-119">Una lista de $n $ qubits a la que se aplica la permutación.</span><span class="sxs-lookup"><span data-stu-id="99285-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99285-120">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99285-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="99285-121">Referencias</span><span class="sxs-lookup"><span data-stu-id="99285-121">References</span></span>

- [<span data-ttu-id="99285-122">*Alexis de vos* , *Yvan van Rentergem* , ADV. en Math. of COMM. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="99285-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="99285-123">*Dittrich Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of simbólica Calculation 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="99285-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="99285-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99285-124">See Also</span></span>

- [<span data-ttu-id="99285-125">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="99285-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="99285-126">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="99285-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)