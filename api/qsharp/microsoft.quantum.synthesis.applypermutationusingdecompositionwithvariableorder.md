---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operación ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858881"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="9d8b4-102">Operación ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="9d8b4-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="9d8b4-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9d8b4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9d8b4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d8b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d8b4-105">Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la descomposición.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9d8b4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d8b4-106">Description</span></span>

<span data-ttu-id="9d8b4-107">Esta operación es una versión más general de @"microsoft.quantum.synthesis.applypermutationusingdecomposition" en la que se puede especificar el orden de las variables.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="9d8b4-108">Un orden de variables diferente cambia la secuencia de descomposición y las tablas de veracidad utilizadas para las puertas controladas @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="9d8b4-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="9d8b4-109">Por lo tanto, cambiar el orden de las variables cambia el número de puertas generales que se usan para obtener la permutación.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="9d8b4-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d8b4-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="9d8b4-111">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9d8b4-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9d8b4-112">Una permutación de $2 ^ n $ elementos a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="9d8b4-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9d8b4-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9d8b4-114">Una permutación de $n $ Elements a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9d8b4-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d8b4-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9d8b4-116">Una lista de $n $ qubits a la que se aplica la permutación.</span><span class="sxs-lookup"><span data-stu-id="9d8b4-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d8b4-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d8b4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="9d8b4-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d8b4-118">Example</span></span>

<span data-ttu-id="9d8b4-119">Para sintetizar una `SWAP` operación:</span><span class="sxs-lookup"><span data-stu-id="9d8b4-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="9d8b4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d8b4-120">See Also</span></span>

- [<span data-ttu-id="9d8b4-121">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="9d8b4-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="9d8b4-122">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="9d8b4-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)