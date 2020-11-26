---
uid: Microsoft.Quantum.Logical.Or
title: Función or
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197133"
---
# <a name="or-function"></a><span data-ttu-id="15f78-102">Función or</span><span class="sxs-lookup"><span data-stu-id="15f78-102">Or function</span></span>

<span data-ttu-id="15f78-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="15f78-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="15f78-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15f78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15f78-105">Devuelve la disyunción booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="15f78-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="15f78-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="15f78-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="15f78-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="15f78-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="15f78-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="15f78-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="15f78-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="15f78-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="15f78-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="15f78-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="15f78-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="15f78-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="15f78-112">`true` es si y solo si `a` o `b` son `true` .</span><span class="sxs-lookup"><span data-stu-id="15f78-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="15f78-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15f78-113">Remarks</span></span>

<span data-ttu-id="15f78-114">A diferencia del `or` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="15f78-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="15f78-115">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="15f78-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```