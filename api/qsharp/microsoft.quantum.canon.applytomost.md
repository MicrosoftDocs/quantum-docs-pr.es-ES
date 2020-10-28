---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operación ApplyToMost
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729153"
---
# <a name="applytomost-operation"></a><span data-ttu-id="dce8f-102">Operación ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="dce8f-102">ApplyToMost operation</span></span>

<span data-ttu-id="dce8f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dce8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dce8f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dce8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dce8f-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="dce8f-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="dce8f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dce8f-106">Description</span></span>

<span data-ttu-id="dce8f-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="dce8f-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="dce8f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="dce8f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="dce8f-109">OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="dce8f-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dce8f-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="dce8f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="dce8f-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="dce8f-111">targets : 'T[]</span></span>

<span data-ttu-id="dce8f-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="dce8f-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dce8f-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dce8f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dce8f-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dce8f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dce8f-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="dce8f-115">'T</span></span>

<span data-ttu-id="dce8f-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="dce8f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dce8f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dce8f-117">See Also</span></span>

- [<span data-ttu-id="dce8f-118">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="dce8f-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="dce8f-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="dce8f-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="dce8f-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="dce8f-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)