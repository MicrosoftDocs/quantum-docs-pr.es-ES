---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Operación ApplyToRestCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729086"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="6c323-102">Operación ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="6c323-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="6c323-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c323-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c323-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c323-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c323-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="6c323-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6c323-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c323-106">Description</span></span>

<span data-ttu-id="6c323-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6c323-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6c323-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c323-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="6c323-109">OP: ' t [] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL</span><span class="sxs-lookup"><span data-stu-id="6c323-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6c323-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="6c323-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6c323-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="6c323-111">targets : 'T[]</span></span>

<span data-ttu-id="6c323-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="6c323-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c323-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c323-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6c323-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6c323-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c323-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="6c323-115">'T</span></span>

<span data-ttu-id="6c323-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="6c323-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c323-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c323-117">See Also</span></span>

- [<span data-ttu-id="6c323-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="6c323-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="6c323-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="6c323-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="6c323-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="6c323-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)