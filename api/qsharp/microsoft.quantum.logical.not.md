---
uid: Microsoft.Quantum.Logical.Not
title: Not (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197456"
---
# <a name="not-function"></a><span data-ttu-id="b0a6d-102">Not (función)</span><span class="sxs-lookup"><span data-stu-id="b0a6d-102">Not function</span></span>

<span data-ttu-id="b0a6d-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b0a6d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b0a6d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0a6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0a6d-105">Devuelve la negación booleana de un valor.</span><span class="sxs-lookup"><span data-stu-id="b0a6d-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="b0a6d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0a6d-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="b0a6d-107">valor: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b0a6d-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b0a6d-108">Valor que se va a negar.</span><span class="sxs-lookup"><span data-stu-id="b0a6d-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b0a6d-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b0a6d-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b0a6d-110">`true` Si y solo si `value` es `false` .</span><span class="sxs-lookup"><span data-stu-id="b0a6d-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0a6d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0a6d-111">Remarks</span></span>

<span data-ttu-id="b0a6d-112">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="b0a6d-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```