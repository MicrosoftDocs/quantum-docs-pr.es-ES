---
uid: Microsoft.Quantum.Canon.Delay
title: Operación de retraso
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840656"
---
# <a name="delay-operation"></a><span data-ttu-id="d7bf0-102">Operación de retraso</span><span class="sxs-lookup"><span data-stu-id="d7bf0-102">Delay operation</span></span>

<span data-ttu-id="d7bf0-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7bf0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7bf0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7bf0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7bf0-105">Aplica una operación determinada con un retraso.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="d7bf0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7bf0-106">Description</span></span>

<span data-ttu-id="d7bf0-107">Dada una operación y una entrada para esa operación, se aplica la operación una vez que se proporciona una entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="d7bf0-108">En concreto, la expresión `Delay(op, arg, _)` es una operación que se aplica `op` a `arg` cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="d7bf0-109">`Delay(op,arg,_)`La expresión permite retrasar la aplicación de `op` .</span><span class="sxs-lookup"><span data-stu-id="d7bf0-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="d7bf0-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7bf0-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="d7bf0-111">OP: ' t => ' U</span><span class="sxs-lookup"><span data-stu-id="d7bf0-111">op : 'T => 'U</span></span> 

<span data-ttu-id="d7bf0-112">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="d7bf0-113">Arg: ' t</span><span class="sxs-lookup"><span data-stu-id="d7bf0-113">arg : 'T</span></span>

<span data-ttu-id="d7bf0-114">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="d7bf0-115">AUX: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7bf0-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="d7bf0-116">Argumento que se usa para retrasar la aplicación de la operación mediante el uso de una aplicación parcial.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="d7bf0-117">Salida: ' U</span><span class="sxs-lookup"><span data-stu-id="d7bf0-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7bf0-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d7bf0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7bf0-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="d7bf0-119">'T</span></span>

<span data-ttu-id="d7bf0-120">Tipo de entrada de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="d7bf0-121">' U</span><span class="sxs-lookup"><span data-stu-id="d7bf0-121">'U</span></span>

<span data-ttu-id="d7bf0-122">El tipo de valor devuelto de la operación que se va a retrasar.</span><span class="sxs-lookup"><span data-stu-id="d7bf0-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7bf0-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7bf0-123">See Also</span></span>

- [<span data-ttu-id="d7bf0-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="d7bf0-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="d7bf0-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="d7bf0-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="d7bf0-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="d7bf0-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="d7bf0-127">Microsoft. Quantum. Canon. retrasado</span><span class="sxs-lookup"><span data-stu-id="d7bf0-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)