---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727448"
---
# <a name="rangeend-function"></a><span data-ttu-id="7ba39-102">RangeEnd función)</span><span class="sxs-lookup"><span data-stu-id="7ba39-102">RangeEnd function</span></span>

<span data-ttu-id="7ba39-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="7ba39-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="7ba39-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7ba39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7ba39-105">Devuelve el valor final definido del intervalo especificado, que no es necesariamente el último elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7ba39-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="7ba39-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ba39-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="7ba39-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7ba39-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="7ba39-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ba39-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ba39-109">Valor final definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="7ba39-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ba39-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ba39-110">Remarks</span></span>

<span data-ttu-id="7ba39-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="7ba39-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="7ba39-112">Tenga en cuenta que el valor final definido de un intervalo puede diferir del último elemento de la secuencia especificada por el intervalo; por ejemplo, en un intervalo de 0..</span><span class="sxs-lookup"><span data-stu-id="7ba39-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="7ba39-113">2..</span><span class="sxs-lookup"><span data-stu-id="7ba39-113">2 ..</span></span> <span data-ttu-id="7ba39-114">5 el último elemento es 4, pero el valor final es 5.</span><span class="sxs-lookup"><span data-stu-id="7ba39-114">5 the last element is 4 but the end value is 5.</span></span>