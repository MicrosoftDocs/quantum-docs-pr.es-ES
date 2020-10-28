---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726027"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="59d79-102">LessThanOrEqualI función)</span><span class="sxs-lookup"><span data-stu-id="59d79-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="59d79-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="59d79-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="59d79-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59d79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59d79-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="59d79-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="59d79-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="59d79-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="59d79-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59d79-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59d79-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="59d79-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="59d79-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59d79-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59d79-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="59d79-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="59d79-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59d79-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="59d79-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="59d79-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="59d79-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59d79-113">Remarks</span></span>

<span data-ttu-id="59d79-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="59d79-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```