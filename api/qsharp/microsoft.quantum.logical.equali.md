---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUALI (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816745"
---
# <a name="equali-function"></a><span data-ttu-id="99941-102">EQUALI (función)</span><span class="sxs-lookup"><span data-stu-id="99941-102">EqualI function</span></span>

<span data-ttu-id="99941-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="99941-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="99941-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99941-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99941-105">Devuelve true si y solo si dos entradas son iguales.</span><span class="sxs-lookup"><span data-stu-id="99941-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="99941-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="99941-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="99941-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99941-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99941-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="99941-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="99941-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99941-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99941-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="99941-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="99941-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="99941-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="99941-112">`true` Si y solo si `a` es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="99941-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="99941-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99941-113">Remarks</span></span>

<span data-ttu-id="99941-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="99941-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```