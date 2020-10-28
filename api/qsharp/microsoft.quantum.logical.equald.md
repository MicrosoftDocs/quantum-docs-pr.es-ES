---
uid: Microsoft.Quantum.Logical.EqualD
title: Función igual
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726656"
---
# <a name="equald-function"></a><span data-ttu-id="776b1-102">Función igual</span><span class="sxs-lookup"><span data-stu-id="776b1-102">EqualD function</span></span>

<span data-ttu-id="776b1-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="776b1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="776b1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="776b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="776b1-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="776b1-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="776b1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="776b1-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="776b1-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="776b1-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="776b1-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="776b1-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="776b1-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="776b1-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="776b1-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="776b1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="776b1-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="776b1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="776b1-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="776b1-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="776b1-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="776b1-113">Remarks</span></span>

<span data-ttu-id="776b1-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="776b1-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```