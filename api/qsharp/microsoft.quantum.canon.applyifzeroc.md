---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Operación ApplyIfZeroC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: c89490b13d946d119f3fd38d130d90847d67fea6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209356"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="e6f17-102">Operación ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="e6f17-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="e6f17-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6f17-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6f17-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6f17-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6f17-105">Aplica una operación controlable condicionada en un valor de resultado clásico a cero.</span><span class="sxs-lookup"><span data-stu-id="e6f17-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="e6f17-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6f17-106">Description</span></span>

<span data-ttu-id="e6f17-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` .</span><span class="sxs-lookup"><span data-stu-id="e6f17-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="e6f17-108">Si es `One` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="e6f17-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e6f17-109">El sufijo `C` indica que la operación que se va a aplicar es controlable.</span><span class="sxs-lookup"><span data-stu-id="e6f17-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="e6f17-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="e6f17-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e6f17-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="e6f17-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e6f17-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="e6f17-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="e6f17-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="e6f17-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e6f17-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="e6f17-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e6f17-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="e6f17-115">target : 'T</span></span>

<span data-ttu-id="e6f17-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="e6f17-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6f17-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6f17-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e6f17-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e6f17-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6f17-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="e6f17-119">'T</span></span>

<span data-ttu-id="e6f17-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="e6f17-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6f17-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6f17-121">See Also</span></span>

- [<span data-ttu-id="e6f17-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="e6f17-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="e6f17-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="e6f17-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="e6f17-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="e6f17-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)