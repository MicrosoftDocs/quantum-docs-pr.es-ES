---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operación ApplyIfElseRA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729548"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="2bf0f-102">Operación ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="2bf0f-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="2bf0f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2bf0f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bf0f-105">Aplica una de las dos operaciones adjointable, dependiendo del valor de un resultado clásico.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="2bf0f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bf0f-106">Description</span></span>

<span data-ttu-id="2bf0f-107">Dado un resultado `result` , se aplica la operación `zeroOp` con `zeroInput` como entrada cuando `result` es igual a `Zero` y se aplica `oneOp(oneInput)` cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="2bf0f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2bf0f-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="2bf0f-109">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="2bf0f-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="2bf0f-110">El resultado de la medida que se usa para determinar si `zeroOp` `oneOp` se aplica o.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj"></a><span data-ttu-id="2bf0f-111">zeroOp: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2bf0f-112">La operación adjointable que se va a aplicar cuando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="2bf0f-113">zeroInput: ' t</span><span class="sxs-lookup"><span data-stu-id="2bf0f-113">zeroInput : 'T</span></span>

<span data-ttu-id="2bf0f-114">Entrada que se va a proporcionar `zeroOp` cuando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj"></a><span data-ttu-id="2bf0f-115">oneOp: ' U => ajuste de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2bf0f-116">La operación adjointable que se va a aplicar cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="2bf0f-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="2bf0f-117">oneInput : 'U</span></span>

<span data-ttu-id="2bf0f-118">Entrada que se va a proporcionar `oneOp` cuando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2bf0f-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2bf0f-120">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2bf0f-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2bf0f-121">Traslada</span><span class="sxs-lookup"><span data-stu-id="2bf0f-121">'T</span></span>

<span data-ttu-id="2bf0f-122">Tipo de entrada de la operación `zeroOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="2bf0f-123">' U</span><span class="sxs-lookup"><span data-stu-id="2bf0f-123">'U</span></span>

<span data-ttu-id="2bf0f-124">Tipo de entrada de la operación `oneOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bf0f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bf0f-125">See Also</span></span>

- [<span data-ttu-id="2bf0f-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="2bf0f-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="2bf0f-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="2bf0f-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="2bf0f-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="2bf0f-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="2bf0f-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="2bf0f-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="2bf0f-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="2bf0f-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)