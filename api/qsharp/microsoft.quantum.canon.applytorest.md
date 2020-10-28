---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operación ApplyToRest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 29bf080d693c668421181f10faef50f5681683be
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729104"
---
# <a name="applytorest-operation"></a><span data-ttu-id="0010c-102">Operación ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="0010c-102">ApplyToRest operation</span></span>

<span data-ttu-id="0010c-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0010c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0010c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0010c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0010c-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="0010c-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0010c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0010c-106">Description</span></span>

<span data-ttu-id="0010c-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0010c-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0010c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0010c-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="0010c-109">OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0010c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0010c-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0010c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0010c-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="0010c-111">targets : 'T[]</span></span>

<span data-ttu-id="0010c-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="0010c-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0010c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0010c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0010c-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0010c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0010c-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="0010c-115">'T</span></span>

<span data-ttu-id="0010c-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0010c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0010c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0010c-117">See Also</span></span>

- [<span data-ttu-id="0010c-118">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="0010c-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="0010c-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="0010c-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="0010c-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="0010c-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)