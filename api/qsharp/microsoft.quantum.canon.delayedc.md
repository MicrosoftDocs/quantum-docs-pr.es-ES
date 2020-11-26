---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207025"
---
# <a name="delayedc-function"></a><span data-ttu-id="cb71a-102">DelayedC función)</span><span class="sxs-lookup"><span data-stu-id="cb71a-102">DelayedC function</span></span>

<span data-ttu-id="cb71a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb71a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb71a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb71a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb71a-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="cb71a-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="cb71a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cb71a-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="cb71a-107">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="cb71a-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cb71a-108">Operación que se va a aplicar como resultado de aplicar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="cb71a-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="cb71a-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="cb71a-109">arg : 'T</span></span>

<span data-ttu-id="cb71a-110">Entrada a la que `op` se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="cb71a-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="cb71a-111">Salida: la unidad de [unidad](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) es CTL</span><span class="sxs-lookup"><span data-stu-id="cb71a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cb71a-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="cb71a-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cb71a-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="cb71a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb71a-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="cb71a-114">'T</span></span>

<span data-ttu-id="cb71a-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="cb71a-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb71a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb71a-116">See Also</span></span>

- [<span data-ttu-id="cb71a-117">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="cb71a-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="cb71a-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="cb71a-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)