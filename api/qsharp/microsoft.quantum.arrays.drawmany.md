---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operación DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846200"
---
# <a name="drawmany-operation"></a><span data-ttu-id="b0811-102">Operación DrawMany</span><span class="sxs-lookup"><span data-stu-id="b0811-102">DrawMany operation</span></span>

<span data-ttu-id="b0811-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0811-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0811-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0811-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0811-105">Repite una operación para un número determinado de muestras, recopilando sus resultados en una matriz.</span><span class="sxs-lookup"><span data-stu-id="b0811-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="b0811-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0811-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="b0811-107">OP: ' TInput => ' TOutput '</span><span class="sxs-lookup"><span data-stu-id="b0811-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="b0811-108">Operación a la que se va a llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="b0811-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="b0811-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0811-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0811-110">Número de muestras de la llamada `op` a que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="b0811-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="b0811-111">entrada: ' TInput</span><span class="sxs-lookup"><span data-stu-id="b0811-111">input : 'TInput</span></span>

<span data-ttu-id="b0811-112">Entrada que se va a pasar a `op` .</span><span class="sxs-lookup"><span data-stu-id="b0811-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="b0811-113">Salida: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="b0811-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0811-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b0811-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="b0811-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="b0811-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="b0811-116">' TOutput '</span><span class="sxs-lookup"><span data-stu-id="b0811-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="b0811-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0811-117">Example</span></span>

<span data-ttu-id="b0811-118">En los siguientes ejemplos se muestra un entero, dada una operación que muestrea un solo bit cada vez.</span><span class="sxs-lookup"><span data-stu-id="b0811-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="b0811-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0811-119">See Also</span></span>

- [<span data-ttu-id="b0811-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="b0811-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)