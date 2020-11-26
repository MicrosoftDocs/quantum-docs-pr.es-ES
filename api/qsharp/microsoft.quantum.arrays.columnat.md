---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210109"
---
# <a name="columnat-function"></a><span data-ttu-id="4acf1-102">ColumnAt función)</span><span class="sxs-lookup"><span data-stu-id="4acf1-102">ColumnAt function</span></span>

<span data-ttu-id="4acf1-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4acf1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4acf1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4acf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4acf1-105">Extrae una columna de una matriz.</span><span class="sxs-lookup"><span data-stu-id="4acf1-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4acf1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4acf1-106">Description</span></span>

<span data-ttu-id="4acf1-107">Esta función extrae una columna de una matriz en orden de fila.</span><span class="sxs-lookup"><span data-stu-id="4acf1-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="4acf1-108">Extraer una fila corrsponds al acceso a elementos del primer índice y, por lo tanto, no requiere ningún tratamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="4acf1-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="4acf1-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="4acf1-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="4acf1-110">columna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4acf1-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4acf1-111">Columna de la matriz</span><span class="sxs-lookup"><span data-stu-id="4acf1-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="4acf1-112">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="4acf1-112">matrix : 'T[][]</span></span>

<span data-ttu-id="4acf1-113">matriz bidimensional en orden de fila</span><span class="sxs-lookup"><span data-stu-id="4acf1-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="4acf1-114">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="4acf1-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4acf1-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4acf1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4acf1-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="4acf1-116">'T</span></span>

<span data-ttu-id="4acf1-117">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="4acf1-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4acf1-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4acf1-118">See Also</span></span>

- [<span data-ttu-id="4acf1-119">Microsoft. Quantum. matrices. transpuesto</span><span class="sxs-lookup"><span data-stu-id="4acf1-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="4acf1-120">Microsoft. Quantum. matrices. Diagonal</span><span class="sxs-lookup"><span data-stu-id="4acf1-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)