---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727413"
---
# <a name="rangestart-function"></a><span data-ttu-id="4b7f7-102">RangeStart (función)</span><span class="sxs-lookup"><span data-stu-id="4b7f7-102">RangeStart function</span></span>

<span data-ttu-id="4b7f7-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4b7f7-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4b7f7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b7f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b7f7-105">Devuelve el valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="4b7f7-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="4b7f7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b7f7-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4b7f7-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4b7f7-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="4b7f7-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b7f7-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b7f7-109">Valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="4b7f7-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b7f7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b7f7-110">Remarks</span></span>

<span data-ttu-id="4b7f7-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="4b7f7-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="4b7f7-112">Tenga en cuenta que el valor inicial definido de un intervalo es el mismo que el primer elemento de la secuencia, a menos que el intervalo especifique una secuencia vacía (por ejemplo, 2..</span><span class="sxs-lookup"><span data-stu-id="4b7f7-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="4b7f7-113">1).</span><span class="sxs-lookup"><span data-stu-id="4b7f7-113">1).</span></span>