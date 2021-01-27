---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848498"
---
# <a name="notequalr-function"></a><span data-ttu-id="d24f3-102">NotEqualR función)</span><span class="sxs-lookup"><span data-stu-id="d24f3-102">NotEqualR function</span></span>

<span data-ttu-id="d24f3-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d24f3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d24f3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d24f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d24f3-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="d24f3-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d24f3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d24f3-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="d24f3-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="d24f3-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="d24f3-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="d24f3-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="d24f3-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="d24f3-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="d24f3-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="d24f3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d24f3-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d24f3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d24f3-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="d24f3-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d24f3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d24f3-113">Remarks</span></span>

<span data-ttu-id="d24f3-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="d24f3-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```