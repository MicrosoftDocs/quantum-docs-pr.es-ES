---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815830"
---
# <a name="lessthani-function"></a><span data-ttu-id="ebbf6-102">LessThanI función)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-102">LessThanI function</span></span>

<span data-ttu-id="ebbf6-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ebbf6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebbf6-105">Devuelve true si y solo si un número es menor que otro número.</span><span class="sxs-lookup"><span data-stu-id="ebbf6-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ebbf6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ebbf6-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ebbf6-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebbf6-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="ebbf6-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ebbf6-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebbf6-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="ebbf6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ebbf6-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ebbf6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ebbf6-112">`true` es si y solo si `a` es estrictamente menor que `b` .</span><span class="sxs-lookup"><span data-stu-id="ebbf6-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebbf6-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ebbf6-113">Remarks</span></span>

<span data-ttu-id="ebbf6-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ebbf6-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```