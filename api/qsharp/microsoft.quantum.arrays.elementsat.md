---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 295aa4e2d79857405186b835d9788f59db83d1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842788"
---
# <a name="elementsat-function"></a><span data-ttu-id="d11af-102">ElementsAt función)</span><span class="sxs-lookup"><span data-stu-id="d11af-102">ElementsAt function</span></span>

<span data-ttu-id="d11af-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d11af-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d11af-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d11af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d11af-105">Devuelve los elementos de la matriz en un intervalo determinado de índices.</span><span class="sxs-lookup"><span data-stu-id="d11af-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d11af-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d11af-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="d11af-107">intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d11af-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d11af-108">Intervalo de índices de matriz</span><span class="sxs-lookup"><span data-stu-id="d11af-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="d11af-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="d11af-109">array : 'T[]</span></span>

<span data-ttu-id="d11af-110">Array</span><span class="sxs-lookup"><span data-stu-id="d11af-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="d11af-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="d11af-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d11af-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d11af-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d11af-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="d11af-113">'T</span></span>

<span data-ttu-id="d11af-114">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="d11af-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="d11af-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d11af-115">Example</span></span>

<span data-ttu-id="d11af-116">Obtiene los índices impares en secuencias enteras famosas.</span><span class="sxs-lookup"><span data-stu-id="d11af-116">Get the odd indexes in famous integer sequences.</span></span> <span data-ttu-id="d11af-117">(tenga en cuenta que el índice 0 corresponde al _primer_ valor de la secuencia.)</span><span class="sxs-lookup"><span data-stu-id="d11af-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famousOdd = Mapped(ElementsAt<Int>(0..2..9, _), [lucas, prime, fibonacci, catalan]);
// same as: famousOdd = [[2, 3, 7, 18, 47], [2, 5, 11, 17, 23], [0, 1, 3, 8, 21], [1, 2, 14, 132, 1430]]
```

## <a name="see-also"></a><span data-ttu-id="d11af-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d11af-118">See Also</span></span>

- [<span data-ttu-id="d11af-119">Microsoft. Quantum. arrays. ElementAt</span><span class="sxs-lookup"><span data-stu-id="d11af-119">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="d11af-120">Microsoft. Quantum. arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="d11af-120">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)