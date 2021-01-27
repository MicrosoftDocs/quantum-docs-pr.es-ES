---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operación ApplySeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841497"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="12d14-102">Operación ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="12d14-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="12d14-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12d14-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12d14-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12d14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12d14-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="12d14-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="12d14-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="12d14-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="12d14-107">listOfOps: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="12d14-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="12d14-108">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="12d14-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="12d14-109">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="12d14-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="12d14-110">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="12d14-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="12d14-111">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="12d14-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="12d14-112">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="12d14-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="12d14-113">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="12d14-113">register : 'T[]</span></span>

<span data-ttu-id="12d14-114">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="12d14-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="12d14-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12d14-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="12d14-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="12d14-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12d14-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="12d14-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="12d14-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12d14-118">Example</span></span>

<span data-ttu-id="12d14-119">A continuación se aplica exp ([PauliX, PauliY], 0,5) a qubits 0, 1//then X a qubit 2 Let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; permitir índices = [[0, 1], [2]]; ApplySeriesOfOps (OPS, índices, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="12d14-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="12d14-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12d14-120">See Also</span></span>

- [<span data-ttu-id="12d14-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="12d14-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)