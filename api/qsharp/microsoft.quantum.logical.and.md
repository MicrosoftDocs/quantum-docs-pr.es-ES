---
uid: Microsoft.Quantum.Logical.And
title: And (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731301"
---
# <a name="and-function"></a><span data-ttu-id="859a7-102">And (función)</span><span class="sxs-lookup"><span data-stu-id="859a7-102">And function</span></span>

<span data-ttu-id="859a7-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="859a7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="859a7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="859a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="859a7-105">Devuelve la conjunción booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="859a7-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="859a7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="859a7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="859a7-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="859a7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="859a7-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="859a7-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="859a7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="859a7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="859a7-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="859a7-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="859a7-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="859a7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="859a7-112">`true` es si y solo si `a` y `b` son ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="859a7-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="859a7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="859a7-113">Remarks</span></span>

<span data-ttu-id="859a7-114">A diferencia del `and` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="859a7-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="859a7-115">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="859a7-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```