---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726038"
---
# <a name="lessthanl-function"></a><span data-ttu-id="18f0c-102">LessThanL función)</span><span class="sxs-lookup"><span data-stu-id="18f0c-102">LessThanL function</span></span>

<span data-ttu-id="18f0c-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="18f0c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="18f0c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18f0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18f0c-105">Devuelve true si y solo si un número es menor que otro número.</span><span class="sxs-lookup"><span data-stu-id="18f0c-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="18f0c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="18f0c-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="18f0c-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="18f0c-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="18f0c-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="18f0c-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="18f0c-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="18f0c-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="18f0c-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="18f0c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="18f0c-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="18f0c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="18f0c-112">`true` es si y solo si `a` es estrictamente menor que `b` .</span><span class="sxs-lookup"><span data-stu-id="18f0c-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18f0c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="18f0c-113">Remarks</span></span>

<span data-ttu-id="18f0c-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="18f0c-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```