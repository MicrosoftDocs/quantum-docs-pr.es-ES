---
uid: Microsoft.Quantum.Logical.EqualD
title: Función igual
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816870"
---
# <a name="equald-function"></a><span data-ttu-id="65eb6-102">Función igual</span><span class="sxs-lookup"><span data-stu-id="65eb6-102">EqualD function</span></span>

<span data-ttu-id="65eb6-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="65eb6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="65eb6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65eb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65eb6-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="65eb6-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="65eb6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="65eb6-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="65eb6-107">r: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="65eb6-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="65eb6-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="65eb6-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="65eb6-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="65eb6-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="65eb6-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="65eb6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="65eb6-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="65eb6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="65eb6-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="65eb6-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="65eb6-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65eb6-113">Remarks</span></span>

<span data-ttu-id="65eb6-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="65eb6-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```