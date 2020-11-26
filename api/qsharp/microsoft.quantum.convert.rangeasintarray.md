---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214014"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="048db-102">RangeAsIntArray función)</span><span class="sxs-lookup"><span data-stu-id="048db-102">RangeAsIntArray function</span></span>

<span data-ttu-id="048db-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="048db-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="048db-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="048db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="048db-105">Crea una matriz `arr` de enteros enumerados por Start.. paso... extremo.</span><span class="sxs-lookup"><span data-stu-id="048db-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="048db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="048db-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="048db-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="048db-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="048db-108">`Range`De valores `start..step..end` que se van a convertir en una matriz.</span><span class="sxs-lookup"><span data-stu-id="048db-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="048db-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="048db-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="048db-110">Nueva matriz de enteros que corresponde a los valores iterados por `range` .</span><span class="sxs-lookup"><span data-stu-id="048db-110">A new array of integers corresponding to values iterated over by `range`.</span></span>