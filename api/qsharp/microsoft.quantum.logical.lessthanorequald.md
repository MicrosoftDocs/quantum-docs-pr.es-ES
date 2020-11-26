---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197643"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="97a88-102">LessThanOrEqualD función)</span><span class="sxs-lookup"><span data-stu-id="97a88-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="97a88-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="97a88-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="97a88-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97a88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97a88-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="97a88-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="97a88-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="97a88-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="97a88-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97a88-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97a88-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="97a88-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="97a88-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97a88-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97a88-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="97a88-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="97a88-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="97a88-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="97a88-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="97a88-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="97a88-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="97a88-113">Remarks</span></span>

<span data-ttu-id="97a88-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="97a88-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```