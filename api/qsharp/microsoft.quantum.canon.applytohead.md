---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operación ApplyToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217346"
---
# <a name="applytohead-operation"></a><span data-ttu-id="436d5-102">Operación ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="436d5-102">ApplyToHead operation</span></span>

<span data-ttu-id="436d5-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="436d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="436d5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="436d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="436d5-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="436d5-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="436d5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="436d5-106">Description</span></span>

<span data-ttu-id="436d5-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="436d5-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="436d5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="436d5-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="436d5-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="436d5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="436d5-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="436d5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="436d5-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="436d5-111">targets : 'T[]</span></span>

<span data-ttu-id="436d5-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="436d5-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="436d5-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="436d5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="436d5-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="436d5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="436d5-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="436d5-115">'T</span></span>

<span data-ttu-id="436d5-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="436d5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="436d5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="436d5-117">See Also</span></span>

- [<span data-ttu-id="436d5-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="436d5-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="436d5-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="436d5-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="436d5-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="436d5-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)