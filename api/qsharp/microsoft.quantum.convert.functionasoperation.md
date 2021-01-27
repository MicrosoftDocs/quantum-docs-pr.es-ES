---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833841"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="d4d08-102">FunctionAsOperation función)</span><span class="sxs-lookup"><span data-stu-id="d4d08-102">FunctionAsOperation function</span></span>

<span data-ttu-id="d4d08-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d4d08-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d4d08-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4d08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4d08-105">Convierte funciones en operaciones.</span><span class="sxs-lookup"><span data-stu-id="d4d08-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="d4d08-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4d08-106">Description</span></span>

<span data-ttu-id="d4d08-107">Dada una función, devuelve una operación que llama a esa función y que no hace nada más.</span><span class="sxs-lookup"><span data-stu-id="d4d08-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="d4d08-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d4d08-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="d4d08-109">FN: salida de "entrada->"</span><span class="sxs-lookup"><span data-stu-id="d4d08-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="d4d08-110">Función que se va a convertir en una operación.</span><span class="sxs-lookup"><span data-stu-id="d4d08-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="d4d08-111">Salida: salida ' input => '</span><span class="sxs-lookup"><span data-stu-id="d4d08-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="d4d08-112">Operación `op` tal que `op(input)` es idéntica a `fn(input)` para todos los `input` .</span><span class="sxs-lookup"><span data-stu-id="d4d08-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d4d08-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d4d08-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="d4d08-114">' Entrada</span><span class="sxs-lookup"><span data-stu-id="d4d08-114">'Input</span></span>

<span data-ttu-id="d4d08-115">Tipo de entrada de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d4d08-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="d4d08-116">' Output</span><span class="sxs-lookup"><span data-stu-id="d4d08-116">'Output</span></span>

<span data-ttu-id="d4d08-117">Tipo de salida de la función que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d4d08-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4d08-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4d08-118">Remarks</span></span>

<span data-ttu-id="d4d08-119">Esto es especialmente útil para pasar funciones a funciones u operaciones que esperan una operación como entrada.</span><span class="sxs-lookup"><span data-stu-id="d4d08-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>