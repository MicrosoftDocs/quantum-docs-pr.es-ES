---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operación DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210002"
---
# <a name="drawmany-operation"></a><span data-ttu-id="8b0ec-102">Operación DrawMany</span><span class="sxs-lookup"><span data-stu-id="8b0ec-102">DrawMany operation</span></span>

<span data-ttu-id="8b0ec-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b0ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b0ec-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b0ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b0ec-105">Repite una operación para un número determinado de muestras, recopilando sus resultados en una matriz.</span><span class="sxs-lookup"><span data-stu-id="8b0ec-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="8b0ec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b0ec-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="8b0ec-107">OP: ' TInput => ' TOutput '</span><span class="sxs-lookup"><span data-stu-id="8b0ec-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="8b0ec-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="8b0ec-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="8b0ec-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b0ec-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b0ec-110">Número de muestras de la llamada `op` a que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="8b0ec-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="8b0ec-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="8b0ec-111">input : 'TInput</span></span>

<span data-ttu-id="8b0ec-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="8b0ec-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="8b0ec-113">Salida: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="8b0ec-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8b0ec-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8b0ec-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="8b0ec-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="8b0ec-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="8b0ec-116">' TOutput '</span><span class="sxs-lookup"><span data-stu-id="8b0ec-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="8b0ec-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b0ec-117">See Also</span></span>

- [<span data-ttu-id="8b0ec-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="8b0ec-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)