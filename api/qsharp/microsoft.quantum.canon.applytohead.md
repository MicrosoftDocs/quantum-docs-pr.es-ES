---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operación ApplyToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841339"
---
# <a name="applytohead-operation"></a><span data-ttu-id="e675b-102">Operación ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="e675b-102">ApplyToHead operation</span></span>

<span data-ttu-id="e675b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e675b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e675b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e675b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e675b-105">Aplica una operación al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e675b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e675b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e675b-106">Description</span></span>

<span data-ttu-id="e675b-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e675b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e675b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e675b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e675b-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="e675b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e675b-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="e675b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e675b-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="e675b-111">targets : 'T[]</span></span>

<span data-ttu-id="e675b-112">Matriz de destinos a la que se aplicará el primer `op` .</span><span class="sxs-lookup"><span data-stu-id="e675b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e675b-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e675b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e675b-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e675b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e675b-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="e675b-115">'T</span></span>

<span data-ttu-id="e675b-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="e675b-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="e675b-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e675b-117">Example</span></span>

<span data-ttu-id="e675b-118">Los siguientes fragmentos de código de Q # son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="e675b-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="e675b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e675b-119">See Also</span></span>

- [<span data-ttu-id="e675b-120">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="e675b-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="e675b-121">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e675b-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e675b-122">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="e675b-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)