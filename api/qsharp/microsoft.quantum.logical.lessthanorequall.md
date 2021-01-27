---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849109"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="26b56-102">LessThanOrEqualL función)</span><span class="sxs-lookup"><span data-stu-id="26b56-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="26b56-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26b56-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26b56-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26b56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26b56-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="26b56-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="26b56-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="26b56-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="26b56-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26b56-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26b56-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="26b56-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="26b56-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26b56-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26b56-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="26b56-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26b56-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26b56-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26b56-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="26b56-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26b56-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26b56-113">Remarks</span></span>

<span data-ttu-id="26b56-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="26b56-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```