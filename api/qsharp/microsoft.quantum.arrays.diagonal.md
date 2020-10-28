---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Función diagonal
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730357"
---
# <a name="diagonal-function"></a><span data-ttu-id="c7162-102">Función diagonal</span><span class="sxs-lookup"><span data-stu-id="c7162-102">Diagonal function</span></span>

<span data-ttu-id="c7162-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c7162-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c7162-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7162-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7162-105">Devuelve una matriz de elementos diagonales de una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="c7162-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c7162-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7162-106">Description</span></span>

<span data-ttu-id="c7162-107">Si la matriz bidimensional no tiene una forma cuadrada, se devolverá la diagonal sobre el número mínimo de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="c7162-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="c7162-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c7162-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="c7162-109">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c7162-109">matrix : 'T[][]</span></span>

<span data-ttu-id="c7162-110">matriz bidimensional en orden de fila</span><span class="sxs-lookup"><span data-stu-id="c7162-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="c7162-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="c7162-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c7162-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c7162-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7162-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="c7162-113">'T</span></span>

<span data-ttu-id="c7162-114">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="c7162-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7162-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7162-115">See Also</span></span>

- [<span data-ttu-id="c7162-116">Microsoft. Quantum. matrices. transpuesto</span><span class="sxs-lookup"><span data-stu-id="c7162-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)