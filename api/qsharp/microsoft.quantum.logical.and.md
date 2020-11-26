---
uid: Microsoft.Quantum.Logical.And
title: And (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198578"
---
# <a name="and-function"></a><span data-ttu-id="f8349-102">And (función)</span><span class="sxs-lookup"><span data-stu-id="f8349-102">And function</span></span>

<span data-ttu-id="f8349-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f8349-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f8349-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8349-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8349-105">Devuelve la conjunción booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="f8349-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f8349-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8349-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="f8349-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8349-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8349-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="f8349-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="f8349-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8349-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8349-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="f8349-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f8349-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8349-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8349-112">`true` es si y solo si `a` y `b` son ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="f8349-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8349-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8349-113">Remarks</span></span>

<span data-ttu-id="f8349-114">A diferencia del `and` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="f8349-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="f8349-115">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f8349-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```