---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operación de repetición
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728439"
---
# <a name="repeata-operation"></a><span data-ttu-id="8c281-102">Operación de repetición</span><span class="sxs-lookup"><span data-stu-id="8c281-102">RepeatA operation</span></span>

<span data-ttu-id="8c281-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c281-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c281-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c281-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c281-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="8c281-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="8c281-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8c281-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="8c281-107">OP: ' TInput => ADJ de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c281-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8c281-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="8c281-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="8c281-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c281-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c281-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="8c281-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="8c281-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="8c281-111">input : 'TInput</span></span>

<span data-ttu-id="8c281-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="8c281-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c281-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c281-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c281-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8c281-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="8c281-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="8c281-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="8c281-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c281-116">See Also</span></span>

- [<span data-ttu-id="8c281-117">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="8c281-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="8c281-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="8c281-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="8c281-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="8c281-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="8c281-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="8c281-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)