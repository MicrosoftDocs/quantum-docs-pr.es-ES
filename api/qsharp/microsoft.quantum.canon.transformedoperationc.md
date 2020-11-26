---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204868"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="38c0b-102">TransformedOperationC función)</span><span class="sxs-lookup"><span data-stu-id="38c0b-102">TransformedOperationC function</span></span>

<span data-ttu-id="38c0b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38c0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38c0b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38c0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38c0b-105">Dada una función y una operación, devuelve una nueva operación cuya entrada se transforma mediante la función especificada.</span><span class="sxs-lookup"><span data-stu-id="38c0b-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="38c0b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="38c0b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="38c0b-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="38c0b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="38c0b-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="38c0b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="38c0b-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="38c0b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="38c0b-110">Operación que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="38c0b-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="38c0b-111">Salida: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="38c0b-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="38c0b-112">Una nueva operación tbat llama a `fn` con su entrada y, a continuación, pasa el resultado a `op` .</span><span class="sxs-lookup"><span data-stu-id="38c0b-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="38c0b-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="38c0b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38c0b-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="38c0b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="38c0b-115">' U</span><span class="sxs-lookup"><span data-stu-id="38c0b-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="38c0b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38c0b-116">See Also</span></span>

- [<span data-ttu-id="38c0b-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="38c0b-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="38c0b-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="38c0b-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="38c0b-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="38c0b-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="38c0b-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="38c0b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="38c0b-121">Microsoft. Quantum. Canon. compuestas</span><span class="sxs-lookup"><span data-stu-id="38c0b-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)