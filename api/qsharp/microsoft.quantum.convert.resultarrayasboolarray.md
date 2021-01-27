---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832590"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="e8603-102">ResultArrayAsBoolArray función)</span><span class="sxs-lookup"><span data-stu-id="e8603-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="e8603-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e8603-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e8603-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8603-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8603-105">Convierte un `Result[]` tipo en un `Bool[]` tipo, donde `One` se asigna a `true` y `Zero` se asigna a `false` .</span><span class="sxs-lookup"><span data-stu-id="e8603-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="e8603-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8603-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="e8603-107">entrada: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="e8603-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="e8603-108">`Result[]` que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="e8603-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e8603-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e8603-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e8603-110">`Bool[]` que representa el `input`.</span><span class="sxs-lookup"><span data-stu-id="e8603-110">A `Bool[]` representing the `input`.</span></span>