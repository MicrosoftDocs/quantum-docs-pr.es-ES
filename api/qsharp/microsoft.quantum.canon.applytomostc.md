---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operación ApplyToMostC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208472"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="a8724-102">Operación ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="a8724-102">ApplyToMostC operation</span></span>

<span data-ttu-id="a8724-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8724-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8724-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8724-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8724-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="a8724-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="a8724-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8724-106">Description</span></span>

<span data-ttu-id="a8724-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a8724-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a8724-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a8724-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="a8724-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="a8724-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a8724-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a8724-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a8724-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="a8724-111">targets : 'T[]</span></span>

<span data-ttu-id="a8724-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="a8724-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8724-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8724-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8724-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a8724-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8724-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="a8724-115">'T</span></span>

<span data-ttu-id="a8724-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a8724-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8724-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8724-117">See Also</span></span>

- [<span data-ttu-id="a8724-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="a8724-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="a8724-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="a8724-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="a8724-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="a8724-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)