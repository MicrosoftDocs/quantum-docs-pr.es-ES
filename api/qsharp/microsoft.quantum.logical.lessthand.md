---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732925"
---
# <a name="lessthand-function"></a><span data-ttu-id="68589-102">LessThanD función)</span><span class="sxs-lookup"><span data-stu-id="68589-102">LessThanD function</span></span>

<span data-ttu-id="68589-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="68589-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="68589-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68589-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68589-105">Devuelve true si y solo si un número es menor que otro número.</span><span class="sxs-lookup"><span data-stu-id="68589-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="68589-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="68589-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="68589-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="68589-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="68589-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="68589-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="68589-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="68589-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="68589-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="68589-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="68589-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68589-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68589-112">`true` es si y solo si `a` es estrictamente menor que `b` .</span><span class="sxs-lookup"><span data-stu-id="68589-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="68589-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="68589-113">Remarks</span></span>

<span data-ttu-id="68589-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="68589-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```