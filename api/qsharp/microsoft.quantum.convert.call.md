---
uid: Microsoft.Quantum.Convert.Call
title: Operación de llamada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850211"
---
# <a name="call-operation"></a><span data-ttu-id="13113-102">Operación de llamada</span><span class="sxs-lookup"><span data-stu-id="13113-102">Call operation</span></span>

<span data-ttu-id="13113-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="13113-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="13113-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13113-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13113-105">Llama a una función con una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="13113-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="13113-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="13113-106">Description</span></span>

<span data-ttu-id="13113-107">Dada una función y una entrada para esa función, llama a la función y devuelve su resultado.</span><span class="sxs-lookup"><span data-stu-id="13113-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="13113-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="13113-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="13113-109">FN: salida de "entrada->"</span><span class="sxs-lookup"><span data-stu-id="13113-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="13113-110">Función a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="13113-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="13113-111">entrada: ' entrada</span><span class="sxs-lookup"><span data-stu-id="13113-111">input : 'Input</span></span>

<span data-ttu-id="13113-112">Entrada que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="13113-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="13113-113">Salida: ' Output</span><span class="sxs-lookup"><span data-stu-id="13113-113">Output : 'Output</span></span>

<span data-ttu-id="13113-114">Resultado de llamar a `fn`.</span><span class="sxs-lookup"><span data-stu-id="13113-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="13113-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="13113-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="13113-116">' Entrada</span><span class="sxs-lookup"><span data-stu-id="13113-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="13113-117">' Output</span><span class="sxs-lookup"><span data-stu-id="13113-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="13113-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13113-118">Remarks</span></span>

<span data-ttu-id="13113-119">Esta operación es especialmente útil para forzar que se llame a una función en un lugar específico dentro de una operación, o para llamar a una función en la que se espera una operación.</span><span class="sxs-lookup"><span data-stu-id="13113-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>