---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Operación ApplyIfElseR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 78c1cf23614fbb7c27122548de487c7350467948
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729554"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="7f3fe-102">Operación ApplyIfElseR</span><span class="sxs-lookup"><span data-stu-id="7f3fe-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="7f3fe-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7f3fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7f3fe-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f3fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f3fe-105">Aplica una de dos operaciones, dependiendo del valor de un resultado clásico.</span><span class="sxs-lookup"><span data-stu-id="7f3fe-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="7f3fe-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f3fe-106">Description</span></span>

<span data-ttu-id="7f3fe-107">Dado un resultado `result` , se aplica la operación `zeroOp` con `zeroInput` como entrada cuando `result` es igual a `Zero` y se aplica `oneOp(oneInput)` cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7f3fe-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="7f3fe-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7f3fe-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7f3fe-109">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="7f3fe-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="7f3fe-110">El resultado de la medida que se usa para determinar si `zeroOp` `oneOp` se aplica o.</span><span class="sxs-lookup"><span data-stu-id="7f3fe-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="7f3fe-111">zeroOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7f3fe-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7f3fe-112">Operación que se va a aplicar cuando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7f3fe-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="7f3fe-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="7f3fe-113">zeroInput : 'T</span></span>

<span data-ttu-id="7f3fe-114">Entrada que se va a proporcionar `zeroOp` cuando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7f3fe-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="7f3fe-115">oneOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7f3fe-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7f3fe-116">Operación que se va a aplicar cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7f3fe-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="7f3fe-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="7f3fe-117">oneInput : 'U</span></span>

<span data-ttu-id="7f3fe-118">Entrada que se va a proporcionar `oneOp` cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7f3fe-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f3fe-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f3fe-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7f3fe-120">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="7f3fe-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f3fe-121">Traslada</span><span class="sxs-lookup"><span data-stu-id="7f3fe-121">'T</span></span>

<span data-ttu-id="7f3fe-122">Tipo de entrada de la operación `zeroOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="7f3fe-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="7f3fe-123">' U</span><span class="sxs-lookup"><span data-stu-id="7f3fe-123">'U</span></span>

<span data-ttu-id="7f3fe-124">Tipo de entrada de la operación `oneOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="7f3fe-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f3fe-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f3fe-125">See Also</span></span>

- [<span data-ttu-id="7f3fe-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="7f3fe-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="7f3fe-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="7f3fe-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="7f3fe-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="7f3fe-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="7f3fe-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="7f3fe-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="7f3fe-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="7f3fe-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)