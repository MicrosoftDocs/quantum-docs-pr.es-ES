---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852003"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="4ac23-102">UncurriedOp función)</span><span class="sxs-lookup"><span data-stu-id="4ac23-102">UncurriedOp function</span></span>

<span data-ttu-id="4ac23-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4ac23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4ac23-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ac23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ac23-105">Dada una función que devuelve operaciones, devuelve una nueva operación que toma ambas entradas como una tupla.</span><span class="sxs-lookup"><span data-stu-id="4ac23-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="4ac23-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4ac23-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="4ac23-107">curriedOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > de></span><span class="sxs-lookup"><span data-stu-id="4ac23-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4ac23-108">Función que devuelve las operaciones.</span><span class="sxs-lookup"><span data-stu-id="4ac23-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="4ac23-109">Salida: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4ac23-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4ac23-110">Una nueva operación `op` , como `op(t, u)` es equivalente a `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="4ac23-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4ac23-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4ac23-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4ac23-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="4ac23-112">'T</span></span>

<span data-ttu-id="4ac23-113">El tipo de la primera entrada a una operación currificada.</span><span class="sxs-lookup"><span data-stu-id="4ac23-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="4ac23-114">' U</span><span class="sxs-lookup"><span data-stu-id="4ac23-114">'U</span></span>

<span data-ttu-id="4ac23-115">Tipo de la segunda entrada a una operación currificada.</span><span class="sxs-lookup"><span data-stu-id="4ac23-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ac23-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ac23-116">See Also</span></span>

- [<span data-ttu-id="4ac23-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="4ac23-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="4ac23-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="4ac23-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="4ac23-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="4ac23-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)