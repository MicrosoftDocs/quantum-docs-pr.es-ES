---
uid: Microsoft.Quantum.Canon.DelayedA
title: Función retrasada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728733"
---
# <a name="delayeda-function"></a><span data-ttu-id="dc277-102">Función retrasada</span><span class="sxs-lookup"><span data-stu-id="dc277-102">DelayedA function</span></span>

<span data-ttu-id="dc277-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc277-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc277-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc277-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc277-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="dc277-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="dc277-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dc277-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="dc277-107">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc277-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dc277-108">Operación que se va a aplicar como resultado de aplicar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="dc277-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="dc277-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="dc277-109">arg : 'T</span></span>

<span data-ttu-id="dc277-110">Entrada a la que `op` se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="dc277-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="dc277-111">Salida: [Unit](xref:microsoft.quantum.lang-ref.unit) ajuste de => [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad</span><span class="sxs-lookup"><span data-stu-id="dc277-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dc277-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="dc277-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc277-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dc277-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc277-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="dc277-114">'T</span></span>

<span data-ttu-id="dc277-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="dc277-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc277-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc277-116">See Also</span></span>

- [<span data-ttu-id="dc277-117">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="dc277-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="dc277-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="dc277-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)