---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849023"
---
# <a name="notequall-function"></a><span data-ttu-id="48e70-102">NotEqualL función)</span><span class="sxs-lookup"><span data-stu-id="48e70-102">NotEqualL function</span></span>

<span data-ttu-id="48e70-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="48e70-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="48e70-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48e70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48e70-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="48e70-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="48e70-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="48e70-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="48e70-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="48e70-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="48e70-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="48e70-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="48e70-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="48e70-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="48e70-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="48e70-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="48e70-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="48e70-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="48e70-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="48e70-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="48e70-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48e70-113">Remarks</span></span>

<span data-ttu-id="48e70-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="48e70-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```