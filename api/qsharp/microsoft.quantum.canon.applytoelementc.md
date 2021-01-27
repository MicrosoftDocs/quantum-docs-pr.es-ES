---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operación ApplyToElementC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850739"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="fbcf7-102">Operación ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="fbcf7-102">ApplyToElementC operation</span></span>

<span data-ttu-id="fbcf7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbcf7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbcf7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbcf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbcf7-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="fbcf7-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="fbcf7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbcf7-106">Description</span></span>

<span data-ttu-id="fbcf7-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="fbcf7-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="fbcf7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fbcf7-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="fbcf7-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="fbcf7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fbcf7-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="fbcf7-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="fbcf7-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbcf7-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbcf7-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="fbcf7-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fbcf7-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="fbcf7-113">targets : 'T[]</span></span>

<span data-ttu-id="fbcf7-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="fbcf7-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbcf7-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbcf7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fbcf7-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fbcf7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbcf7-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="fbcf7-117">'T</span></span>

<span data-ttu-id="fbcf7-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="fbcf7-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbcf7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbcf7-119">See Also</span></span>

- [<span data-ttu-id="fbcf7-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="fbcf7-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="fbcf7-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="fbcf7-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="fbcf7-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="fbcf7-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)