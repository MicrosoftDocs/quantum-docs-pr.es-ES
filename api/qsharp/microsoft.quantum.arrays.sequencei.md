---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220304"
---
# <a name="sequencei-function"></a><span data-ttu-id="636e3-102">Sequencei (función)</span><span class="sxs-lookup"><span data-stu-id="636e3-102">SequenceI function</span></span>

<span data-ttu-id="636e3-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="636e3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="636e3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="636e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="636e3-105">Obtiene una matriz de enteros en un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="636e3-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="636e3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="636e3-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="636e3-107">de: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="636e3-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="636e3-108">Índice inicial inclusivo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="636e3-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="636e3-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="636e3-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="636e3-110">Índice final inclusivo del intervalo que no es menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="636e3-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="636e3-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="636e3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="636e3-112">Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .</span><span class="sxs-lookup"><span data-stu-id="636e3-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>