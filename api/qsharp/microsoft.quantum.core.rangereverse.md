---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727442"
---
# <a name="rangereverse-function"></a><span data-ttu-id="c3644-102">RangeReverse función)</span><span class="sxs-lookup"><span data-stu-id="c3644-102">RangeReverse function</span></span>

<span data-ttu-id="c3644-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="c3644-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="c3644-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3644-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3644-105">Devuelve un nuevo intervalo que es el inverso del intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3644-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="c3644-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3644-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="c3644-107">r: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c3644-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c3644-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3644-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="c3644-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c3644-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c3644-110">Nuevo intervalo que es el inverso del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="c3644-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3644-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3644-111">Remarks</span></span>

<span data-ttu-id="c3644-112">Tenga en cuenta que el inverso de un intervalo no es simplemente `end` .. `-step` .. `start` , porque el último elemento de un intervalo no puede ser el mismo que `end` .</span><span class="sxs-lookup"><span data-stu-id="c3644-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>