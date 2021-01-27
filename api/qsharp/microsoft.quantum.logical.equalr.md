---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815969"
---
# <a name="equalr-function"></a><span data-ttu-id="372f1-102">Equalr (función)</span><span class="sxs-lookup"><span data-stu-id="372f1-102">EqualR function</span></span>

<span data-ttu-id="372f1-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="372f1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="372f1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="372f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="372f1-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="372f1-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="372f1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="372f1-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="372f1-107">r: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="372f1-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="372f1-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="372f1-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="372f1-109">b: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="372f1-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="372f1-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="372f1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="372f1-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="372f1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="372f1-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="372f1-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="372f1-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="372f1-113">Remarks</span></span>

<span data-ttu-id="372f1-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="372f1-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```