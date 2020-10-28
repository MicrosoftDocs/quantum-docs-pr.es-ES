---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728493"
---
# <a name="operationpowc-function"></a><span data-ttu-id="55b9a-102">OperationPowC función)</span><span class="sxs-lookup"><span data-stu-id="55b9a-102">OperationPowC function</span></span>

<span data-ttu-id="55b9a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55b9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55b9a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55b9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55b9a-105">Eleva una operación a una potencia.</span><span class="sxs-lookup"><span data-stu-id="55b9a-105">Raises an operation to a power.</span></span>
<span data-ttu-id="55b9a-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="55b9a-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="55b9a-107">Es decir, dada una operación que representa una puerta $U $, devuelve una nueva operación $U ^ m $ para una potencia $m $.</span><span class="sxs-lookup"><span data-stu-id="55b9a-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="55b9a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="55b9a-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="55b9a-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55b9a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="55b9a-110">Operación $U $ que representa la puerta que se va a repetir.</span><span class="sxs-lookup"><span data-stu-id="55b9a-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="55b9a-111">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55b9a-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55b9a-112">Número de veces que se va a repetir el $U $.</span><span class="sxs-lookup"><span data-stu-id="55b9a-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="55b9a-113">Salida: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55b9a-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="55b9a-114">Nueva operación que representa $U ^ m $, donde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="55b9a-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="55b9a-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="55b9a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55b9a-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="55b9a-116">'T</span></span>

<span data-ttu-id="55b9a-117">Tipo de la operación que se va a alimentar.</span><span class="sxs-lookup"><span data-stu-id="55b9a-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="55b9a-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55b9a-118">See Also</span></span>

- [<span data-ttu-id="55b9a-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="55b9a-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)