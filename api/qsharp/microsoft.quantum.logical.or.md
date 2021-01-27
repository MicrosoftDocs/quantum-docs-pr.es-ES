---
uid: Microsoft.Quantum.Logical.Or
title: Función or
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848474"
---
# <a name="or-function"></a><span data-ttu-id="fd379-102">Función or</span><span class="sxs-lookup"><span data-stu-id="fd379-102">Or function</span></span>

<span data-ttu-id="fd379-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fd379-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fd379-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd379-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd379-105">Devuelve la disyunción booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="fd379-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fd379-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fd379-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fd379-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd379-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd379-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="fd379-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fd379-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd379-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd379-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="fd379-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fd379-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd379-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd379-112">`true` es si y solo si `a` o `b` son `true` .</span><span class="sxs-lookup"><span data-stu-id="fd379-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd379-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd379-113">Remarks</span></span>

<span data-ttu-id="fd379-114">A diferencia del `or` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="fd379-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fd379-115">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fd379-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```