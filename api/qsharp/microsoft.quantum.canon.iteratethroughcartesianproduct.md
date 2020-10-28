---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operación IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728643"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="7deff-102">Operación IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="7deff-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="7deff-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7deff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7deff-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7deff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7deff-105">Aplica una operación para cada índice del producto cartesiano de varios intervalos.</span><span class="sxs-lookup"><span data-stu-id="7deff-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="7deff-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7deff-106">Description</span></span>

<span data-ttu-id="7deff-107">Aplica de forma iterativa una operación para cada elemento del producto cartesiano de `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,... `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="7deff-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="7deff-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7deff-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="7deff-109">límites: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7deff-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7deff-110">Una matriz que especifica los intervalos en los que se va a recorrer en iteración, donde cada intervalo se especifica como una longitud entera.</span><span class="sxs-lookup"><span data-stu-id="7deff-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="7deff-111">OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7deff-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7deff-112">Operación a la que se va a llamar para cada elemento del producto cartesiano determinado.</span><span class="sxs-lookup"><span data-stu-id="7deff-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7deff-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7deff-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7deff-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7deff-114">See Also</span></span>

- [<span data-ttu-id="7deff-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="7deff-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)