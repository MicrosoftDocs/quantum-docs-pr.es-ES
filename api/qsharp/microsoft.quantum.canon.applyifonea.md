---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operación ApplyIfOneA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729525"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="e342b-102">Operación ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="e342b-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="e342b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e342b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e342b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e342b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e342b-105">Aplica una operación adjointable condicionada en un valor de resultado clásico a uno.</span><span class="sxs-lookup"><span data-stu-id="e342b-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="e342b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e342b-106">Description</span></span>

<span data-ttu-id="e342b-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` .</span><span class="sxs-lookup"><span data-stu-id="e342b-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="e342b-108">Si es `Zero` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="e342b-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e342b-109">El sufijo `A` indica que la operación que se va a aplicar es adjointable.</span><span class="sxs-lookup"><span data-stu-id="e342b-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="e342b-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="e342b-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e342b-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="e342b-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e342b-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="e342b-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="e342b-113">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e342b-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e342b-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="e342b-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e342b-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="e342b-115">target : 'T</span></span>

<span data-ttu-id="e342b-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="e342b-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e342b-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e342b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e342b-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e342b-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e342b-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="e342b-119">'T</span></span>

<span data-ttu-id="e342b-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="e342b-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e342b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e342b-121">See Also</span></span>

- [<span data-ttu-id="e342b-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="e342b-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="e342b-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="e342b-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="e342b-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="e342b-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)