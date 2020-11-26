---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operación ApplyToTail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207979"
---
# <a name="applytotail-operation"></a><span data-ttu-id="33da5-102">Operación ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="33da5-102">ApplyToTail operation</span></span>

<span data-ttu-id="33da5-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33da5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33da5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33da5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33da5-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="33da5-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="33da5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="33da5-106">Description</span></span>

<span data-ttu-id="33da5-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="33da5-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="33da5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="33da5-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="33da5-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="33da5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="33da5-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="33da5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="33da5-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="33da5-111">targets : 'T[]</span></span>

<span data-ttu-id="33da5-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="33da5-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33da5-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33da5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33da5-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="33da5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33da5-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="33da5-115">'T</span></span>

<span data-ttu-id="33da5-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="33da5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="33da5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33da5-117">See Also</span></span>

- [<span data-ttu-id="33da5-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="33da5-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="33da5-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="33da5-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="33da5-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="33da5-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)