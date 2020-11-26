---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220423"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="af028-102">RectangularArrayFact función)</span><span class="sxs-lookup"><span data-stu-id="af028-102">RectangularArrayFact function</span></span>

<span data-ttu-id="af028-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="af028-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="af028-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af028-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af028-105">Representa una condición que una matriz bidimensional tiene una forma rectangular</span><span class="sxs-lookup"><span data-stu-id="af028-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="af028-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="af028-106">Description</span></span>

<span data-ttu-id="af028-107">Esta función garantiza que cada fila de una matriz tiene la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="af028-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="af028-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="af028-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="af028-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="af028-109">array : 'T[][]</span></span>

<span data-ttu-id="af028-110">Matriz bidimensional de elementos.</span><span class="sxs-lookup"><span data-stu-id="af028-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="af028-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="af028-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="af028-112">Un mensaje que se va a imprimir si la matriz no es una matriz rectangular</span><span class="sxs-lookup"><span data-stu-id="af028-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="af028-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af028-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af028-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="af028-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af028-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="af028-115">'T</span></span>

<span data-ttu-id="af028-116">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="af028-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="af028-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af028-117">See Also</span></span>

- [<span data-ttu-id="af028-118">Microsoft. Quantum. arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="af028-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)