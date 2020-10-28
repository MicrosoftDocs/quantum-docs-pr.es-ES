---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725985"
---
# <a name="notequalb-function"></a><span data-ttu-id="250bc-102">NotEqualB función)</span><span class="sxs-lookup"><span data-stu-id="250bc-102">NotEqualB function</span></span>

<span data-ttu-id="250bc-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="250bc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="250bc-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="250bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="250bc-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="250bc-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="250bc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="250bc-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="250bc-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="250bc-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="250bc-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="250bc-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="250bc-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="250bc-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="250bc-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="250bc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="250bc-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="250bc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="250bc-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="250bc-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="250bc-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="250bc-113">Remarks</span></span>

<span data-ttu-id="250bc-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="250bc-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```