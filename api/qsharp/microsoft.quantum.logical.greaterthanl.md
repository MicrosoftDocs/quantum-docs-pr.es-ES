---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726650"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="be6fb-102">GreaterThanL función)</span><span class="sxs-lookup"><span data-stu-id="be6fb-102">GreaterThanL function</span></span>

<span data-ttu-id="be6fb-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="be6fb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="be6fb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be6fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be6fb-105">Devuelve true si y solo si un número es mayor que otro número.</span><span class="sxs-lookup"><span data-stu-id="be6fb-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="be6fb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="be6fb-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="be6fb-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="be6fb-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="be6fb-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="be6fb-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="be6fb-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="be6fb-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="be6fb-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="be6fb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="be6fb-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="be6fb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="be6fb-112">`true` es si y solo si `a` es estrictamente mayor que `b` .</span><span class="sxs-lookup"><span data-stu-id="be6fb-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="be6fb-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="be6fb-113">Remarks</span></span>

<span data-ttu-id="be6fb-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="be6fb-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```