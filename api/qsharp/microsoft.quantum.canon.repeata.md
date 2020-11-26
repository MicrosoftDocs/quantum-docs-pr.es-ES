---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operación de repetición
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205565"
---
# <a name="repeata-operation"></a><span data-ttu-id="96a6b-102">Operación de repetición</span><span class="sxs-lookup"><span data-stu-id="96a6b-102">RepeatA operation</span></span>

<span data-ttu-id="96a6b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96a6b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96a6b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96a6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96a6b-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="96a6b-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="96a6b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96a6b-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="96a6b-107">OP: ' TInput => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="96a6b-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="96a6b-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="96a6b-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="96a6b-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96a6b-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96a6b-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="96a6b-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="96a6b-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="96a6b-111">input : 'TInput</span></span>

<span data-ttu-id="96a6b-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="96a6b-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96a6b-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96a6b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96a6b-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="96a6b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="96a6b-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="96a6b-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="96a6b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96a6b-116">See Also</span></span>

- [<span data-ttu-id="96a6b-117">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="96a6b-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="96a6b-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="96a6b-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="96a6b-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="96a6b-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="96a6b-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="96a6b-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)