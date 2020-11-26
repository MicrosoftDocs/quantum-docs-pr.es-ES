---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 32de77cbd54cc8eeb8c4a967fd046dca709cd9ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205650"
---
# <a name="operationpowca-function"></a><span data-ttu-id="32cc9-102">OperationPowCA función)</span><span class="sxs-lookup"><span data-stu-id="32cc9-102">OperationPowCA function</span></span>

<span data-ttu-id="32cc9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32cc9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32cc9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32cc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32cc9-105">Eleva una operación a una potencia.</span><span class="sxs-lookup"><span data-stu-id="32cc9-105">Raises an operation to a power.</span></span>
<span data-ttu-id="32cc9-106">El modificador `A` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="32cc9-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="32cc9-107">Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.</span><span class="sxs-lookup"><span data-stu-id="32cc9-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="32cc9-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="32cc9-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="32cc9-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="32cc9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="32cc9-110">Operación $U $ que representa la puerta que se va a repetir.</span><span class="sxs-lookup"><span data-stu-id="32cc9-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="32cc9-111">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32cc9-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32cc9-112">Número de veces que se va a repetir el $U $.</span><span class="sxs-lookup"><span data-stu-id="32cc9-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="32cc9-113">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="32cc9-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="32cc9-114">Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="32cc9-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32cc9-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="32cc9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32cc9-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="32cc9-116">'T</span></span>

<span data-ttu-id="32cc9-117">Tipo de la operación que se va a alimentar.</span><span class="sxs-lookup"><span data-stu-id="32cc9-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="32cc9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32cc9-118">See Also</span></span>

- [<span data-ttu-id="32cc9-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="32cc9-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)