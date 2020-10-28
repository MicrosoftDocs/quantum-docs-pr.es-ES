---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728720"
---
# <a name="delayedc-function"></a><span data-ttu-id="c4793-102">DelayedC función)</span><span class="sxs-lookup"><span data-stu-id="c4793-102">DelayedC function</span></span>

<span data-ttu-id="c4793-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4793-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4793-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4793-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4793-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="c4793-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c4793-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4793-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c4793-107">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4793-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4793-108">Operación que se va a aplicar como resultado de aplicar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c4793-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="c4793-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="c4793-109">arg : 'T</span></span>

<span data-ttu-id="c4793-110">Entrada a la que `op` se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="c4793-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="c4793-111">Salida: [Unit](xref:microsoft.quantum.lang-ref.unit) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad</span><span class="sxs-lookup"><span data-stu-id="c4793-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4793-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="c4793-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4793-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c4793-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4793-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="c4793-114">'T</span></span>

<span data-ttu-id="c4793-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="c4793-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4793-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4793-116">See Also</span></span>

- [<span data-ttu-id="c4793-117">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="c4793-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="c4793-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="c4793-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)