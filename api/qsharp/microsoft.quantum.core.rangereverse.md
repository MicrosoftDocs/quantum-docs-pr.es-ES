---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213844"
---
# <a name="rangereverse-function"></a><span data-ttu-id="bb9b4-102">RangeReverse función)</span><span class="sxs-lookup"><span data-stu-id="bb9b4-102">RangeReverse function</span></span>

<span data-ttu-id="bb9b4-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="bb9b4-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="bb9b4-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bb9b4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bb9b4-105">Devuelve un nuevo intervalo que es el inverso del intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="bb9b4-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="bb9b4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bb9b4-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="bb9b4-107">r: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="bb9b4-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="bb9b4-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="bb9b4-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="bb9b4-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="bb9b4-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="bb9b4-110">Nuevo intervalo que es el inverso del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="bb9b4-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb9b4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bb9b4-111">Remarks</span></span>

<span data-ttu-id="bb9b4-112">Tenga en cuenta que el inverso de un intervalo no es simplemente `end` .. `-step` .. `start` , porque el último elemento de un intervalo no puede ser el mismo que `end` .</span><span class="sxs-lookup"><span data-stu-id="bb9b4-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>