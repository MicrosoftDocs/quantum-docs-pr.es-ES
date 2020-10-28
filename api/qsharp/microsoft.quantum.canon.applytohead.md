---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operación ApplyToHead
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e5fc439f48a5c7e527b7805c35cce18eca3ab36
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729171"
---
# <a name="applytohead-operation"></a><span data-ttu-id="db6ce-102">Operación ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="db6ce-102">ApplyToHead operation</span></span>

<span data-ttu-id="db6ce-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db6ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db6ce-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db6ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db6ce-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="db6ce-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="db6ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="db6ce-106">Description</span></span>

<span data-ttu-id="db6ce-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="db6ce-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="db6ce-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="db6ce-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="db6ce-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="db6ce-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="db6ce-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="db6ce-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="db6ce-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="db6ce-111">targets : 'T[]</span></span>

<span data-ttu-id="db6ce-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="db6ce-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db6ce-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db6ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db6ce-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="db6ce-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db6ce-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="db6ce-115">'T</span></span>

<span data-ttu-id="db6ce-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="db6ce-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="db6ce-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db6ce-117">See Also</span></span>

- [<span data-ttu-id="db6ce-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="db6ce-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="db6ce-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="db6ce-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="db6ce-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="db6ce-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)