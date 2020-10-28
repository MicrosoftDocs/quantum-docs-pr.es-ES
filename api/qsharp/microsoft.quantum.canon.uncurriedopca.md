---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728288"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="bfe75-102">UncurriedOpCA función)</span><span class="sxs-lookup"><span data-stu-id="bfe75-102">UncurriedOpCA function</span></span>

<span data-ttu-id="bfe75-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfe75-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfe75-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfe75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfe75-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="bfe75-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="bfe75-106">El modificador `CA` indica que las operaciones se pueden controlar y adjointable.</span><span class="sxs-lookup"><span data-stu-id="bfe75-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="bfe75-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bfe75-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="bfe75-108">curriedOp: ' t-> ' U => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="bfe75-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="bfe75-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="bfe75-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="bfe75-110">Salida: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="bfe75-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="bfe75-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="bfe75-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bfe75-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bfe75-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfe75-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="bfe75-113">'T</span></span>

<span data-ttu-id="bfe75-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="bfe75-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="bfe75-115">' U</span><span class="sxs-lookup"><span data-stu-id="bfe75-115">'U</span></span>

<span data-ttu-id="bfe75-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="bfe75-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe75-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bfe75-117">See Also</span></span>

- [<span data-ttu-id="bfe75-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="bfe75-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)