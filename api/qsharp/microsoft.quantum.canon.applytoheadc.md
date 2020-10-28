---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operación ApplyToHeadC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729164"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="0cfd9-102">Operación ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="0cfd9-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="0cfd9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0cfd9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0cfd9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0cfd9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0cfd9-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="0cfd9-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0cfd9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cfd9-106">Description</span></span>

<span data-ttu-id="0cfd9-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0cfd9-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0cfd9-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cfd9-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="0cfd9-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cfd9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0cfd9-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0cfd9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0cfd9-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="0cfd9-111">targets : 'T[]</span></span>

<span data-ttu-id="0cfd9-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="0cfd9-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cfd9-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cfd9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0cfd9-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0cfd9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0cfd9-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="0cfd9-115">'T</span></span>

<span data-ttu-id="0cfd9-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0cfd9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cfd9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0cfd9-117">See Also</span></span>

- [<span data-ttu-id="0cfd9-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="0cfd9-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="0cfd9-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="0cfd9-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="0cfd9-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="0cfd9-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)