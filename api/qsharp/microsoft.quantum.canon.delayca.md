---
uid: Microsoft.Quantum.Canon.DelayCA
title: Operación DelayCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728744"
---
# <a name="delayca-operation"></a><span data-ttu-id="a9e07-102">Operación DelayCA</span><span class="sxs-lookup"><span data-stu-id="a9e07-102">DelayCA operation</span></span>

<span data-ttu-id="a9e07-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9e07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9e07-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9e07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9e07-105">Aplica una operación determinada con un retraso.</span><span class="sxs-lookup"><span data-stu-id="a9e07-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="a9e07-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9e07-106">Description</span></span>

<span data-ttu-id="a9e07-107">Dada una operación y una entrada para esa operación, se aplica la operación una vez que se proporciona una entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="a9e07-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="a9e07-108">En concreto, la expresión `Delay(op, arg, _)` es una operación que se aplica `op` a `arg` cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="a9e07-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="a9e07-109">`Delay(op,arg,_)`La expresión permite retrasar la aplicación de `op` .</span><span class="sxs-lookup"><span data-stu-id="a9e07-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="a9e07-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="a9e07-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="a9e07-111">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="a9e07-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="a9e07-112">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a9e07-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a9e07-113">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="a9e07-113">arg : 'T</span></span>

<span data-ttu-id="a9e07-114">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="a9e07-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="a9e07-115">AUX: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9e07-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a9e07-116">Argumento que se usa para retrasar la aplicación de la operación mediante el uso de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e07-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9e07-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9e07-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9e07-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a9e07-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9e07-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="a9e07-119">'T</span></span>

<span data-ttu-id="a9e07-120">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="a9e07-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9e07-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9e07-121">See Also</span></span>

- [<span data-ttu-id="a9e07-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a9e07-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="a9e07-123">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="a9e07-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)