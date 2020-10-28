---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732917"
---
# <a name="notequald-function"></a><span data-ttu-id="3105f-102">NotEqualD función)</span><span class="sxs-lookup"><span data-stu-id="3105f-102">NotEqualD function</span></span>

<span data-ttu-id="3105f-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3105f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3105f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3105f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3105f-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="3105f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3105f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3105f-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3105f-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3105f-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3105f-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3105f-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3105f-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3105f-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3105f-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="3105f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3105f-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3105f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3105f-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="3105f-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3105f-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3105f-113">Remarks</span></span>

<span data-ttu-id="3105f-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3105f-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```