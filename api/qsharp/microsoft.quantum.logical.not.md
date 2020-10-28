---
uid: Microsoft.Quantum.Logical.Not
title: Not (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725997"
---
# <a name="not-function"></a><span data-ttu-id="64b6a-102">Not (función)</span><span class="sxs-lookup"><span data-stu-id="64b6a-102">Not function</span></span>

<span data-ttu-id="64b6a-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="64b6a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="64b6a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64b6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64b6a-105">Devuelve la negación booleana de un valor.</span><span class="sxs-lookup"><span data-stu-id="64b6a-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="64b6a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="64b6a-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="64b6a-107">valor: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64b6a-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64b6a-108">Valor que se va a negar.</span><span class="sxs-lookup"><span data-stu-id="64b6a-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="64b6a-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64b6a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64b6a-110">`true` Si y solo si `value` es `false` .</span><span class="sxs-lookup"><span data-stu-id="64b6a-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="64b6a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64b6a-111">Remarks</span></span>

<span data-ttu-id="64b6a-112">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="64b6a-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```