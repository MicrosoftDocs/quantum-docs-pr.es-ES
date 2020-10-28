---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727497"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="c13b9-102">RangeAsIntArray función)</span><span class="sxs-lookup"><span data-stu-id="c13b9-102">RangeAsIntArray function</span></span>

<span data-ttu-id="c13b9-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c13b9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c13b9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c13b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c13b9-105">Crea una matriz `arr` de enteros enumerados por Start.. paso... extremo.</span><span class="sxs-lookup"><span data-stu-id="c13b9-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="c13b9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c13b9-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="c13b9-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c13b9-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c13b9-108">`Range`De valores `start..step..end` que se van a convertir en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c13b9-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="c13b9-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c13b9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c13b9-110">Nueva matriz de enteros que corresponde a los valores iterados por `range` .</span><span class="sxs-lookup"><span data-stu-id="c13b9-110">A new array of integers corresponding to values iterated over by `range`.</span></span>