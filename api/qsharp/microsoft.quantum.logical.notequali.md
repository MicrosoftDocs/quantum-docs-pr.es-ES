---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814504"
---
# <a name="notequali-function"></a><span data-ttu-id="36701-102">NotEqualI función)</span><span class="sxs-lookup"><span data-stu-id="36701-102">NotEqualI function</span></span>

<span data-ttu-id="36701-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="36701-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="36701-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36701-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36701-105">Devuelve true si y solo si dos entradas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="36701-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="36701-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="36701-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="36701-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36701-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36701-108">Primer valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="36701-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="36701-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36701-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36701-110">Segundo valor que se va a comparar.</span><span class="sxs-lookup"><span data-stu-id="36701-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="36701-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="36701-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="36701-112">`true` Si y solo si `a` no es igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="36701-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36701-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36701-113">Remarks</span></span>

<span data-ttu-id="36701-114">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="36701-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```