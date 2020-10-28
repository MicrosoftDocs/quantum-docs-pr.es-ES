---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operación ApplyWithInputTransformation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728997"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="52eaa-102">Operación ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="52eaa-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="52eaa-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="52eaa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="52eaa-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52eaa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52eaa-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="52eaa-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="52eaa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="52eaa-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="52eaa-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="52eaa-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="52eaa-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="52eaa-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="52eaa-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="52eaa-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="52eaa-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="52eaa-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="52eaa-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="52eaa-111">input : 'U</span></span>

<span data-ttu-id="52eaa-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="52eaa-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52eaa-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52eaa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="52eaa-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="52eaa-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="52eaa-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="52eaa-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="52eaa-116">' U</span><span class="sxs-lookup"><span data-stu-id="52eaa-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="52eaa-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52eaa-117">See Also</span></span>

- [<span data-ttu-id="52eaa-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="52eaa-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="52eaa-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="52eaa-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="52eaa-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="52eaa-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="52eaa-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="52eaa-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)