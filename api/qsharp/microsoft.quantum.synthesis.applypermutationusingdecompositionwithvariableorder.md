---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operación ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733957"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="a8ae2-102">Operación ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="a8ae2-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="a8ae2-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a8ae2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a8ae2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8ae2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8ae2-105">Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la descomposición.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="a8ae2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8ae2-106">Description</span></span>

<span data-ttu-id="a8ae2-107">Esta operación es una versión más general de @"microsoft.quantum.synthesis.applypermutationusingdecomposition" en la que se puede especificar el orden de las variables.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="a8ae2-108">Un orden de variables diferente cambia la secuencia de descomposición y las tablas de veracidad utilizadas para las puertas controladas @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="a8ae2-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="a8ae2-109">Por lo tanto, cambiar el orden de las variables cambia el número de puertas generales que se usan para obtener la permutación.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="a8ae2-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="a8ae2-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="a8ae2-111">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a8ae2-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a8ae2-112">Una permutación de $2 ^ n $ elementos a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="a8ae2-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a8ae2-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a8ae2-114">Una permutación de $n $ Elements a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a8ae2-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a8ae2-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a8ae2-116">Una lista de $n $ qubits a la que se aplica la permutación.</span><span class="sxs-lookup"><span data-stu-id="a8ae2-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8ae2-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8ae2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a8ae2-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8ae2-118">See Also</span></span>

- [<span data-ttu-id="a8ae2-119">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="a8ae2-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="a8ae2-120">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="a8ae2-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)