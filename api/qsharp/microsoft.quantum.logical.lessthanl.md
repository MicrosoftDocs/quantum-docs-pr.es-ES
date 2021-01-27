---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849145"
---
# <a name="lessthanl-function"></a><span data-ttu-id="a66ae-102">LessThanL función)</span><span class="sxs-lookup"><span data-stu-id="a66ae-102">LessThanL function</span></span>

<span data-ttu-id="a66ae-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a66ae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a66ae-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a66ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a66ae-105">Devuelve true si y solo si un número es menor que otro número.</span><span class="sxs-lookup"><span data-stu-id="a66ae-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a66ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a66ae-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a66ae-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a66ae-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a66ae-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a66ae-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a66ae-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a66ae-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a66ae-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a66ae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a66ae-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a66ae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a66ae-112">`true` es si y solo si `a` es estrictamente menor que `b` .</span><span class="sxs-lookup"><span data-stu-id="a66ae-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a66ae-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a66ae-113">Remarks</span></span>

<span data-ttu-id="a66ae-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a66ae-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```