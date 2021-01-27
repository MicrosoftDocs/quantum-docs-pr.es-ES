---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840048"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="8052a-102">UncurriedOpA función)</span><span class="sxs-lookup"><span data-stu-id="8052a-102">UncurriedOpA function</span></span>

<span data-ttu-id="8052a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8052a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8052a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8052a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8052a-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="8052a-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8052a-106">El modificador `A` indica que las operaciones son adjointable.</span><span class="sxs-lookup"><span data-stu-id="8052a-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8052a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8052a-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="8052a-108">curriedOp: ' t-> ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es ADJ</span><span class="sxs-lookup"><span data-stu-id="8052a-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8052a-109">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="8052a-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="8052a-110">Salida: (' t, ' U) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="8052a-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8052a-111">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="8052a-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8052a-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8052a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8052a-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="8052a-113">'T</span></span>

<span data-ttu-id="8052a-114">Tipo del primer argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="8052a-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8052a-115">' U</span><span class="sxs-lookup"><span data-stu-id="8052a-115">'U</span></span>

<span data-ttu-id="8052a-116">Tipo del segundo argumento de una función currificada.</span><span class="sxs-lookup"><span data-stu-id="8052a-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8052a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8052a-117">See Also</span></span>

- [<span data-ttu-id="8052a-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="8052a-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)