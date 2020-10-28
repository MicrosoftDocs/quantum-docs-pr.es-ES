---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728721"
---
# <a name="delayedca-function"></a><span data-ttu-id="8727d-102">DelayedCA función)</span><span class="sxs-lookup"><span data-stu-id="8727d-102">DelayedCA function</span></span>

<span data-ttu-id="8727d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8727d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8727d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8727d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8727d-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="8727d-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="8727d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8727d-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="8727d-107">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="8727d-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="8727d-108">Operación que se va a aplicar como resultado de aplicar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="8727d-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="8727d-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="8727d-109">arg : 'T</span></span>

<span data-ttu-id="8727d-110">Entrada a la que `op` se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="8727d-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="8727d-111">Salida: [Unit](xref:microsoft.quantum.lang-ref.unit) => [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="8727d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="8727d-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="8727d-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8727d-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8727d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8727d-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="8727d-114">'T</span></span>

<span data-ttu-id="8727d-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="8727d-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8727d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8727d-116">See Also</span></span>

- [<span data-ttu-id="8727d-117">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="8727d-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="8727d-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="8727d-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)