---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728289"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="9bc65-102">UncurriedOpC función)</span><span class="sxs-lookup"><span data-stu-id="9bc65-102">UncurriedOpC function</span></span>

<span data-ttu-id="9bc65-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9bc65-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9bc65-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9bc65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9bc65-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="9bc65-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="9bc65-106">El modificador `C` indica que las operaciones se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="9bc65-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="9bc65-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9bc65-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="9bc65-108">curriedOp: ' U = > ' U => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="9bc65-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9bc65-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="9bc65-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="9bc65-110">Salida: (' t, ' U) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bc65-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9bc65-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="9bc65-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9bc65-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9bc65-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9bc65-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="9bc65-113">'T</span></span>

<span data-ttu-id="9bc65-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="9bc65-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="9bc65-115">' U</span><span class="sxs-lookup"><span data-stu-id="9bc65-115">'U</span></span>

<span data-ttu-id="9bc65-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="9bc65-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bc65-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bc65-117">See Also</span></span>

- [<span data-ttu-id="9bc65-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="9bc65-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)