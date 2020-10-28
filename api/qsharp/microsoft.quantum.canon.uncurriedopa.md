---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728294"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="01c96-102">UncurriedOpA función)</span><span class="sxs-lookup"><span data-stu-id="01c96-102">UncurriedOpA function</span></span>

<span data-ttu-id="01c96-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01c96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01c96-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01c96-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01c96-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="01c96-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="01c96-106">El modificador `A` indica que las operaciones son adjointable.</span><span class="sxs-lookup"><span data-stu-id="01c96-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="01c96-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="01c96-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="01c96-108">curriedOp: ' U = > ' U => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01c96-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="01c96-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="01c96-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="01c96-110">Salida: (' t, ' U) => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01c96-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="01c96-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="01c96-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01c96-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="01c96-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01c96-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="01c96-113">'T</span></span>

<span data-ttu-id="01c96-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="01c96-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="01c96-115">' U</span><span class="sxs-lookup"><span data-stu-id="01c96-115">'U</span></span>

<span data-ttu-id="01c96-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="01c96-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="01c96-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01c96-117">See Also</span></span>

- [<span data-ttu-id="01c96-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="01c96-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)