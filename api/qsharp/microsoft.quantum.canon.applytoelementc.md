---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operación ApplyToElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217584"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="1d894-102">Operación ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="1d894-102">ApplyToElementC operation</span></span>

<span data-ttu-id="1d894-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d894-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d894-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d894-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d894-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="1d894-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="1d894-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d894-106">Description</span></span>

<span data-ttu-id="1d894-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="1d894-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="1d894-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d894-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1d894-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="1d894-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1d894-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="1d894-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="1d894-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d894-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d894-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="1d894-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1d894-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="1d894-113">targets : 'T[]</span></span>

<span data-ttu-id="1d894-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="1d894-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d894-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d894-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1d894-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1d894-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1d894-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="1d894-117">'T</span></span>

<span data-ttu-id="1d894-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="1d894-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d894-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d894-119">See Also</span></span>

- [<span data-ttu-id="1d894-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="1d894-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="1d894-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="1d894-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="1d894-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="1d894-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)