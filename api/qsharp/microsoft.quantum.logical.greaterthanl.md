---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849196"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="9927b-102">GreaterThanL función)</span><span class="sxs-lookup"><span data-stu-id="9927b-102">GreaterThanL function</span></span>

<span data-ttu-id="9927b-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9927b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9927b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9927b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9927b-105">Devuelve true si y solo si un número es mayor que otro número.</span><span class="sxs-lookup"><span data-stu-id="9927b-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="9927b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9927b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9927b-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9927b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9927b-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9927b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9927b-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9927b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9927b-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9927b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9927b-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9927b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9927b-112">`true` es si y solo si `a` es estrictamente mayor que `b` .</span><span class="sxs-lookup"><span data-stu-id="9927b-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9927b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9927b-113">Remarks</span></span>

<span data-ttu-id="9927b-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9927b-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```