---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operación ApplyToElementA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729266"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="9e1ae-102">Operación ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="9e1ae-102">ApplyToElementA operation</span></span>

<span data-ttu-id="9e1ae-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e1ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e1ae-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e1ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e1ae-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="9e1ae-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9e1ae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e1ae-106">Description</span></span>

<span data-ttu-id="9e1ae-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="9e1ae-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9e1ae-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9e1ae-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="9e1ae-109">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e1ae-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9e1ae-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9e1ae-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9e1ae-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e1ae-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e1ae-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="9e1ae-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9e1ae-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="9e1ae-113">targets : 'T[]</span></span>

<span data-ttu-id="9e1ae-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="9e1ae-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e1ae-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e1ae-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9e1ae-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9e1ae-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e1ae-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="9e1ae-117">'T</span></span>

<span data-ttu-id="9e1ae-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9e1ae-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e1ae-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e1ae-119">See Also</span></span>

- [<span data-ttu-id="9e1ae-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="9e1ae-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9e1ae-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="9e1ae-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="9e1ae-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="9e1ae-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)