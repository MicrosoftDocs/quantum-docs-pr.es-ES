---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operación ApplySeriesOfOpsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729327"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="1795f-102">Operación ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="1795f-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="1795f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1795f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1795f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1795f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1795f-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="1795f-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="1795f-106">(Contiguot + controlado)</span><span class="sxs-lookup"><span data-stu-id="1795f-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1795f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1795f-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="1795f-108">listOfOps: ' t [] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL []</span><span class="sxs-lookup"><span data-stu-id="1795f-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="1795f-109">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="1795f-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="1795f-110">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="1795f-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="1795f-111">Cada debe tener un control contiguo y un functor controlado.</span><span class="sxs-lookup"><span data-stu-id="1795f-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="1795f-112">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="1795f-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="1795f-113">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="1795f-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="1795f-114">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="1795f-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="1795f-115">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="1795f-115">register : 'T[]</span></span>

<span data-ttu-id="1795f-116">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="1795f-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1795f-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1795f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1795f-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1795f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1795f-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="1795f-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="1795f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1795f-120">See Also</span></span>

- [<span data-ttu-id="1795f-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="1795f-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)