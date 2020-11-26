---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Operación ApplyIfZeroCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4baae1fe7d615cbbf01935b4eca05fe947ff296e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218468"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="87fc4-102">Operación ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="87fc4-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="87fc4-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87fc4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87fc4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87fc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87fc4-105">Aplica una operación de unitario condicionada en un valor de resultado clásico a cero.</span><span class="sxs-lookup"><span data-stu-id="87fc4-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="87fc4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="87fc4-106">Description</span></span>

<span data-ttu-id="87fc4-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` .</span><span class="sxs-lookup"><span data-stu-id="87fc4-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="87fc4-108">Si es `One` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="87fc4-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="87fc4-109">El sufijo `CA` indica que la operación que se va a aplicar es la unitario (controlable y adjointable).</span><span class="sxs-lookup"><span data-stu-id="87fc4-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="87fc4-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="87fc4-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="87fc4-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="87fc4-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="87fc4-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="87fc4-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="87fc4-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="87fc4-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="87fc4-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="87fc4-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="87fc4-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="87fc4-115">target : 'T</span></span>

<span data-ttu-id="87fc4-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="87fc4-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87fc4-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87fc4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87fc4-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="87fc4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87fc4-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="87fc4-119">'T</span></span>

<span data-ttu-id="87fc4-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="87fc4-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="87fc4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87fc4-121">See Also</span></span>

- [<span data-ttu-id="87fc4-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="87fc4-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="87fc4-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="87fc4-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="87fc4-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="87fc4-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)