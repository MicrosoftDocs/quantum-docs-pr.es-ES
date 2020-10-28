---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732924"
---
# <a name="lessthani-function"></a><span data-ttu-id="54a4e-102">LessThanI función)</span><span class="sxs-lookup"><span data-stu-id="54a4e-102">LessThanI function</span></span>

<span data-ttu-id="54a4e-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="54a4e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="54a4e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54a4e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54a4e-105">Devuelve true si y solo si un número es menor que otro número.</span><span class="sxs-lookup"><span data-stu-id="54a4e-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="54a4e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="54a4e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="54a4e-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54a4e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54a4e-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="54a4e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="54a4e-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54a4e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54a4e-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="54a4e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="54a4e-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54a4e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54a4e-112">`true` es si y solo si `a` es estrictamente menor que `b` .</span><span class="sxs-lookup"><span data-stu-id="54a4e-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="54a4e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54a4e-113">Remarks</span></span>

<span data-ttu-id="54a4e-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="54a4e-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```