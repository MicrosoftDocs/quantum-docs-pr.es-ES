---
uid: Microsoft.Quantum.Canon.DelayCA
title: Operación DelayCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a32a4f4a3f5d0f253a4c4eaf28c67db8da978b0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207095"
---
# <a name="delayca-operation"></a><span data-ttu-id="d53c4-102">Operación DelayCA</span><span class="sxs-lookup"><span data-stu-id="d53c4-102">DelayCA operation</span></span>

<span data-ttu-id="d53c4-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d53c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d53c4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d53c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d53c4-105">Aplica una operación determinada con un retraso.</span><span class="sxs-lookup"><span data-stu-id="d53c4-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d53c4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d53c4-106">Description</span></span>

<span data-ttu-id="d53c4-107">Dada una operación y una entrada para esa operación, se aplica la operación una vez que se proporciona una entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="d53c4-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="d53c4-108">En concreto, la expresión `Delay(op, arg, _)` es una operación que se aplica `op` a `arg` cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="d53c4-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="d53c4-109">`Delay(op,arg,_)`La expresión permite retrasar la aplicación de `op` .</span><span class="sxs-lookup"><span data-stu-id="d53c4-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="d53c4-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="d53c4-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="d53c4-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="d53c4-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d53c4-112">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d53c4-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="d53c4-113">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="d53c4-113">arg : 'T</span></span>

<span data-ttu-id="d53c4-114">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="d53c4-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="d53c4-115">AUX: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d53c4-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="d53c4-116">Argumento que se usa para retrasar la aplicación de la operación mediante el uso de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="d53c4-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d53c4-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d53c4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d53c4-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d53c4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d53c4-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="d53c4-119">'T</span></span>

<span data-ttu-id="d53c4-120">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="d53c4-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d53c4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d53c4-121">See Also</span></span>

- [<span data-ttu-id="d53c4-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="d53c4-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="d53c4-123">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="d53c4-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)