---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operación DrawMany
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730349"
---
# <a name="drawmany-operation"></a><span data-ttu-id="10600-102">Operación DrawMany</span><span class="sxs-lookup"><span data-stu-id="10600-102">DrawMany operation</span></span>

<span data-ttu-id="10600-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10600-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10600-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10600-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10600-105">Repite una operación para un número determinado de muestras, recopilando sus resultados en una matriz.</span><span class="sxs-lookup"><span data-stu-id="10600-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="10600-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="10600-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="10600-107">OP: ' TInput => ' TOutput '</span><span class="sxs-lookup"><span data-stu-id="10600-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="10600-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="10600-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="10600-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10600-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10600-110">Número de muestras de la llamada `op` a que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="10600-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="10600-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="10600-111">input : 'TInput</span></span>

<span data-ttu-id="10600-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="10600-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="10600-113">Salida: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="10600-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="10600-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="10600-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="10600-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="10600-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="10600-116">' TOutput '</span><span class="sxs-lookup"><span data-stu-id="10600-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="10600-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10600-117">See Also</span></span>

- [<span data-ttu-id="10600-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="10600-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)