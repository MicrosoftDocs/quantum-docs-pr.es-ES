---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840035"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="5e8dc-102">UncurriedOpCA función)</span><span class="sxs-lookup"><span data-stu-id="5e8dc-102">UncurriedOpCA function</span></span>

<span data-ttu-id="5e8dc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e8dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e8dc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e8dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e8dc-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="5e8dc-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="5e8dc-106">El modificador `CA` indica que las operaciones se pueden controlar y adjointable.</span><span class="sxs-lookup"><span data-stu-id="5e8dc-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="5e8dc-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5e8dc-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="5e8dc-108">curriedOp: ' U = la [unidad](xref:microsoft.quantum.lang-ref.unit)  > de> es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5e8dc-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5e8dc-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="5e8dc-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="5e8dc-110">Output: (' t, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5e8dc-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5e8dc-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="5e8dc-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5e8dc-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="5e8dc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e8dc-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="5e8dc-113">'T</span></span>

<span data-ttu-id="5e8dc-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="5e8dc-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="5e8dc-115">' U</span><span class="sxs-lookup"><span data-stu-id="5e8dc-115">'U</span></span>

<span data-ttu-id="5e8dc-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="5e8dc-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e8dc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e8dc-117">See Also</span></span>

- [<span data-ttu-id="5e8dc-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="5e8dc-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)