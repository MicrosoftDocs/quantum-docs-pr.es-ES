---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204630"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="e4ca7-102">UncurriedOpA función)</span><span class="sxs-lookup"><span data-stu-id="e4ca7-102">UncurriedOpA function</span></span>

<span data-ttu-id="e4ca7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4ca7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4ca7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4ca7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4ca7-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="e4ca7-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="e4ca7-106">El modificador `A` indica que las operaciones son adjointable.</span><span class="sxs-lookup"><span data-stu-id="e4ca7-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="e4ca7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e4ca7-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="e4ca7-108">curriedOp: ' t-> ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es ADJ</span><span class="sxs-lookup"><span data-stu-id="e4ca7-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e4ca7-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e4ca7-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="e4ca7-110">Salida: (' t, ' U) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="e4ca7-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e4ca7-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="e4ca7-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e4ca7-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e4ca7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4ca7-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="e4ca7-113">'T</span></span>

<span data-ttu-id="e4ca7-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="e4ca7-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="e4ca7-115">' U</span><span class="sxs-lookup"><span data-stu-id="e4ca7-115">'U</span></span>

<span data-ttu-id="e4ca7-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="e4ca7-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ca7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4ca7-117">See Also</span></span>

- [<span data-ttu-id="e4ca7-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="e4ca7-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)