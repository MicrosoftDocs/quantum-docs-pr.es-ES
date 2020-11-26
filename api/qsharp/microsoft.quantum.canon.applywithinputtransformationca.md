---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Operación ApplyWithInputTransformationCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207792"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="dea16-102">Operación ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="dea16-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="dea16-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dea16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dea16-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dea16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dea16-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="dea16-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dea16-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dea16-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="dea16-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="dea16-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="dea16-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="dea16-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="dea16-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dea16-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dea16-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="dea16-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="dea16-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="dea16-111">input : 'U</span></span>

<span data-ttu-id="dea16-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="dea16-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dea16-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dea16-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dea16-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dea16-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dea16-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="dea16-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="dea16-116">' U</span><span class="sxs-lookup"><span data-stu-id="dea16-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="dea16-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dea16-117">See Also</span></span>

- [<span data-ttu-id="dea16-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="dea16-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="dea16-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="dea16-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="dea16-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="dea16-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="dea16-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="dea16-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)