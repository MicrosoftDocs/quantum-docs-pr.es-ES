---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operación ApplyToHeadC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208608"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="99cc0-102">Operación ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="99cc0-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="99cc0-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99cc0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99cc0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99cc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99cc0-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="99cc0-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="99cc0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="99cc0-106">Description</span></span>

<span data-ttu-id="99cc0-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="99cc0-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="99cc0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="99cc0-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="99cc0-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="99cc0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="99cc0-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="99cc0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="99cc0-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="99cc0-111">targets : 'T[]</span></span>

<span data-ttu-id="99cc0-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="99cc0-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99cc0-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99cc0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99cc0-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="99cc0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99cc0-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="99cc0-115">'T</span></span>

<span data-ttu-id="99cc0-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="99cc0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="99cc0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99cc0-117">See Also</span></span>

- [<span data-ttu-id="99cc0-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="99cc0-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="99cc0-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="99cc0-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="99cc0-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="99cc0-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)