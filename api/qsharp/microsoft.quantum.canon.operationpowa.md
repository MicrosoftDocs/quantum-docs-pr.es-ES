---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728505"
---
# <a name="operationpowa-function"></a><span data-ttu-id="c3cf8-102">OperationPowA función)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-102">OperationPowA function</span></span>

<span data-ttu-id="c3cf8-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3cf8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3cf8-105">Eleva una operación a una potencia.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-105">Raises an operation to a power.</span></span>
<span data-ttu-id="c3cf8-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="c3cf8-107">Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="c3cf8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3cf8-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c3cf8-109">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c3cf8-110">Operación $U $ que representa la puerta que se va a repetir.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c3cf8-111">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3cf8-112">Número de veces que se va a repetir el $U $.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="c3cf8-113">Salida: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3cf8-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c3cf8-114">Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3cf8-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c3cf8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3cf8-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="c3cf8-116">'T</span></span>

<span data-ttu-id="c3cf8-117">Tipo de la operación que se va a alimentar.</span><span class="sxs-lookup"><span data-stu-id="c3cf8-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3cf8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3cf8-118">See Also</span></span>

- [<span data-ttu-id="c3cf8-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="c3cf8-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)