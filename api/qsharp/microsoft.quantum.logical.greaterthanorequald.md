---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726645"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="f6a29-102">GreaterThanOrEqualD función)</span><span class="sxs-lookup"><span data-stu-id="f6a29-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="f6a29-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f6a29-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f6a29-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6a29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6a29-105">Devuelve true si y solo si un número es mayor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="f6a29-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f6a29-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f6a29-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f6a29-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6a29-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6a29-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="f6a29-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f6a29-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6a29-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6a29-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="f6a29-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f6a29-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6a29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6a29-112">`true` es si y solo si `a` es mayor que o es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="f6a29-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6a29-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f6a29-113">Remarks</span></span>

<span data-ttu-id="f6a29-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f6a29-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```