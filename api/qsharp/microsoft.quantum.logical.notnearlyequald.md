---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731253"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="fe5c3-102">NotNearlyEqualD función)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="fe5c3-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fe5c3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe5c3-105">Devuelve true si y solo si dos entradas no son casi iguales (es decir, no se encuentran dentro de una tolerancia de 1E-12).</span><span class="sxs-lookup"><span data-stu-id="fe5c3-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="fe5c3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fe5c3-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="fe5c3-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe5c3-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="fe5c3-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="fe5c3-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe5c3-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="fe5c3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe5c3-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe5c3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe5c3-112">`true` Si y solo si `a` no es casi igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="fe5c3-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe5c3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe5c3-113">Remarks</span></span>

<span data-ttu-id="fe5c3-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fe5c3-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```