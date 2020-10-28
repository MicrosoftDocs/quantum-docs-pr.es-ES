---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727562"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="0b225-102">FunctionAsOperation función)</span><span class="sxs-lookup"><span data-stu-id="0b225-102">FunctionAsOperation function</span></span>

<span data-ttu-id="0b225-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0b225-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0b225-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b225-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b225-105">Convierte funciones en operaciones.</span><span class="sxs-lookup"><span data-stu-id="0b225-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="0b225-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b225-106">Description</span></span>

<span data-ttu-id="0b225-107">Dada una función, devuelve una operación que llama a esa función y que no hace nada más.</span><span class="sxs-lookup"><span data-stu-id="0b225-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="0b225-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b225-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="0b225-109">FN: salida de "entrada->"</span><span class="sxs-lookup"><span data-stu-id="0b225-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="0b225-110">Función que se va a convertir en una operación.</span><span class="sxs-lookup"><span data-stu-id="0b225-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="0b225-111">Salida: salida ' input => '</span><span class="sxs-lookup"><span data-stu-id="0b225-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="0b225-112">Operación `op` tal que `op(input)` es idéntica a `fn(input)` para todos los `input` .</span><span class="sxs-lookup"><span data-stu-id="0b225-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b225-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0b225-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="0b225-114">' Entrada</span><span class="sxs-lookup"><span data-stu-id="0b225-114">'Input</span></span>

<span data-ttu-id="0b225-115">Tipo de entrada de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="0b225-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="0b225-116">' Output</span><span class="sxs-lookup"><span data-stu-id="0b225-116">'Output</span></span>

<span data-ttu-id="0b225-117">Tipo de salida de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="0b225-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b225-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0b225-118">Remarks</span></span>

<span data-ttu-id="0b225-119">Esto es especialmente útil para pasar funciones a funciones u operaciones que esperan una operación como entrada.</span><span class="sxs-lookup"><span data-stu-id="0b225-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>