---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727538"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="4b0b3-102">IntAsBoolArray función)</span><span class="sxs-lookup"><span data-stu-id="4b0b3-102">IntAsBoolArray function</span></span>

<span data-ttu-id="4b0b3-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4b0b3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4b0b3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b0b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b0b3-105">Genera una representación binaria de un entero positivo, utilizando la representación Little-Endian de la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="4b0b3-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="4b0b3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b0b3-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="4b0b3-107">número: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b0b3-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b0b3-108">Entero positivo que se va a convertir en una matriz de valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="4b0b3-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="4b0b3-109">bits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b0b3-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b0b3-110">Número de bits en la representación binaria de `number` .</span><span class="sxs-lookup"><span data-stu-id="4b0b3-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4b0b3-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4b0b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4b0b3-112">Matriz de valores booleanos que representan `number` .</span><span class="sxs-lookup"><span data-stu-id="4b0b3-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b0b3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b0b3-113">Remarks</span></span>

<span data-ttu-id="4b0b3-114">La entrada `bits` debe estar comprendida entre 0 y 63.</span><span class="sxs-lookup"><span data-stu-id="4b0b3-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="4b0b3-115">La entrada `number` debe estar comprendida entre 0 y $2 ^ {\texttt{bits}}-$1.</span><span class="sxs-lookup"><span data-stu-id="4b0b3-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>