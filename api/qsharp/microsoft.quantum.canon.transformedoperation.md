---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728343"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="931e8-102">TransformedOperation función)</span><span class="sxs-lookup"><span data-stu-id="931e8-102">TransformedOperation function</span></span>

<span data-ttu-id="931e8-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="931e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="931e8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="931e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="931e8-105">Dada una función y una operación, devuelve una nueva operación cuya entrada se transforma mediante la función especificada.</span><span class="sxs-lookup"><span data-stu-id="931e8-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="931e8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="931e8-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="931e8-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="931e8-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="931e8-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="931e8-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="931e8-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="931e8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="931e8-110">Operación que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="931e8-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="931e8-111">Salida: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="931e8-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="931e8-112">Una nueva operación tbat llama a `fn` con su entrada y, a continuación, pasa el resultado a `op` .</span><span class="sxs-lookup"><span data-stu-id="931e8-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="931e8-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="931e8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="931e8-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="931e8-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="931e8-115">' U</span><span class="sxs-lookup"><span data-stu-id="931e8-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="931e8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="931e8-116">See Also</span></span>

- [<span data-ttu-id="931e8-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="931e8-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="931e8-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="931e8-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="931e8-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="931e8-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="931e8-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="931e8-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="931e8-121">Microsoft. Quantum. Canon. compuestas</span><span class="sxs-lookup"><span data-stu-id="931e8-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)