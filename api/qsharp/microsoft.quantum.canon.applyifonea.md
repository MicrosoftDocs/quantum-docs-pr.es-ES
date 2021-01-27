---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operación ApplyIfOneA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844927"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="6b6dc-102">Operación ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="6b6dc-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="6b6dc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b6dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b6dc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b6dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b6dc-105">Aplica una operación adjointable condicionada en un valor de resultado clásico a uno.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="6b6dc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b6dc-106">Description</span></span>

<span data-ttu-id="6b6dc-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` .</span><span class="sxs-lookup"><span data-stu-id="6b6dc-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="6b6dc-108">Si es `Zero` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="6b6dc-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="6b6dc-109">El sufijo `A` indica que la operación que se va a aplicar es adjointable.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="6b6dc-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b6dc-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="6b6dc-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="6b6dc-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="6b6dc-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="6b6dc-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="6b6dc-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6b6dc-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="6b6dc-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="6b6dc-115">target : 'T</span></span>

<span data-ttu-id="6b6dc-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b6dc-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b6dc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b6dc-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6b6dc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b6dc-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="6b6dc-119">'T</span></span>

<span data-ttu-id="6b6dc-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="6b6dc-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b6dc-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b6dc-121">See Also</span></span>

- [<span data-ttu-id="6b6dc-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="6b6dc-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="6b6dc-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="6b6dc-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="6b6dc-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="6b6dc-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)