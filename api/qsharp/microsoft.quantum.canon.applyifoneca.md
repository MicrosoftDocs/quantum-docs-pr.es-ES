---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: Operación ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218587"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="ca190-102">Operación ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="ca190-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="ca190-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca190-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca190-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca190-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca190-105">Aplica una operación de unitario condicionada en un valor de resultado clásico a uno.</span><span class="sxs-lookup"><span data-stu-id="ca190-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ca190-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca190-106">Description</span></span>

<span data-ttu-id="ca190-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` .</span><span class="sxs-lookup"><span data-stu-id="ca190-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="ca190-108">Si es `Zero` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="ca190-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="ca190-109">El sufijo `CA` indica que la operación que se va a aplicar es la unitario (controlable y adjointable).</span><span class="sxs-lookup"><span data-stu-id="ca190-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="ca190-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="ca190-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="ca190-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="ca190-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="ca190-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="ca190-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ca190-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ca190-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ca190-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="ca190-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="ca190-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="ca190-115">target : 'T</span></span>

<span data-ttu-id="ca190-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="ca190-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca190-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca190-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca190-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ca190-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca190-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="ca190-119">'T</span></span>

<span data-ttu-id="ca190-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="ca190-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca190-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca190-121">See Also</span></span>

- [<span data-ttu-id="ca190-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="ca190-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="ca190-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="ca190-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="ca190-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="ca190-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)