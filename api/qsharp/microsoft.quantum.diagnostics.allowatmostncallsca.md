---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operación AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727370"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="413dd-102">Operación AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="413dd-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="413dd-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="413dd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="413dd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="413dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="413dd-105">Entre una llamada a esta operación y su método contiguo, se declara que se llama a una operación determinada a lo sumo un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="413dd-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="413dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="413dd-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="413dd-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="413dd-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="413dd-108">Número máximo de veces que `op` se puede llamar a.</span><span class="sxs-lookup"><span data-stu-id="413dd-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="413dd-109">OP: ' TInput => ' TOutput ajustable + CTL</span><span class="sxs-lookup"><span data-stu-id="413dd-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="413dd-110">Operación cuyas llamadas se van a restringir.</span><span class="sxs-lookup"><span data-stu-id="413dd-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="413dd-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="413dd-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="413dd-112">Mensaje que se va a mostrar cuando se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="413dd-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="413dd-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="413dd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="413dd-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="413dd-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="413dd-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="413dd-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="413dd-116">' TOutput '</span><span class="sxs-lookup"><span data-stu-id="413dd-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="413dd-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="413dd-117">Remarks</span></span>

<span data-ttu-id="413dd-118">Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.</span><span class="sxs-lookup"><span data-stu-id="413dd-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>