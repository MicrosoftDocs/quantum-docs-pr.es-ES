---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197201"
---
# <a name="notequalr-function"></a><span data-ttu-id="77657-102">NotEqualR función)</span><span class="sxs-lookup"><span data-stu-id="77657-102">NotEqualR function</span></span>

<span data-ttu-id="77657-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="77657-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="77657-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77657-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77657-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="77657-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="77657-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="77657-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="77657-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="77657-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="77657-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="77657-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="77657-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="77657-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="77657-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="77657-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="77657-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="77657-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="77657-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="77657-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="77657-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77657-113">Remarks</span></span>

<span data-ttu-id="77657-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="77657-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```