---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operación ApplyToElementA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850763"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="3aa0e-102">Operación ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="3aa0e-102">ApplyToElementA operation</span></span>

<span data-ttu-id="3aa0e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3aa0e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3aa0e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3aa0e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3aa0e-105">Aplica una operación a un elemento determinado de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3aa0e-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3aa0e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3aa0e-106">Description</span></span>

<span data-ttu-id="3aa0e-107">Dada una operación `op` , `index` se aplica un índice y una matriz de destinos `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="3aa0e-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="3aa0e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3aa0e-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3aa0e-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="3aa0e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3aa0e-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="3aa0e-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="3aa0e-111">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3aa0e-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3aa0e-112">Índice en la matriz de destinos.</span><span class="sxs-lookup"><span data-stu-id="3aa0e-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="3aa0e-113">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="3aa0e-113">targets : 'T[]</span></span>

<span data-ttu-id="3aa0e-114">Matriz de destinos posibles para `op` .</span><span class="sxs-lookup"><span data-stu-id="3aa0e-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3aa0e-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3aa0e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3aa0e-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3aa0e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3aa0e-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="3aa0e-117">'T</span></span>

<span data-ttu-id="3aa0e-118">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="3aa0e-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3aa0e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3aa0e-119">See Also</span></span>

- [<span data-ttu-id="3aa0e-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="3aa0e-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="3aa0e-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="3aa0e-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="3aa0e-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="3aa0e-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)