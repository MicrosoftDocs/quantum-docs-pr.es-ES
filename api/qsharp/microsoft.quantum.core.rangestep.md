---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727412"
---
# <a name="rangestep-function"></a><span data-ttu-id="9094e-102">RangeStep función)</span><span class="sxs-lookup"><span data-stu-id="9094e-102">RangeStep function</span></span>

<span data-ttu-id="9094e-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9094e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9094e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9094e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9094e-105">Devuelve el entero que especifica cómo se calcula el siguiente valor de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="9094e-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="9094e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9094e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="9094e-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9094e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="9094e-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9094e-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9094e-109">Valor de paso definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="9094e-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="9094e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9094e-110">Remarks</span></span>

<span data-ttu-id="9094e-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="9094e-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>