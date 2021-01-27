---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operación ApplySeriesOfOpsA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844665"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="6b9be-102">Operación ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="6b9be-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="6b9be-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b9be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b9be-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b9be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b9be-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="6b9be-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="6b9be-106">(Contiguo)</span><span class="sxs-lookup"><span data-stu-id="6b9be-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6b9be-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b9be-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="6b9be-108">listOfOps: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ []</span><span class="sxs-lookup"><span data-stu-id="6b9be-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="6b9be-109">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="6b9be-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="6b9be-110">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6b9be-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="6b9be-111">Cada debe tener un functor injoin</span><span class="sxs-lookup"><span data-stu-id="6b9be-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="6b9be-112">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6b9be-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6b9be-113">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="6b9be-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6b9be-114">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="6b9be-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="6b9be-115">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="6b9be-115">register : 'T[]</span></span>

<span data-ttu-id="6b9be-116">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="6b9be-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b9be-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b9be-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b9be-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6b9be-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b9be-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="6b9be-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="6b9be-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b9be-120">Example</span></span>

<span data-ttu-id="6b9be-121">A continuación se aplica exp ([PauliX, PauliY], 0,5) a qubits 0, 1//then X a qubit 2 Let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitA (X, _)]; permitir índices = [[0, 1], [2]]; ApplySeriesOfOpsA (OPS, índices, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="6b9be-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="6b9be-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b9be-122">See Also</span></span>

- [<span data-ttu-id="6b9be-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6b9be-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)