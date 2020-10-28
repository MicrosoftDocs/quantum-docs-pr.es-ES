---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operación IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728637"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="854fc-102">Operación IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="854fc-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="854fc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="854fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="854fc-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="854fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="854fc-105">Aplica una operación para cada índice en la potencia cartesiano de un intervalo de enteros.</span><span class="sxs-lookup"><span data-stu-id="854fc-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="854fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="854fc-106">Description</span></span>

<span data-ttu-id="854fc-107">Aplica de forma iterativa una operación para cada elemento de una potencia cartesiano del intervalo `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="854fc-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="854fc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="854fc-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="854fc-109">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="854fc-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="854fc-110">La potencia cartesiano a la que `0..(bound - 1)` se debe elevar el intervalo.</span><span class="sxs-lookup"><span data-stu-id="854fc-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="854fc-111">enlazado: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="854fc-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="854fc-112">Especificación del intervalo que se va a recorrer en iteración, dado como la longitud del intervalo.</span><span class="sxs-lookup"><span data-stu-id="854fc-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="854fc-113">OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="854fc-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="854fc-114">Operación a la que se va a llamar para cada elemento de la potencia cartesiano dada.</span><span class="sxs-lookup"><span data-stu-id="854fc-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="854fc-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="854fc-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="854fc-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="854fc-116">See Also</span></span>

- [<span data-ttu-id="854fc-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="854fc-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)