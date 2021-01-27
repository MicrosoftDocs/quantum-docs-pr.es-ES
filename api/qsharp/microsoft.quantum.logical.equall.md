---
uid: Microsoft.Quantum.Logical.EqualL
title: Equall (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815987"
---
# <a name="equall-function"></a><span data-ttu-id="12895-102">Equall (función)</span><span class="sxs-lookup"><span data-stu-id="12895-102">EqualL function</span></span>

<span data-ttu-id="12895-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="12895-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="12895-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12895-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12895-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="12895-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="12895-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="12895-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="12895-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12895-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="12895-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="12895-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="12895-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12895-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="12895-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="12895-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="12895-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="12895-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="12895-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="12895-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="12895-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12895-113">Remarks</span></span>

<span data-ttu-id="12895-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="12895-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```