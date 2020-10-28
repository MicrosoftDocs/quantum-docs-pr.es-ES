---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Operación ApplyIfElseBC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729580"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="67032-102">Operación ApplyIfElseBC</span><span class="sxs-lookup"><span data-stu-id="67032-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="67032-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67032-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67032-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67032-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67032-105">Aplica una de dos operaciones controlables, dependiendo del valor de un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="67032-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="67032-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="67032-106">Description</span></span>

<span data-ttu-id="67032-107">Dado un bit `bit` , aplica la operación `trueOp` con `trueInput` como su entrada cuando `bit` es `true` y se aplica `falseOp(falseInput)` cuando `bit` es `false` .</span><span class="sxs-lookup"><span data-stu-id="67032-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="67032-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="67032-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="67032-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67032-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="67032-110">Valor booleano que se usa para determinar `trueOp` si `falseOp` se aplica o.</span><span class="sxs-lookup"><span data-stu-id="67032-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-ctl"></a><span data-ttu-id="67032-111">trueOp: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67032-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="67032-112">Operación controlable que se va a aplicar cuando `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="67032-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="67032-113">trueInput: ' t</span><span class="sxs-lookup"><span data-stu-id="67032-113">trueInput : 'T</span></span>

<span data-ttu-id="67032-114">Entrada que se va a proporcionar `trueOp` cuando `bit` sea `true` .</span><span class="sxs-lookup"><span data-stu-id="67032-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-ctl"></a><span data-ttu-id="67032-115">falseOp: ' U => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67032-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="67032-116">Operación controlable que se va a aplicar cuando `bit` es `false` .</span><span class="sxs-lookup"><span data-stu-id="67032-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="67032-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="67032-117">falseInput : 'U</span></span>

<span data-ttu-id="67032-118">Entrada que se va a proporcionar `falseOp` cuando `bit` sea `false` .</span><span class="sxs-lookup"><span data-stu-id="67032-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67032-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67032-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="67032-120">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="67032-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67032-121">Traslada</span><span class="sxs-lookup"><span data-stu-id="67032-121">'T</span></span>

<span data-ttu-id="67032-122">Tipo de entrada de la operación `trueOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="67032-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="67032-123">' U</span><span class="sxs-lookup"><span data-stu-id="67032-123">'U</span></span>

<span data-ttu-id="67032-124">Tipo de entrada de la operación `falseOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="67032-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="67032-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67032-125">See Also</span></span>

- [<span data-ttu-id="67032-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="67032-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="67032-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="67032-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="67032-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="67032-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="67032-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="67032-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="67032-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="67032-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)