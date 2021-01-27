---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Operación ApplyIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841756"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="3c03f-102">Operación ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3c03f-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="3c03f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c03f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c03f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c03f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c03f-105">Aplica una operación controlable condicionada a un valor de resultado clásico que es uno.</span><span class="sxs-lookup"><span data-stu-id="3c03f-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="3c03f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c03f-106">Description</span></span>

<span data-ttu-id="3c03f-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` .</span><span class="sxs-lookup"><span data-stu-id="3c03f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="3c03f-108">Si es `Zero` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="3c03f-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3c03f-109">El sufijo `C` indica que la operación que se va a aplicar es controlable.</span><span class="sxs-lookup"><span data-stu-id="3c03f-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="3c03f-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c03f-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3c03f-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="3c03f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3c03f-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="3c03f-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="3c03f-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="3c03f-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3c03f-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="3c03f-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3c03f-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="3c03f-115">target : 'T</span></span>

<span data-ttu-id="3c03f-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="3c03f-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c03f-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c03f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c03f-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3c03f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c03f-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="3c03f-119">'T</span></span>

<span data-ttu-id="3c03f-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="3c03f-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c03f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c03f-121">See Also</span></span>

- [<span data-ttu-id="3c03f-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3c03f-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="3c03f-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="3c03f-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="3c03f-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="3c03f-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)