---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731292"
---
# <a name="equalb-function"></a><span data-ttu-id="5c5cd-102">EqualB función)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-102">EqualB function</span></span>

<span data-ttu-id="5c5cd-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c5cd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c5cd-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5c5cd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5c5cd-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5c5cd-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c5cd-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5c5cd-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c5cd-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c5cd-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c5cd-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="5c5cd-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c5cd-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c5cd-113">Remarks</span></span>

<span data-ttu-id="5c5cd-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5c5cd-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```