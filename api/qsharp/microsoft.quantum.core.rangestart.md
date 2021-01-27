---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831113"
---
# <a name="rangestart-function"></a><span data-ttu-id="6827d-102">RangeStart (función)</span><span class="sxs-lookup"><span data-stu-id="6827d-102">RangeStart function</span></span>

<span data-ttu-id="6827d-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="6827d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="6827d-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6827d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6827d-105">Devuelve el valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="6827d-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="6827d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6827d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="6827d-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6827d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="6827d-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6827d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6827d-109">Valor inicial definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="6827d-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="6827d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6827d-110">Remarks</span></span>

<span data-ttu-id="6827d-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="6827d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="6827d-112">Tenga en cuenta que el valor inicial definido de un intervalo es el mismo que el primer elemento de la secuencia, a menos que el intervalo especifique una secuencia vacía (por ejemplo, 2..</span><span class="sxs-lookup"><span data-stu-id="6827d-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="6827d-113">1).</span><span class="sxs-lookup"><span data-stu-id="6827d-113">1).</span></span>