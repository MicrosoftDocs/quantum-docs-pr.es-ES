---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833300"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="3ac01-102">IntAsBoolArray función)</span><span class="sxs-lookup"><span data-stu-id="3ac01-102">IntAsBoolArray function</span></span>

<span data-ttu-id="3ac01-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="3ac01-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="3ac01-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ac01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ac01-105">Genera una representación binaria de un entero no negativo, utilizando la representación Little-Endian de la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="3ac01-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="3ac01-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ac01-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="3ac01-107">número: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ac01-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ac01-108">Entero no negativo que se va a convertir en una matriz de valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="3ac01-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="3ac01-109">bits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ac01-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ac01-110">Número de bits en la representación binaria de `number` .</span><span class="sxs-lookup"><span data-stu-id="3ac01-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3ac01-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3ac01-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3ac01-112">Matriz de valores booleanos que representan `number` .</span><span class="sxs-lookup"><span data-stu-id="3ac01-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ac01-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ac01-113">Remarks</span></span>

<span data-ttu-id="3ac01-114">La entrada `bits` debe estar comprendida entre 0 y 63.</span><span class="sxs-lookup"><span data-stu-id="3ac01-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="3ac01-115">La entrada `number` debe estar comprendida entre 0 y $2 ^ {\texttt{bits}}-$1.</span><span class="sxs-lookup"><span data-stu-id="3ac01-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>