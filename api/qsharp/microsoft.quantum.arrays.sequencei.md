---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730036"
---
# <a name="sequencei-function"></a><span data-ttu-id="30b08-102">Sequencei (función)</span><span class="sxs-lookup"><span data-stu-id="30b08-102">SequenceI function</span></span>

<span data-ttu-id="30b08-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="30b08-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="30b08-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30b08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30b08-105">Obtiene una matriz de enteros en un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="30b08-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="30b08-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="30b08-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="30b08-107">de: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="30b08-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="30b08-108">Índice inicial inclusivo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="30b08-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="30b08-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="30b08-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="30b08-110">Índice final inclusivo del intervalo que no es menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="30b08-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="30b08-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="30b08-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="30b08-112">Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .</span><span class="sxs-lookup"><span data-stu-id="30b08-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>