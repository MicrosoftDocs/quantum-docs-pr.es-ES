---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Operación ApplyToElementCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841468"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="35646-102">Operación ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="35646-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="35646-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35646-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35646-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35646-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35646-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="35646-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="35646-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="35646-106">Description</span></span>

<span data-ttu-id="35646-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="35646-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="35646-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="35646-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="35646-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="35646-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="35646-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="35646-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="35646-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35646-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35646-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="35646-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="35646-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="35646-113">targets : 'T[]</span></span>

<span data-ttu-id="35646-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="35646-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35646-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35646-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35646-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="35646-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35646-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="35646-117">'T</span></span>

<span data-ttu-id="35646-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="35646-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="35646-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35646-119">See Also</span></span>

- [<span data-ttu-id="35646-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="35646-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="35646-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="35646-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="35646-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="35646-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)