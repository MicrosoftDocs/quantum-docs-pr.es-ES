---
uid: Microsoft.Quantum.Logical.And
title: And (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849239"
---
# <a name="and-function"></a><span data-ttu-id="2be80-102">And (función)</span><span class="sxs-lookup"><span data-stu-id="2be80-102">And function</span></span>

<span data-ttu-id="2be80-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2be80-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2be80-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2be80-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2be80-105">Devuelve la conjunción booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="2be80-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="2be80-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2be80-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="2be80-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2be80-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2be80-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="2be80-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="2be80-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2be80-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2be80-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="2be80-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2be80-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2be80-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2be80-112">`true` es si y solo si `a` y `b` son ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="2be80-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2be80-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2be80-113">Remarks</span></span>

<span data-ttu-id="2be80-114">A diferencia del `and` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="2be80-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="2be80-115">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="2be80-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```