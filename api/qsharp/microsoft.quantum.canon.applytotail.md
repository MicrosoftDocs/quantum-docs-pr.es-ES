---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operación ApplyToTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 72b55ec7161d5f6af5e4cb512c648078516c3b4e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729050"
---
# <a name="applytotail-operation"></a><span data-ttu-id="69d07-102">Operación ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="69d07-102">ApplyToTail operation</span></span>

<span data-ttu-id="69d07-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69d07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69d07-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69d07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69d07-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="69d07-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="69d07-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d07-106">Description</span></span>

<span data-ttu-id="69d07-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="69d07-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="69d07-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="69d07-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="69d07-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="69d07-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69d07-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="69d07-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="69d07-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="69d07-111">targets : 'T[]</span></span>

<span data-ttu-id="69d07-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="69d07-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69d07-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69d07-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="69d07-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="69d07-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69d07-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="69d07-115">'T</span></span>

<span data-ttu-id="69d07-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="69d07-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="69d07-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69d07-117">See Also</span></span>

- [<span data-ttu-id="69d07-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="69d07-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="69d07-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="69d07-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="69d07-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="69d07-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)