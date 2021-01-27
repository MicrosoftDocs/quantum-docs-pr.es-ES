---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851985"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="b86ce-102">UncurriedOpC función)</span><span class="sxs-lookup"><span data-stu-id="b86ce-102">UncurriedOpC function</span></span>

<span data-ttu-id="b86ce-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b86ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b86ce-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b86ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b86ce-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="b86ce-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="b86ce-106">El modificador `C` indica que las operaciones se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="b86ce-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b86ce-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b86ce-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="b86ce-108">curriedOp: ' U = > [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es CTL</span><span class="sxs-lookup"><span data-stu-id="b86ce-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b86ce-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="b86ce-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="b86ce-110">Salida: (' t, ' U) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="b86ce-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b86ce-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="b86ce-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b86ce-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b86ce-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b86ce-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="b86ce-113">'T</span></span>

<span data-ttu-id="b86ce-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="b86ce-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="b86ce-115">' U</span><span class="sxs-lookup"><span data-stu-id="b86ce-115">'U</span></span>

<span data-ttu-id="b86ce-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="b86ce-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="b86ce-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b86ce-117">See Also</span></span>

- [<span data-ttu-id="b86ce-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="b86ce-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)