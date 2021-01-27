---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846252"
---
# <a name="columnat-function"></a><span data-ttu-id="87af6-102">ColumnAt función)</span><span class="sxs-lookup"><span data-stu-id="87af6-102">ColumnAt function</span></span>

<span data-ttu-id="87af6-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="87af6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="87af6-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87af6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87af6-105">Extrae una columna de una matriz.</span><span class="sxs-lookup"><span data-stu-id="87af6-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="87af6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="87af6-106">Description</span></span>

<span data-ttu-id="87af6-107">Esta función extrae una columna de una matriz en orden de fila.</span><span class="sxs-lookup"><span data-stu-id="87af6-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="87af6-108">Extraer una fila corrsponds al acceso a elementos del primer índice y, por lo tanto, no requiere ningún tratamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="87af6-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="87af6-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="87af6-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="87af6-110">columna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87af6-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87af6-111">Columna de la matriz</span><span class="sxs-lookup"><span data-stu-id="87af6-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="87af6-112">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="87af6-112">matrix : 'T[][]</span></span>

<span data-ttu-id="87af6-113">matriz bidimensional en orden de fila</span><span class="sxs-lookup"><span data-stu-id="87af6-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="87af6-114">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="87af6-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87af6-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="87af6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87af6-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="87af6-116">'T</span></span>

<span data-ttu-id="87af6-117">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="87af6-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="87af6-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87af6-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="87af6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87af6-119">See Also</span></span>

- [<span data-ttu-id="87af6-120">Microsoft. Quantum. matrices. transpuesto</span><span class="sxs-lookup"><span data-stu-id="87af6-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="87af6-121">Microsoft. Quantum. matrices. Diagonal</span><span class="sxs-lookup"><span data-stu-id="87af6-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)