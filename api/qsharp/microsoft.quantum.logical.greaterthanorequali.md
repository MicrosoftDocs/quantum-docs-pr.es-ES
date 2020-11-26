---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197796"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="3857e-102">GreaterThanOrEqualI función)</span><span class="sxs-lookup"><span data-stu-id="3857e-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="3857e-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3857e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3857e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3857e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3857e-105">Devuelve true si y solo si un número es mayor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="3857e-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="3857e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3857e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3857e-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3857e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3857e-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3857e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="3857e-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3857e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3857e-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3857e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3857e-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3857e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3857e-112">`true` es si y solo si `a` es mayor que o es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="3857e-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3857e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3857e-113">Remarks</span></span>

<span data-ttu-id="3857e-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3857e-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```