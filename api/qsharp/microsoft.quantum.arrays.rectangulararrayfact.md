---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730052"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="9d8cd-102">RectangularArrayFact función)</span><span class="sxs-lookup"><span data-stu-id="9d8cd-102">RectangularArrayFact function</span></span>

<span data-ttu-id="9d8cd-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9d8cd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9d8cd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d8cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d8cd-105">Representa una condición que una matriz bidimensional tiene una forma rectangular</span><span class="sxs-lookup"><span data-stu-id="9d8cd-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="9d8cd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d8cd-106">Description</span></span>

<span data-ttu-id="9d8cd-107">Esta función garantiza que cada fila de una matriz tiene la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="9d8cd-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="9d8cd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d8cd-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9d8cd-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="9d8cd-109">array : 'T[][]</span></span>

<span data-ttu-id="9d8cd-110">Matriz bidimensional de elementos.</span><span class="sxs-lookup"><span data-stu-id="9d8cd-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="9d8cd-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9d8cd-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9d8cd-112">Un mensaje que se va a imprimir si la matriz no es una matriz rectangular</span><span class="sxs-lookup"><span data-stu-id="9d8cd-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d8cd-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d8cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9d8cd-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9d8cd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d8cd-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="9d8cd-115">'T</span></span>

<span data-ttu-id="9d8cd-116">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="9d8cd-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d8cd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d8cd-117">See Also</span></span>

- [<span data-ttu-id="9d8cd-118">Microsoft. Quantum. arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="9d8cd-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)