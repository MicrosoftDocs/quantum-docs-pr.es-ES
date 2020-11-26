---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197813"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="9ae5d-102">GreaterThanOrEqualD función)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="9ae5d-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9ae5d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ae5d-105">Devuelve true si y solo si un número es mayor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="9ae5d-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="9ae5d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9ae5d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="9ae5d-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ae5d-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9ae5d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="9ae5d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ae5d-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9ae5d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9ae5d-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9ae5d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9ae5d-112">`true` es si y solo si `a` es mayor que o es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="9ae5d-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ae5d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ae5d-113">Remarks</span></span>

<span data-ttu-id="9ae5d-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9ae5d-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```