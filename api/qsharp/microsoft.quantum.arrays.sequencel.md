---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Función sequencel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730021"
---
# <a name="sequencel-function"></a><span data-ttu-id="2915c-102">Función sequencel</span><span class="sxs-lookup"><span data-stu-id="2915c-102">SequenceL function</span></span>

<span data-ttu-id="2915c-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2915c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2915c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2915c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2915c-105">Obtiene una matriz de enteros en un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="2915c-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="2915c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2915c-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="2915c-107">From: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2915c-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2915c-108">Índice inicial inclusivo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2915c-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="2915c-109">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2915c-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2915c-110">Índice final inclusivo del intervalo que no es menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="2915c-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="2915c-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="2915c-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="2915c-112">Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .</span><span class="sxs-lookup"><span data-stu-id="2915c-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2915c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2915c-113">Remarks</span></span>

<span data-ttu-id="2915c-114">La diferencia entre `from` y `to` debe ajustarse a un `Int` valor.</span><span class="sxs-lookup"><span data-stu-id="2915c-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>