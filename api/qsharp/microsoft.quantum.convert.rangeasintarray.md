---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850098"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="fa096-102">RangeAsIntArray función)</span><span class="sxs-lookup"><span data-stu-id="fa096-102">RangeAsIntArray function</span></span>

<span data-ttu-id="fa096-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="fa096-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="fa096-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa096-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa096-105">Crea una matriz `arr` de enteros enumerados por Start.. paso... extremo.</span><span class="sxs-lookup"><span data-stu-id="fa096-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="fa096-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fa096-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="fa096-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="fa096-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="fa096-108">`Range`De valores `start..step..end` que se van a convertir en una matriz.</span><span class="sxs-lookup"><span data-stu-id="fa096-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="fa096-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fa096-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fa096-110">Nueva matriz de enteros que corresponde a los valores iterados por `range` .</span><span class="sxs-lookup"><span data-stu-id="fa096-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="fa096-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa096-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```