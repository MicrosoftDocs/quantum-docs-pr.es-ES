---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853596"
---
# <a name="rangestep-function"></a><span data-ttu-id="115e8-102">RangeStep función)</span><span class="sxs-lookup"><span data-stu-id="115e8-102">RangeStep function</span></span>

<span data-ttu-id="115e8-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="115e8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="115e8-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="115e8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="115e8-105">Devuelve el entero que especifica cómo se calcula el siguiente valor de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="115e8-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="115e8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="115e8-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="115e8-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="115e8-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="115e8-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="115e8-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="115e8-109">Valor de paso definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="115e8-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="115e8-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="115e8-110">Remarks</span></span>

<span data-ttu-id="115e8-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="115e8-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>