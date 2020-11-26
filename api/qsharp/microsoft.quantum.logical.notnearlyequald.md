---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 23229b1630982eba4485330cc2290aed733c4d86
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197150"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="04506-102">NotNearlyEqualD función)</span><span class="sxs-lookup"><span data-stu-id="04506-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="04506-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="04506-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="04506-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04506-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04506-105">Devuelve true si y solo si dos entradas no son casi iguales (es decir, no se encuentran dentro de una tolerancia de 1E-12).</span><span class="sxs-lookup"><span data-stu-id="04506-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="04506-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="04506-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="04506-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04506-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04506-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="04506-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="04506-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04506-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04506-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="04506-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="04506-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="04506-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="04506-112">`true` Si y solo si `a` no es casi igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="04506-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="04506-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04506-113">Remarks</span></span>

<span data-ttu-id="04506-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="04506-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```