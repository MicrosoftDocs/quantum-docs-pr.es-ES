---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198013"
---
# <a name="equalr-function"></a><span data-ttu-id="3a017-102">Equalr (función)</span><span class="sxs-lookup"><span data-stu-id="3a017-102">EqualR function</span></span>

<span data-ttu-id="3a017-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3a017-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3a017-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a017-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a017-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="3a017-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3a017-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a017-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="3a017-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="3a017-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="3a017-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3a017-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="3a017-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="3a017-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="3a017-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3a017-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3a017-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3a017-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3a017-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="3a017-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a017-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a017-113">Remarks</span></span>

<span data-ttu-id="3a017-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3a017-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```