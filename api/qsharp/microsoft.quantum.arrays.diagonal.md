---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Función diagonal
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842824"
---
# <a name="diagonal-function"></a><span data-ttu-id="e19ef-102">Función diagonal</span><span class="sxs-lookup"><span data-stu-id="e19ef-102">Diagonal function</span></span>

<span data-ttu-id="e19ef-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e19ef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e19ef-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e19ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e19ef-105">Devuelve una matriz de elementos diagonales de una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="e19ef-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="e19ef-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e19ef-106">Description</span></span>

<span data-ttu-id="e19ef-107">Si la matriz bidimensional no tiene una forma cuadrada, se devolverá la diagonal sobre el número mínimo de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="e19ef-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="e19ef-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e19ef-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="e19ef-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="e19ef-109">matrix : 'T[][]</span></span>

<span data-ttu-id="e19ef-110">matriz bidimensional en orden de fila</span><span class="sxs-lookup"><span data-stu-id="e19ef-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="e19ef-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="e19ef-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e19ef-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e19ef-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e19ef-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="e19ef-113">'T</span></span>

<span data-ttu-id="e19ef-114">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="e19ef-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="e19ef-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e19ef-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="e19ef-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e19ef-116">See Also</span></span>

- [<span data-ttu-id="e19ef-117">Microsoft. Quantum. matrices. transpuesto</span><span class="sxs-lookup"><span data-stu-id="e19ef-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)