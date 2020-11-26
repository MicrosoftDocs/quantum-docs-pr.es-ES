---
uid: Microsoft.Quantum.Logical.EqualL
title: Equall (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198119"
---
# <a name="equall-function"></a><span data-ttu-id="cc4f8-102">Equall (función)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-102">EqualL function</span></span>

<span data-ttu-id="cc4f8-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc4f8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc4f8-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="cc4f8-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cc4f8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc4f8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cc4f8-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc4f8-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="cc4f8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cc4f8-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc4f8-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="cc4f8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc4f8-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc4f8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc4f8-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="cc4f8-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc4f8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc4f8-113">Remarks</span></span>

<span data-ttu-id="cc4f8-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="cc4f8-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```