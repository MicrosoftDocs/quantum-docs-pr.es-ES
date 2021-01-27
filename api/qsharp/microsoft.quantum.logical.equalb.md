---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817251"
---
# <a name="equalb-function"></a><span data-ttu-id="a7d43-102">EqualB función)</span><span class="sxs-lookup"><span data-stu-id="a7d43-102">EqualB function</span></span>

<span data-ttu-id="a7d43-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a7d43-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a7d43-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7d43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7d43-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="a7d43-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a7d43-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7d43-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="a7d43-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7d43-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7d43-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a7d43-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="a7d43-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7d43-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7d43-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="a7d43-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a7d43-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7d43-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7d43-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="a7d43-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7d43-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7d43-113">Remarks</span></span>

<span data-ttu-id="a7d43-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a7d43-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```