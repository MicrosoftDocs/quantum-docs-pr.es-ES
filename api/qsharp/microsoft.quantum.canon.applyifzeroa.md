---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Operación ApplyIfZeroA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218502"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="5ed7f-102">Operación ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="5ed7f-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="5ed7f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ed7f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ed7f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ed7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ed7f-105">Aplica una operación adjointable condicionada en un valor de resultado clásico a cero.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="5ed7f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ed7f-106">Description</span></span>

<span data-ttu-id="5ed7f-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` .</span><span class="sxs-lookup"><span data-stu-id="5ed7f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="5ed7f-108">Si es `One` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="5ed7f-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="5ed7f-109">El sufijo `A` indica que la operación que se va a aplicar es adjointable.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="5ed7f-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="5ed7f-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="5ed7f-111">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="5ed7f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="5ed7f-112">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="5ed7f-113">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="5ed7f-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ed7f-114">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="5ed7f-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="5ed7f-115">target : 'T</span></span>

<span data-ttu-id="5ed7f-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ed7f-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ed7f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ed7f-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="5ed7f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ed7f-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="5ed7f-119">'T</span></span>

<span data-ttu-id="5ed7f-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="5ed7f-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed7f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ed7f-121">See Also</span></span>

- [<span data-ttu-id="5ed7f-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="5ed7f-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="5ed7f-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="5ed7f-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="5ed7f-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="5ed7f-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)