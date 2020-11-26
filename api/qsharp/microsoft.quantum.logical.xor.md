---
uid: Microsoft.Quantum.Logical.Xor
title: XOR (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197099"
---
# <a name="xor-function"></a><span data-ttu-id="56aea-102">XOR (función)</span><span class="sxs-lookup"><span data-stu-id="56aea-102">Xor function</span></span>

<span data-ttu-id="56aea-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="56aea-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="56aea-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56aea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56aea-105">Devuelve la disyunción exclusiva booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="56aea-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="56aea-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="56aea-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="56aea-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="56aea-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="56aea-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="56aea-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="56aea-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="56aea-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="56aea-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="56aea-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="56aea-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="56aea-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="56aea-112">`true` es si y solo si exactamente uno de `a` y `b` es `true` .</span><span class="sxs-lookup"><span data-stu-id="56aea-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>