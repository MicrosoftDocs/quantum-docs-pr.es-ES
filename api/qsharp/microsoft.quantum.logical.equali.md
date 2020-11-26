---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUALI (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198170"
---
# <a name="equali-function"></a><span data-ttu-id="63163-102">EQUALI (función)</span><span class="sxs-lookup"><span data-stu-id="63163-102">EqualI function</span></span>

<span data-ttu-id="63163-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="63163-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="63163-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63163-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63163-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="63163-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="63163-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="63163-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="63163-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63163-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63163-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="63163-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="63163-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63163-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63163-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="63163-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="63163-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63163-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63163-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="63163-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="63163-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63163-113">Remarks</span></span>

<span data-ttu-id="63163-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="63163-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```