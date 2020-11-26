---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224384"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="b9787-102">FunctionAsOperation función)</span><span class="sxs-lookup"><span data-stu-id="b9787-102">FunctionAsOperation function</span></span>

<span data-ttu-id="b9787-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b9787-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b9787-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9787-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9787-105">Convierte funciones en operaciones.</span><span class="sxs-lookup"><span data-stu-id="b9787-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="b9787-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9787-106">Description</span></span>

<span data-ttu-id="b9787-107">Dada una función, devuelve una operación que llama a esa función y que no hace nada más.</span><span class="sxs-lookup"><span data-stu-id="b9787-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="b9787-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b9787-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="b9787-109">FN: salida de "entrada->"</span><span class="sxs-lookup"><span data-stu-id="b9787-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="b9787-110">Función que se va a convertir en una operación.</span><span class="sxs-lookup"><span data-stu-id="b9787-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="b9787-111">Salida: salida ' input => '</span><span class="sxs-lookup"><span data-stu-id="b9787-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="b9787-112">Operación `op` tal que `op(input)` es idéntica a `fn(input)` para todos los `input` .</span><span class="sxs-lookup"><span data-stu-id="b9787-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b9787-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b9787-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="b9787-114">' Entrada</span><span class="sxs-lookup"><span data-stu-id="b9787-114">'Input</span></span>

<span data-ttu-id="b9787-115">Tipo de entrada de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="b9787-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="b9787-116">' Output</span><span class="sxs-lookup"><span data-stu-id="b9787-116">'Output</span></span>

<span data-ttu-id="b9787-117">Tipo de salida de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="b9787-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9787-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9787-118">Remarks</span></span>

<span data-ttu-id="b9787-119">Esto es especialmente útil para pasar funciones a funciones u operaciones que esperan una operación como entrada.</span><span class="sxs-lookup"><span data-stu-id="b9787-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>