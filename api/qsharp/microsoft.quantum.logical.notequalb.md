---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814419"
---
# <a name="notequalb-function"></a><span data-ttu-id="132e7-102">NotEqualB función)</span><span class="sxs-lookup"><span data-stu-id="132e7-102">NotEqualB function</span></span>

<span data-ttu-id="132e7-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="132e7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="132e7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="132e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="132e7-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="132e7-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="132e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="132e7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="132e7-107">r: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="132e7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="132e7-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="132e7-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="132e7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="132e7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="132e7-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="132e7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="132e7-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="132e7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="132e7-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="132e7-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="132e7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="132e7-113">Remarks</span></span>

<span data-ttu-id="132e7-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="132e7-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```