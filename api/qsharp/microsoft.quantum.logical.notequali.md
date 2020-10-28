---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725984"
---
# <a name="notequali-function"></a><span data-ttu-id="5186a-102">NotEqualI función)</span><span class="sxs-lookup"><span data-stu-id="5186a-102">NotEqualI function</span></span>

<span data-ttu-id="5186a-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5186a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5186a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5186a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5186a-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="5186a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5186a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5186a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5186a-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5186a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5186a-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5186a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5186a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5186a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5186a-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5186a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5186a-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5186a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5186a-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="5186a-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5186a-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5186a-113">Remarks</span></span>

<span data-ttu-id="5186a-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5186a-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```