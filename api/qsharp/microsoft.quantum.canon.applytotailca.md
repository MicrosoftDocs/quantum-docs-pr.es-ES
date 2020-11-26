---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operación ApplyToTailCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207860"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="91281-102">Operación ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="91281-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="91281-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91281-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91281-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91281-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91281-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="91281-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="91281-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="91281-106">Description</span></span>

<span data-ttu-id="91281-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="91281-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="91281-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="91281-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="91281-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="91281-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="91281-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="91281-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="91281-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="91281-111">targets : 'T[]</span></span>

<span data-ttu-id="91281-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="91281-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91281-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91281-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="91281-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="91281-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91281-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="91281-115">'T</span></span>

<span data-ttu-id="91281-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="91281-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="91281-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91281-117">See Also</span></span>

- [<span data-ttu-id="91281-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="91281-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="91281-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="91281-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="91281-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="91281-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)