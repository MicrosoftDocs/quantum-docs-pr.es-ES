---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726069"
---
# <a name="equalr-function"></a><span data-ttu-id="9b372-102">Equalr (función)</span><span class="sxs-lookup"><span data-stu-id="9b372-102">EqualR function</span></span>

<span data-ttu-id="9b372-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9b372-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9b372-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b372-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b372-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="9b372-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="9b372-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9b372-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="9b372-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="9b372-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="9b372-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9b372-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="9b372-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="9b372-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="9b372-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="9b372-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9b372-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9b372-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9b372-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="9b372-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b372-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b372-113">Remarks</span></span>

<span data-ttu-id="9b372-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9b372-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```