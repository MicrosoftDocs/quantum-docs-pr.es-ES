---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726057"
---
# <a name="greaterthand-function"></a><span data-ttu-id="69a22-102">GreaterThanD función)</span><span class="sxs-lookup"><span data-stu-id="69a22-102">GreaterThanD function</span></span>

<span data-ttu-id="69a22-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="69a22-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="69a22-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69a22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69a22-105">Devuelve true si y solo si un número es mayor que otro número.</span><span class="sxs-lookup"><span data-stu-id="69a22-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="69a22-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="69a22-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="69a22-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69a22-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69a22-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="69a22-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="69a22-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69a22-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69a22-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="69a22-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="69a22-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="69a22-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="69a22-112">`true` es si y solo si `a` es estrictamente mayor que `b` .</span><span class="sxs-lookup"><span data-stu-id="69a22-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69a22-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69a22-113">Remarks</span></span>

<span data-ttu-id="69a22-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="69a22-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```