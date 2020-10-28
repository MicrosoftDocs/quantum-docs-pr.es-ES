---
uid: Microsoft.Quantum.Canon.Repeat
title: Repetir operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728456"
---
# <a name="repeat-operation"></a><span data-ttu-id="c58c1-102">Repetir operación</span><span class="sxs-lookup"><span data-stu-id="c58c1-102">Repeat operation</span></span>

<span data-ttu-id="c58c1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c58c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c58c1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c58c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c58c1-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="c58c1-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="c58c1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c58c1-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="c58c1-107">OP: ' TInput => [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c58c1-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c58c1-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="c58c1-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="c58c1-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c58c1-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c58c1-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="c58c1-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c58c1-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="c58c1-111">input : 'TInput</span></span>

<span data-ttu-id="c58c1-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="c58c1-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c58c1-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c58c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c58c1-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c58c1-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c58c1-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="c58c1-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="c58c1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c58c1-116">See Also</span></span>

- [<span data-ttu-id="c58c1-117">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="c58c1-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="c58c1-118">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="c58c1-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="c58c1-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="c58c1-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="c58c1-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="c58c1-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)