---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operación ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850586"
---
# <a name="applytomost-operation"></a><span data-ttu-id="f38bb-102">Operación ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="f38bb-102">ApplyToMost operation</span></span>

<span data-ttu-id="f38bb-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f38bb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f38bb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f38bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f38bb-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f38bb-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f38bb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f38bb-106">Description</span></span>

<span data-ttu-id="f38bb-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f38bb-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f38bb-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f38bb-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f38bb-109">OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f38bb-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f38bb-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f38bb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f38bb-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="f38bb-111">targets : 'T[]</span></span>

<span data-ttu-id="f38bb-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="f38bb-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f38bb-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f38bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f38bb-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f38bb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f38bb-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="f38bb-115">'T</span></span>

<span data-ttu-id="f38bb-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f38bb-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="f38bb-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f38bb-117">Example</span></span>

<span data-ttu-id="f38bb-118">Los siguientes fragmentos de código de Q # son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f38bb-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="f38bb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f38bb-119">See Also</span></span>

- [<span data-ttu-id="f38bb-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="f38bb-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="f38bb-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="f38bb-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="f38bb-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="f38bb-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)