---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725967"
---
# <a name="notequalr-function"></a><span data-ttu-id="1ddd1-102">NotEqualR función)</span><span class="sxs-lookup"><span data-stu-id="1ddd1-102">NotEqualR function</span></span>

<span data-ttu-id="1ddd1-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1ddd1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1ddd1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ddd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ddd1-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="1ddd1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ddd1-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="1ddd1-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="1ddd1-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="1ddd1-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="1ddd1-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="1ddd1-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="1ddd1-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1ddd1-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1ddd1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1ddd1-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="1ddd1-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ddd1-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ddd1-113">Remarks</span></span>

<span data-ttu-id="1ddd1-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1ddd1-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```