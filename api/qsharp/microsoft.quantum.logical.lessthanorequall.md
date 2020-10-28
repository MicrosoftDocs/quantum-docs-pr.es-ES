---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726021"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="a5c13-102">LessThanOrEqualL función)</span><span class="sxs-lookup"><span data-stu-id="a5c13-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="a5c13-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a5c13-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a5c13-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5c13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5c13-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="a5c13-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a5c13-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5c13-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a5c13-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a5c13-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a5c13-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a5c13-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a5c13-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a5c13-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a5c13-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a5c13-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a5c13-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5c13-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a5c13-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="a5c13-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5c13-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5c13-113">Remarks</span></span>

<span data-ttu-id="a5c13-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a5c13-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```