---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operación ApplyToElementC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729249"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="44566-102">Operación ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="44566-102">ApplyToElementC operation</span></span>

<span data-ttu-id="44566-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44566-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44566-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44566-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44566-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="44566-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="44566-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="44566-106">Description</span></span>

<span data-ttu-id="44566-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="44566-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="44566-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="44566-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="44566-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44566-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="44566-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="44566-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="44566-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44566-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44566-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="44566-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="44566-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="44566-113">targets : 'T[]</span></span>

<span data-ttu-id="44566-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="44566-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44566-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44566-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="44566-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="44566-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44566-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="44566-117">'T</span></span>

<span data-ttu-id="44566-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="44566-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="44566-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44566-119">See Also</span></span>

- [<span data-ttu-id="44566-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="44566-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="44566-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="44566-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="44566-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="44566-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)