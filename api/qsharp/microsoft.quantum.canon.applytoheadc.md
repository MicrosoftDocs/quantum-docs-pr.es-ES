---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operación ApplyToHeadC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850625"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="fc20b-102">Operación ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="fc20b-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="fc20b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc20b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc20b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc20b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc20b-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="fc20b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="fc20b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc20b-106">Description</span></span>

<span data-ttu-id="fc20b-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="fc20b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="fc20b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc20b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="fc20b-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="fc20b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fc20b-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="fc20b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fc20b-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="fc20b-111">targets : 'T[]</span></span>

<span data-ttu-id="fc20b-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="fc20b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc20b-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc20b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc20b-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fc20b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc20b-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="fc20b-115">'T</span></span>

<span data-ttu-id="fc20b-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="fc20b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc20b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc20b-117">See Also</span></span>

- [<span data-ttu-id="fc20b-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="fc20b-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="fc20b-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="fc20b-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="fc20b-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="fc20b-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)