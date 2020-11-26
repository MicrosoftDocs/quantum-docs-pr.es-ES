---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198034"
---
# <a name="greaterthand-function"></a><span data-ttu-id="6338b-102">GreaterThanD función)</span><span class="sxs-lookup"><span data-stu-id="6338b-102">GreaterThanD function</span></span>

<span data-ttu-id="6338b-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6338b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6338b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6338b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6338b-105">Devuelve true si y solo si un número es mayor que otro número.</span><span class="sxs-lookup"><span data-stu-id="6338b-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6338b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6338b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6338b-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6338b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6338b-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="6338b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6338b-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6338b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6338b-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="6338b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6338b-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6338b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6338b-112">`true` es si y solo si `a` es estrictamente mayor que `b` .</span><span class="sxs-lookup"><span data-stu-id="6338b-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6338b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6338b-113">Remarks</span></span>

<span data-ttu-id="6338b-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6338b-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```