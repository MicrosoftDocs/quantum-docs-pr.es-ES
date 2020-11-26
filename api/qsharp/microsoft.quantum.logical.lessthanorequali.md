---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197573"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="c7800-102">LessThanOrEqualI función)</span><span class="sxs-lookup"><span data-stu-id="c7800-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="c7800-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c7800-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c7800-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7800-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7800-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="c7800-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c7800-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c7800-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c7800-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7800-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7800-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="c7800-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c7800-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7800-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7800-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="c7800-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c7800-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c7800-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c7800-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="c7800-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7800-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7800-113">Remarks</span></span>

<span data-ttu-id="c7800-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c7800-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```