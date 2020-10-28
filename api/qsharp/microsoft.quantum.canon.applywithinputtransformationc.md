---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Operación ApplyWithInputTransformationC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728990"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="d9a84-102">Operación ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d9a84-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="d9a84-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9a84-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9a84-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9a84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9a84-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="d9a84-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="d9a84-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d9a84-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d9a84-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="d9a84-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d9a84-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="d9a84-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="d9a84-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9a84-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d9a84-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d9a84-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d9a84-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="d9a84-111">input : 'U</span></span>

<span data-ttu-id="d9a84-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="d9a84-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9a84-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9a84-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d9a84-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d9a84-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9a84-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="d9a84-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d9a84-116">' U</span><span class="sxs-lookup"><span data-stu-id="d9a84-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="d9a84-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9a84-117">See Also</span></span>

- [<span data-ttu-id="d9a84-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d9a84-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="d9a84-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="d9a84-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="d9a84-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="d9a84-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="d9a84-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d9a84-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)