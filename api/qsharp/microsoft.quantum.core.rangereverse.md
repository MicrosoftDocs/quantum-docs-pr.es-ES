---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853652"
---
# <a name="rangereverse-function"></a><span data-ttu-id="cc35b-102">RangeReverse función)</span><span class="sxs-lookup"><span data-stu-id="cc35b-102">RangeReverse function</span></span>

<span data-ttu-id="cc35b-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="cc35b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="cc35b-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cc35b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cc35b-105">Devuelve un nuevo intervalo que es el inverso del intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc35b-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="cc35b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc35b-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="cc35b-107">r: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="cc35b-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="cc35b-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc35b-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="cc35b-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="cc35b-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="cc35b-110">Nuevo intervalo que es el inverso del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="cc35b-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc35b-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc35b-111">Remarks</span></span>

<span data-ttu-id="cc35b-112">Tenga en cuenta que el inverso de un intervalo no es simplemente `end` .. `-step` .. `start` , porque el último elemento de un intervalo no puede ser el mismo que `end` .</span><span class="sxs-lookup"><span data-stu-id="cc35b-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>