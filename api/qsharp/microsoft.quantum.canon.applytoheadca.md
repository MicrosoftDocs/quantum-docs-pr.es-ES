---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Operación ApplyToHeadCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850612"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="b0e5f-102">Operación ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="b0e5f-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="b0e5f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0e5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0e5f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0e5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0e5f-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b0e5f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0e5f-106">Description</span></span>

<span data-ttu-id="b0e5f-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b0e5f-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b0e5f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0e5f-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b0e5f-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b0e5f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b0e5f-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b0e5f-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="b0e5f-111">targets : 'T[]</span></span>

<span data-ttu-id="b0e5f-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="b0e5f-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0e5f-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0e5f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0e5f-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b0e5f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0e5f-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="b0e5f-115">'T</span></span>

<span data-ttu-id="b0e5f-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0e5f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0e5f-117">See Also</span></span>

- [<span data-ttu-id="b0e5f-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="b0e5f-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="b0e5f-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="b0e5f-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="b0e5f-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="b0e5f-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)