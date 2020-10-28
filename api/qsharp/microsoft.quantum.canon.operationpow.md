---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728529"
---
# <a name="operationpow-function"></a><span data-ttu-id="dbada-102">OperationPow función)</span><span class="sxs-lookup"><span data-stu-id="dbada-102">OperationPow function</span></span>

<span data-ttu-id="dbada-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dbada-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dbada-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbada-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbada-105">Eleva una operación a una potencia.</span><span class="sxs-lookup"><span data-stu-id="dbada-105">Raises an operation to a power.</span></span>

<span data-ttu-id="dbada-106">Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.</span><span class="sxs-lookup"><span data-stu-id="dbada-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="dbada-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="dbada-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="dbada-108">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="dbada-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dbada-109">Operación $U $ que representa la puerta que se va a repetir.</span><span class="sxs-lookup"><span data-stu-id="dbada-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="dbada-110">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbada-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbada-111">Número de veces que se va a repetir el $U $.</span><span class="sxs-lookup"><span data-stu-id="dbada-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="dbada-112">Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="dbada-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dbada-113">Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="dbada-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dbada-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dbada-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbada-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="dbada-115">'T</span></span>

<span data-ttu-id="dbada-116">Tipo de la operación que se va a alimentar.</span><span class="sxs-lookup"><span data-stu-id="dbada-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbada-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbada-117">See Also</span></span>

- [<span data-ttu-id="dbada-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="dbada-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="dbada-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="dbada-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="dbada-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="dbada-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)