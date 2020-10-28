---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732932"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="01fea-102">GreaterThanOrEqualI función)</span><span class="sxs-lookup"><span data-stu-id="01fea-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="01fea-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="01fea-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="01fea-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01fea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01fea-105">Devuelve true si y solo si un número es mayor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="01fea-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="01fea-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="01fea-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="01fea-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01fea-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01fea-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="01fea-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="01fea-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01fea-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01fea-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="01fea-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="01fea-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="01fea-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01fea-112">`true` es si y solo si `a` es mayor que o es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="01fea-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="01fea-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="01fea-113">Remarks</span></span>

<span data-ttu-id="01fea-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="01fea-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```