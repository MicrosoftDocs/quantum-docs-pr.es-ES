---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operación ApplyToTailA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729045"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="4e73f-102">Operación ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="4e73f-102">ApplyToTailA operation</span></span>

<span data-ttu-id="4e73f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e73f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e73f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e73f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e73f-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="4e73f-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4e73f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e73f-106">Description</span></span>

<span data-ttu-id="4e73f-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4e73f-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4e73f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4e73f-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="4e73f-109">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e73f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4e73f-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4e73f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4e73f-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="4e73f-111">targets : 'T[]</span></span>

<span data-ttu-id="4e73f-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="4e73f-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e73f-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e73f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4e73f-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4e73f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e73f-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="4e73f-115">'T</span></span>

<span data-ttu-id="4e73f-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4e73f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e73f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e73f-117">See Also</span></span>

- [<span data-ttu-id="4e73f-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="4e73f-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="4e73f-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="4e73f-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="4e73f-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="4e73f-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)