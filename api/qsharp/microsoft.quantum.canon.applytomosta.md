---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operación ApplyToMostA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729146"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="c17be-102">Operación ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="c17be-102">ApplyToMostA operation</span></span>

<span data-ttu-id="c17be-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c17be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c17be-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c17be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c17be-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="c17be-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c17be-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c17be-106">Description</span></span>

<span data-ttu-id="c17be-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c17be-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c17be-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c17be-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c17be-109">OP: ' t [] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c17be-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c17be-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="c17be-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c17be-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="c17be-111">targets : 'T[]</span></span>

<span data-ttu-id="c17be-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="c17be-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c17be-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c17be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c17be-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c17be-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c17be-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="c17be-115">'T</span></span>

<span data-ttu-id="c17be-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="c17be-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c17be-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c17be-117">See Also</span></span>

- [<span data-ttu-id="c17be-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="c17be-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="c17be-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="c17be-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="c17be-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="c17be-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)