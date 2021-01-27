---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845499"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="42532-102">RectangularArrayFact función)</span><span class="sxs-lookup"><span data-stu-id="42532-102">RectangularArrayFact function</span></span>

<span data-ttu-id="42532-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="42532-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="42532-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42532-105">Representa una condición que una matriz bidimensional tiene una forma rectangular</span><span class="sxs-lookup"><span data-stu-id="42532-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="42532-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="42532-106">Description</span></span>

<span data-ttu-id="42532-107">Esta función garantiza que cada fila de una matriz tiene la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="42532-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="42532-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="42532-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="42532-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="42532-109">array : 'T[][]</span></span>

<span data-ttu-id="42532-110">Matriz bidimensional de elementos.</span><span class="sxs-lookup"><span data-stu-id="42532-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="42532-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="42532-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="42532-112">Un mensaje que se va a imprimir si la matriz no es una matriz rectangular</span><span class="sxs-lookup"><span data-stu-id="42532-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="42532-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42532-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42532-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="42532-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42532-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="42532-115">'T</span></span>

<span data-ttu-id="42532-116">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="42532-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="42532-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42532-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="42532-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42532-118">See Also</span></span>

- [<span data-ttu-id="42532-119">Microsoft. Quantum. arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="42532-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)