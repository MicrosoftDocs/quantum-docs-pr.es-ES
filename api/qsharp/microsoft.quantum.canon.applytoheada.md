---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operación ApplyToHeadA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208642"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="45a97-102">Operación ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="45a97-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="45a97-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45a97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45a97-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45a97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45a97-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="45a97-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="45a97-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="45a97-106">Description</span></span>

<span data-ttu-id="45a97-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="45a97-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="45a97-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="45a97-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="45a97-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="45a97-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="45a97-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45a97-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="45a97-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="45a97-111">targets : 'T[]</span></span>

<span data-ttu-id="45a97-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="45a97-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45a97-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45a97-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="45a97-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="45a97-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45a97-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="45a97-115">'T</span></span>

<span data-ttu-id="45a97-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45a97-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="45a97-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45a97-117">See Also</span></span>

- [<span data-ttu-id="45a97-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="45a97-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="45a97-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="45a97-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="45a97-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="45a97-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)