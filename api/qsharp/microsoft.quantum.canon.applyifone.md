---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Operación ApplyIfOne
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841777"
---
# <a name="applyifone-operation"></a><span data-ttu-id="9a38f-102">Operación ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="9a38f-102">ApplyIfOne operation</span></span>

<span data-ttu-id="9a38f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a38f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a38f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a38f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a38f-105">Aplica una operación condicionada a un valor de resultado clásico a uno.</span><span class="sxs-lookup"><span data-stu-id="9a38f-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="9a38f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a38f-106">Description</span></span>

<span data-ttu-id="9a38f-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` .</span><span class="sxs-lookup"><span data-stu-id="9a38f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="9a38f-108">Si es `Zero` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="9a38f-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="9a38f-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="9a38f-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9a38f-110">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="9a38f-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="9a38f-111">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="9a38f-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="9a38f-112">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="9a38f-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9a38f-113">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="9a38f-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="9a38f-114">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="9a38f-114">target : 'T</span></span>

<span data-ttu-id="9a38f-115">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="9a38f-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a38f-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a38f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a38f-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9a38f-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a38f-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="9a38f-118">'T</span></span>

<span data-ttu-id="9a38f-119">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="9a38f-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a38f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a38f-120">See Also</span></span>

- [<span data-ttu-id="9a38f-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="9a38f-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="9a38f-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="9a38f-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="9a38f-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="9a38f-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)