---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operación ApplySeriesOfOpsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729338"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="c33b4-102">Operación ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="c33b4-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="c33b4-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c33b4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c33b4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c33b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c33b4-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c33b4-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="c33b4-106">(Contiguo)</span><span class="sxs-lookup"><span data-stu-id="c33b4-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c33b4-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c33b4-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="c33b4-108">listOfOps: ' t [] => el ajust de [unidad](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="c33b4-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="c33b4-109">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="c33b4-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="c33b4-110">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c33b4-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="c33b4-111">Cada debe tener un functor injoin</span><span class="sxs-lookup"><span data-stu-id="c33b4-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="c33b4-112">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="c33b4-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="c33b4-113">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="c33b4-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="c33b4-114">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="c33b4-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="c33b4-115">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="c33b4-115">register : 'T[]</span></span>

<span data-ttu-id="c33b4-116">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="c33b4-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c33b4-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c33b4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c33b4-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c33b4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c33b4-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="c33b4-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="c33b4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c33b4-120">See Also</span></span>

- [<span data-ttu-id="c33b4-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="c33b4-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)