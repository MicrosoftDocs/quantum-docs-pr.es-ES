---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operación ApplyToMostCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208421"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="138f1-102">Operación ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="138f1-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="138f1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="138f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="138f1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="138f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="138f1-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="138f1-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="138f1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="138f1-106">Description</span></span>

<span data-ttu-id="138f1-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="138f1-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="138f1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="138f1-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="138f1-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="138f1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="138f1-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="138f1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="138f1-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="138f1-111">targets : 'T[]</span></span>

<span data-ttu-id="138f1-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="138f1-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="138f1-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="138f1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="138f1-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="138f1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="138f1-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="138f1-115">'T</span></span>

<span data-ttu-id="138f1-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="138f1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="138f1-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="138f1-117">See Also</span></span>

- [<span data-ttu-id="138f1-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="138f1-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="138f1-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="138f1-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="138f1-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="138f1-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)