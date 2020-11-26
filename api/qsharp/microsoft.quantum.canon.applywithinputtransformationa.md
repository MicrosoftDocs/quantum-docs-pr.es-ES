---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Operación ApplyWithInputTransformationA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207894"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="d1699-102">Operación ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="d1699-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="d1699-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1699-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1699-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1699-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1699-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="d1699-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d1699-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1699-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d1699-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="d1699-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d1699-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="d1699-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d1699-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="d1699-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d1699-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d1699-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d1699-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="d1699-111">input : 'U</span></span>

<span data-ttu-id="d1699-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="d1699-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1699-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1699-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1699-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d1699-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1699-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="d1699-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d1699-116">' U</span><span class="sxs-lookup"><span data-stu-id="d1699-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="d1699-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1699-117">See Also</span></span>

- [<span data-ttu-id="d1699-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d1699-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="d1699-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d1699-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="d1699-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="d1699-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="d1699-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d1699-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)