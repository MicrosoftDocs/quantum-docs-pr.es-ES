---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849135"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="f7b6d-102">LessThanOrEqualD función)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="f7b6d-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f7b6d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7b6d-105">Devuelve true si y solo si un número es menor o igual que otro número.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f7b6d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f7b6d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f7b6d-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f7b6d-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f7b6d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f7b6d-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f7b6d-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f7b6d-112">`true` es si y solo si `a` es menor o igual que `b` .</span><span class="sxs-lookup"><span data-stu-id="f7b6d-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7b6d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f7b6d-113">Remarks</span></span>

<span data-ttu-id="f7b6d-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f7b6d-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```