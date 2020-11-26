---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207024"
---
# <a name="delayedca-function"></a><span data-ttu-id="ab548-102">DelayedCA función)</span><span class="sxs-lookup"><span data-stu-id="ab548-102">DelayedCA function</span></span>

<span data-ttu-id="ab548-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab548-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab548-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab548-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab548-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="ab548-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="ab548-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ab548-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ab548-107">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ab548-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ab548-108">Operación que se va a aplicar como resultado de aplicar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ab548-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="ab548-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="ab548-109">arg : 'T</span></span>

<span data-ttu-id="ab548-110">Entrada a la que `op` se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="ab548-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="ab548-111">Salida: [Unit](xref:microsoft.quantum.lang-ref.unit) => [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ab548-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ab548-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="ab548-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ab548-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ab548-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab548-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="ab548-114">'T</span></span>

<span data-ttu-id="ab548-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="ab548-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab548-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab548-116">See Also</span></span>

- [<span data-ttu-id="ab548-117">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="ab548-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="ab548-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="ab548-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)