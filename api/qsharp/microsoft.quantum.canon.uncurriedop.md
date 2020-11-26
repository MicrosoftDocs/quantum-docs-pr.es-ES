---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204647"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="84aed-102">UncurriedOp función)</span><span class="sxs-lookup"><span data-stu-id="84aed-102">UncurriedOp function</span></span>

<span data-ttu-id="84aed-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84aed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84aed-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84aed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84aed-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="84aed-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="84aed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="84aed-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="84aed-107">curriedOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > de></span><span class="sxs-lookup"><span data-stu-id="84aed-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="84aed-108">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="84aed-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="84aed-109">Salida: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="84aed-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="84aed-110">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="84aed-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84aed-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="84aed-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84aed-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="84aed-112">'T</span></span>

<span data-ttu-id="84aed-113">El tipo de la primera entrada a una operación currificada.</span><span class="sxs-lookup"><span data-stu-id="84aed-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="84aed-114">' U</span><span class="sxs-lookup"><span data-stu-id="84aed-114">'U</span></span>

<span data-ttu-id="84aed-115">Tipo de la segunda entrada a una operación currificada.</span><span class="sxs-lookup"><span data-stu-id="84aed-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="84aed-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84aed-116">See Also</span></span>

- [<span data-ttu-id="84aed-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="84aed-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="84aed-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="84aed-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="84aed-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="84aed-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)