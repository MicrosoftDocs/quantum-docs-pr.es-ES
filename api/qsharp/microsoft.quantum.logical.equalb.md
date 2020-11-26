---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198476"
---
# <a name="equalb-function"></a><span data-ttu-id="82435-102">EqualB función)</span><span class="sxs-lookup"><span data-stu-id="82435-102">EqualB function</span></span>

<span data-ttu-id="82435-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="82435-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="82435-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82435-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82435-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="82435-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="82435-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="82435-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="82435-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82435-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82435-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="82435-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="82435-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82435-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82435-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="82435-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="82435-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82435-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82435-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="82435-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="82435-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82435-113">Remarks</span></span>

<span data-ttu-id="82435-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="82435-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```