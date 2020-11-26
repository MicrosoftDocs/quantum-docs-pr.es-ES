---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220202"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="37959-102">SquareArrayFact función)</span><span class="sxs-lookup"><span data-stu-id="37959-102">SquareArrayFact function</span></span>

<span data-ttu-id="37959-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="37959-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="37959-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37959-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37959-105">Representa una condición que una matriz bidimensional tiene una forma cuadrada</span><span class="sxs-lookup"><span data-stu-id="37959-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="37959-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="37959-106">Description</span></span>

<span data-ttu-id="37959-107">Esta función garantiza que cada fila de una matriz tiene tantos elementos como filas (elementos) en la matriz.</span><span class="sxs-lookup"><span data-stu-id="37959-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="37959-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="37959-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="37959-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="37959-109">array : 'T[][]</span></span>

<span data-ttu-id="37959-110">Matriz bidimensional de elementos.</span><span class="sxs-lookup"><span data-stu-id="37959-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="37959-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="37959-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="37959-112">Un mensaje que se va a imprimir si la matriz no es una matriz cuadrada</span><span class="sxs-lookup"><span data-stu-id="37959-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="37959-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37959-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37959-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="37959-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37959-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="37959-115">'T</span></span>

<span data-ttu-id="37959-116">Tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="37959-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="37959-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37959-117">See Also</span></span>

- [<span data-ttu-id="37959-118">Microsoft. Quantum. arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="37959-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)