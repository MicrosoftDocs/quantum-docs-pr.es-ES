---
uid: Microsoft.Quantum.Logical.Not
title: Not (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849087"
---
# <a name="not-function"></a><span data-ttu-id="c934a-102">Not (función)</span><span class="sxs-lookup"><span data-stu-id="c934a-102">Not function</span></span>

<span data-ttu-id="c934a-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c934a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c934a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c934a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c934a-105">Devuelve la negación booleana de un valor.</span><span class="sxs-lookup"><span data-stu-id="c934a-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c934a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c934a-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="c934a-107">valor: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c934a-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c934a-108">Valor que se va a negar.</span><span class="sxs-lookup"><span data-stu-id="c934a-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c934a-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c934a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c934a-110">`true` Si y solo si `value` es `false` .</span><span class="sxs-lookup"><span data-stu-id="c934a-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c934a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c934a-111">Remarks</span></span>

<span data-ttu-id="c934a-112">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c934a-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```