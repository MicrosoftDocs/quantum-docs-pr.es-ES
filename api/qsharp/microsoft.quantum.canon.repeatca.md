---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operación RepeatCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728433"
---
# <a name="repeatca-operation"></a><span data-ttu-id="99d32-102">Operación RepeatCA</span><span class="sxs-lookup"><span data-stu-id="99d32-102">RepeatCA operation</span></span>

<span data-ttu-id="99d32-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99d32-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99d32-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99d32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99d32-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="99d32-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="99d32-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="99d32-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="99d32-107">OP: ' TInput => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="99d32-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="99d32-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="99d32-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="99d32-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99d32-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99d32-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="99d32-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="99d32-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="99d32-111">input : 'TInput</span></span>

<span data-ttu-id="99d32-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="99d32-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99d32-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99d32-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99d32-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="99d32-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="99d32-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="99d32-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="99d32-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99d32-116">See Also</span></span>

- [<span data-ttu-id="99d32-117">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="99d32-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="99d32-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="99d32-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="99d32-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="99d32-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="99d32-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="99d32-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)