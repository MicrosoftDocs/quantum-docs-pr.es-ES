---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197235"
---
# <a name="notequall-function"></a><span data-ttu-id="05382-102">NotEqualL función)</span><span class="sxs-lookup"><span data-stu-id="05382-102">NotEqualL function</span></span>

<span data-ttu-id="05382-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="05382-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="05382-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05382-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05382-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="05382-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="05382-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="05382-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="05382-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="05382-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="05382-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="05382-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="05382-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="05382-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="05382-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="05382-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="05382-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="05382-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="05382-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="05382-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="05382-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05382-113">Remarks</span></span>

<span data-ttu-id="05382-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="05382-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```