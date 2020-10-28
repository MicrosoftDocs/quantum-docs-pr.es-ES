---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operación ApplyToTailCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729032"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="0d04d-102">Operación ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="0d04d-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="0d04d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d04d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d04d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d04d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d04d-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="0d04d-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0d04d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d04d-106">Description</span></span>

<span data-ttu-id="0d04d-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0d04d-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0d04d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d04d-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="0d04d-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL</span><span class="sxs-lookup"><span data-stu-id="0d04d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0d04d-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0d04d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0d04d-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="0d04d-111">targets : 'T[]</span></span>

<span data-ttu-id="0d04d-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="0d04d-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d04d-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d04d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d04d-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0d04d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d04d-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="0d04d-115">'T</span></span>

<span data-ttu-id="0d04d-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0d04d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d04d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d04d-117">See Also</span></span>

- [<span data-ttu-id="0d04d-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="0d04d-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="0d04d-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="0d04d-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="0d04d-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="0d04d-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)