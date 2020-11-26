---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operación ApplySeriesOfOps
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218009"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="97699-102">Operación ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="97699-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="97699-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="97699-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="97699-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97699-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97699-105">Aplica una lista de operaciones y sus destinos secuencialmente en una matriz.</span><span class="sxs-lookup"><span data-stu-id="97699-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="97699-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="97699-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="97699-107">listOfOps: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="97699-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="97699-108">Lista de operaciones, cada una de las cuales toma una matriz ' t ' que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="97699-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="97699-109">Se aplican secuencialmente, el índice más bajo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="97699-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="97699-110">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="97699-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="97699-111">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="97699-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="97699-112">Cada matriz debe contener una lista de enteros que describen los índices que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="97699-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="97699-113">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="97699-113">register : 'T[]</span></span>

<span data-ttu-id="97699-114">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="97699-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97699-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97699-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="97699-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="97699-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="97699-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="97699-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="97699-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97699-118">See Also</span></span>

- [<span data-ttu-id="97699-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="97699-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)