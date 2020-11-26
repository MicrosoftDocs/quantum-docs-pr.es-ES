---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197983"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="69a04-102">GreaterThanL función)</span><span class="sxs-lookup"><span data-stu-id="69a04-102">GreaterThanL function</span></span>

<span data-ttu-id="69a04-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="69a04-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="69a04-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69a04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69a04-105">Devuelve true si y solo si un número es mayor que otro número.</span><span class="sxs-lookup"><span data-stu-id="69a04-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="69a04-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="69a04-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="69a04-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69a04-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69a04-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="69a04-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="69a04-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69a04-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69a04-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="69a04-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="69a04-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="69a04-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="69a04-112">`true` es si y solo si `a` es estrictamente mayor que `b` .</span><span class="sxs-lookup"><span data-stu-id="69a04-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69a04-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69a04-113">Remarks</span></span>

<span data-ttu-id="69a04-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="69a04-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```