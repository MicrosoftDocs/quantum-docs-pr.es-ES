---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operación ApplyIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729567"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="2c475-102">Operación ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="2c475-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="2c475-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c475-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c475-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c475-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c475-105">Aplica una de las dos operaciones de unitario, dependiendo del valor de un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="2c475-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="2c475-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c475-106">Description</span></span>

<span data-ttu-id="2c475-107">Dado un bit `bit` , aplica la operación `trueOp` con `trueInput` como su entrada cuando `bit` es `true` y se aplica `falseOp(falseInput)` cuando `bit` es `false` .</span><span class="sxs-lookup"><span data-stu-id="2c475-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="2c475-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c475-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="2c475-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c475-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c475-110">Valor booleano que se usa para determinar `trueOp` si `falseOp` se aplica o.</span><span class="sxs-lookup"><span data-stu-id="2c475-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="2c475-111">trueOp: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="2c475-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2c475-112">La operación unitario que se va a aplicar cuando `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="2c475-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="2c475-113">trueInput: ' t</span><span class="sxs-lookup"><span data-stu-id="2c475-113">trueInput : 'T</span></span>

<span data-ttu-id="2c475-114">Entrada que se va a proporcionar `trueOp` cuando `bit` sea `true` .</span><span class="sxs-lookup"><span data-stu-id="2c475-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="2c475-115">falseOp: ' U => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="2c475-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2c475-116">La operación unitario que se va a aplicar cuando `bit` es `false` .</span><span class="sxs-lookup"><span data-stu-id="2c475-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="2c475-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="2c475-117">falseInput : 'U</span></span>

<span data-ttu-id="2c475-118">Entrada que se va a proporcionar `falseOp` cuando `bit` sea `false` .</span><span class="sxs-lookup"><span data-stu-id="2c475-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c475-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c475-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c475-120">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2c475-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c475-121">Traslada</span><span class="sxs-lookup"><span data-stu-id="2c475-121">'T</span></span>

<span data-ttu-id="2c475-122">Tipo de entrada de la operación `trueOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2c475-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="2c475-123">' U</span><span class="sxs-lookup"><span data-stu-id="2c475-123">'U</span></span>

<span data-ttu-id="2c475-124">Tipo de entrada de la operación `falseOp` que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2c475-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c475-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c475-125">See Also</span></span>

- [<span data-ttu-id="2c475-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="2c475-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="2c475-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="2c475-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="2c475-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="2c475-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="2c475-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="2c475-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="2c475-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="2c475-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)