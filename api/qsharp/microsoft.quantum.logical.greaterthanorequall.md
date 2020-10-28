---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732444"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="5c153-102">GreaterThanOrEqualL función)</span><span class="sxs-lookup"><span data-stu-id="5c153-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="5c153-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c153-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c153-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c153-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c153-105">Devuelve true si y solo si un número es mayor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="5c153-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5c153-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5c153-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5c153-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5c153-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5c153-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5c153-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5c153-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5c153-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5c153-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5c153-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c153-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c153-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c153-112">`true` es si y solo si `a` es mayor que o es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="5c153-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c153-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c153-113">Remarks</span></span>

<span data-ttu-id="5c153-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5c153-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```