---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213810"
---
# <a name="rangestep-function"></a><span data-ttu-id="204ce-102">RangeStep función)</span><span class="sxs-lookup"><span data-stu-id="204ce-102">RangeStep function</span></span>

<span data-ttu-id="204ce-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="204ce-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="204ce-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="204ce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="204ce-105">Devuelve el entero que especifica cómo se calcula el siguiente valor de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="204ce-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="204ce-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="204ce-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="204ce-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="204ce-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="204ce-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="204ce-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="204ce-109">Valor de paso definido del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="204ce-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="204ce-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="204ce-110">Remarks</span></span>

<span data-ttu-id="204ce-111">El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.</span><span class="sxs-lookup"><span data-stu-id="204ce-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>