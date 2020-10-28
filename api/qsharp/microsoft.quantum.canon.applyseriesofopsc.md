---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operación ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729333"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="621ba-102">Operación ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="621ba-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="621ba-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="621ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="621ba-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="621ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="621ba-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="621ba-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="621ba-106">Regula</span><span class="sxs-lookup"><span data-stu-id="621ba-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="621ba-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="621ba-107">Input</span></span>

### <a name="listofops--t--unit-ctl"></a><span data-ttu-id="621ba-108">listOfOps: ' t [] => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="621ba-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="621ba-109">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="621ba-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="621ba-110">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="621ba-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="621ba-111">Cada debe tener un functor controlado</span><span class="sxs-lookup"><span data-stu-id="621ba-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="621ba-112">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="621ba-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="621ba-113">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="621ba-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="621ba-114">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="621ba-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="621ba-115">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="621ba-115">register : 'T[]</span></span>

<span data-ttu-id="621ba-116">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="621ba-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="621ba-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="621ba-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="621ba-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="621ba-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="621ba-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="621ba-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="621ba-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="621ba-120">See Also</span></span>

- [<span data-ttu-id="621ba-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="621ba-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)