---
uid: Microsoft.Quantum.Canon.RepeatC
title: Operación RepeatC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840266"
---
# <a name="repeatc-operation"></a><span data-ttu-id="f58ca-102">Operación RepeatC</span><span class="sxs-lookup"><span data-stu-id="f58ca-102">RepeatC operation</span></span>

<span data-ttu-id="f58ca-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f58ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f58ca-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f58ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f58ca-105">Repite una operación un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="f58ca-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f58ca-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f58ca-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="f58ca-107">OP: ' TInput => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="f58ca-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f58ca-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="f58ca-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f58ca-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f58ca-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f58ca-110">Número de veces que se va a llamar a `op` .</span><span class="sxs-lookup"><span data-stu-id="f58ca-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f58ca-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="f58ca-111">input : 'TInput</span></span>

<span data-ttu-id="f58ca-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="f58ca-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f58ca-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f58ca-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f58ca-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f58ca-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f58ca-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="f58ca-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="f58ca-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f58ca-116">Example</span></span>

<span data-ttu-id="f58ca-117">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f58ca-117">The following are equivalent:</span></span>

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="f58ca-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f58ca-118">See Also</span></span>

- [<span data-ttu-id="f58ca-119">Microsoft. Quantum. arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="f58ca-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f58ca-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="f58ca-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f58ca-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="f58ca-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="f58ca-122">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f58ca-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)