---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operación RepeatCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852207"
---
# <a name="repeatca-operation"></a><span data-ttu-id="6effe-102">Operación RepeatCA</span><span class="sxs-lookup"><span data-stu-id="6effe-102">RepeatCA operation</span></span>

<span data-ttu-id="6effe-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6effe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6effe-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6effe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6effe-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="6effe-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6effe-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6effe-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="6effe-107">OP: ' TInput => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6effe-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6effe-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="6effe-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="6effe-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6effe-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6effe-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="6effe-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="6effe-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="6effe-111">input : 'TInput</span></span>

<span data-ttu-id="6effe-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="6effe-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6effe-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6effe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6effe-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6effe-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="6effe-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="6effe-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="6effe-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6effe-116">Example</span></span>

<span data-ttu-id="6effe-117">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6effe-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="6effe-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6effe-118">See Also</span></span>

- [<span data-ttu-id="6effe-119">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="6effe-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="6effe-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="6effe-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="6effe-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="6effe-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="6effe-122">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="6effe-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)