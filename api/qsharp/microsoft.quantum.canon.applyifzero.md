---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Operación ApplyIfZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3b14ef8a1aa736fe096a21fe51be5a7c5bb1d09d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209441"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="1e0bc-102">Operación ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="1e0bc-102">ApplyIfZero operation</span></span>

<span data-ttu-id="1e0bc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e0bc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e0bc-105">Aplica una operación condicionada a que un valor de resultado clásico sea cero.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="1e0bc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e0bc-106">Description</span></span>

<span data-ttu-id="1e0bc-107">Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `Zero` .</span><span class="sxs-lookup"><span data-stu-id="1e0bc-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="1e0bc-108">Si es `One` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="1e0bc-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="1e0bc-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="1e0bc-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="1e0bc-110">resultado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="1e0bc-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="1e0bc-111">Resultado de la medida que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="1e0bc-112">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="1e0bc-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1e0bc-113">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="1e0bc-114">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="1e0bc-114">target : 'T</span></span>

<span data-ttu-id="1e0bc-115">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e0bc-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1e0bc-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1e0bc-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1e0bc-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="1e0bc-118">'T</span></span>

<span data-ttu-id="1e0bc-119">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e0bc-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e0bc-120">See Also</span></span>

- [<span data-ttu-id="1e0bc-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="1e0bc-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="1e0bc-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="1e0bc-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="1e0bc-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="1e0bc-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)