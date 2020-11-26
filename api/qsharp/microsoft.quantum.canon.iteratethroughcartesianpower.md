---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operación IterateThroughCartesianPower
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206483"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="fda86-102">Operación IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="fda86-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="fda86-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fda86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fda86-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fda86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fda86-105">Aplica una operación para cada índice en la potencia cartesiano de un intervalo de enteros.</span><span class="sxs-lookup"><span data-stu-id="fda86-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="fda86-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fda86-106">Description</span></span>

<span data-ttu-id="fda86-107">Aplica de forma iterativa una operación para cada elemento de una potencia cartesiano del intervalo `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="fda86-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="fda86-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fda86-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="fda86-109">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fda86-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fda86-110">La potencia cartesiano a la que `0..(bound - 1)` se debe elevar el intervalo.</span><span class="sxs-lookup"><span data-stu-id="fda86-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="fda86-111">enlazado: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fda86-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fda86-112">Especificación del intervalo que se va a recorrer en iteración, dado como la longitud del intervalo.</span><span class="sxs-lookup"><span data-stu-id="fda86-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="fda86-113">OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fda86-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fda86-114">Operación a la que se va a llamar para cada elemento de la potencia cartesiano dada.</span><span class="sxs-lookup"><span data-stu-id="fda86-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fda86-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fda86-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fda86-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fda86-116">See Also</span></span>

- [<span data-ttu-id="fda86-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="fda86-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)