---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204596"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="df363-102">UncurriedOpC función)</span><span class="sxs-lookup"><span data-stu-id="df363-102">UncurriedOpC function</span></span>

<span data-ttu-id="df363-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df363-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df363-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df363-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df363-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="df363-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="df363-106">El modificador `C` indica que las operaciones se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="df363-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="df363-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="df363-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="df363-108">curriedOp: ' U = > [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es CTL</span><span class="sxs-lookup"><span data-stu-id="df363-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="df363-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="df363-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="df363-110">Salida: (' t, ' U) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="df363-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="df363-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="df363-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df363-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="df363-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df363-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="df363-113">'T</span></span>

<span data-ttu-id="df363-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="df363-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="df363-115">' U</span><span class="sxs-lookup"><span data-stu-id="df363-115">'U</span></span>

<span data-ttu-id="df363-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="df363-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="df363-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df363-117">See Also</span></span>

- [<span data-ttu-id="df363-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="df363-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)