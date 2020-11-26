---
uid: Microsoft.Quantum.Canon.Delayed
title: Función retrasada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216462"
---
# <a name="delayed-function"></a><span data-ttu-id="e2a7b-102">Función retrasada</span><span class="sxs-lookup"><span data-stu-id="e2a7b-102">Delayed function</span></span>

<span data-ttu-id="e2a7b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2a7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2a7b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2a7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2a7b-105">Devuelve una operación que aplica la operación dada con el argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="e2a7b-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="e2a7b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e2a7b-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="e2a7b-107">OP: ' t => ' U</span><span class="sxs-lookup"><span data-stu-id="e2a7b-107">op : 'T => 'U</span></span> 

<span data-ttu-id="e2a7b-108">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="e2a7b-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="e2a7b-109">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="e2a7b-109">arg : 'T</span></span>

<span data-ttu-id="e2a7b-110">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="e2a7b-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="e2a7b-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="e2a7b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="e2a7b-112">Una nueva operación que se aplica `op` con la entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="e2a7b-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e2a7b-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e2a7b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2a7b-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="e2a7b-114">'T</span></span>

<span data-ttu-id="e2a7b-115">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="e2a7b-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="e2a7b-116">' U</span><span class="sxs-lookup"><span data-stu-id="e2a7b-116">'U</span></span>

<span data-ttu-id="e2a7b-117">El tipo de valor devuelto de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="e2a7b-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2a7b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2a7b-118">See Also</span></span>

- [<span data-ttu-id="e2a7b-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="e2a7b-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="e2a7b-120">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="e2a7b-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="e2a7b-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="e2a7b-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="e2a7b-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e2a7b-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)