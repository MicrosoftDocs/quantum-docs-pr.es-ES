---
uid: Microsoft.Quantum.Logical.Xor
title: XOR (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732813"
---
# <a name="xor-function"></a><span data-ttu-id="b20b2-102">XOR (función)</span><span class="sxs-lookup"><span data-stu-id="b20b2-102">Xor function</span></span>

<span data-ttu-id="b20b2-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b20b2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b20b2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b20b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b20b2-105">Devuelve la disyunción exclusiva booleana de dos valores.</span><span class="sxs-lookup"><span data-stu-id="b20b2-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="b20b2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b20b2-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="b20b2-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b20b2-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b20b2-108">Primer valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="b20b2-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="b20b2-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b20b2-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b20b2-110">Segundo valor que se va a considerar.</span><span class="sxs-lookup"><span data-stu-id="b20b2-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b20b2-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b20b2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b20b2-112">`true` es si y solo si exactamente uno de `a` y `b` es `true` .</span><span class="sxs-lookup"><span data-stu-id="b20b2-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>