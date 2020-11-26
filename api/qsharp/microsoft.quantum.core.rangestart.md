---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224010"
---
# <a name="rangestart-function"></a><span data-ttu-id="afa12-102">RangeStart (función)</span><span class="sxs-lookup"><span data-stu-id="afa12-102">RangeStart function</span></span>

<span data-ttu-id="afa12-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="afa12-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="afa12-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="afa12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="afa12-105">Devuelve el valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="afa12-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="afa12-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="afa12-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="afa12-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="afa12-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="afa12-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="afa12-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="afa12-109">Valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="afa12-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="afa12-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="afa12-110">Remarks</span></span>

<span data-ttu-id="afa12-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="afa12-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="afa12-112">Tenga en cuenta que el valor inicial definido de un intervalo es el mismo que el primer elemento de la secuencia, a menos que el intervalo especifique una secuencia vacía (por ejemplo, 2..</span><span class="sxs-lookup"><span data-stu-id="afa12-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="afa12-113">1).</span><span class="sxs-lookup"><span data-stu-id="afa12-113">1).</span></span>