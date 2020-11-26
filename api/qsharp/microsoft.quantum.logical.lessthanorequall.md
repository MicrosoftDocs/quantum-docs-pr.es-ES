---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197608"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="5dace-102">LessThanOrEqualL función)</span><span class="sxs-lookup"><span data-stu-id="5dace-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="5dace-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5dace-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5dace-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dace-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dace-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="5dace-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5dace-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5dace-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5dace-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5dace-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5dace-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5dace-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5dace-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5dace-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5dace-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5dace-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5dace-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5dace-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5dace-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="5dace-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dace-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5dace-113">Remarks</span></span>

<span data-ttu-id="5dace-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5dace-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```