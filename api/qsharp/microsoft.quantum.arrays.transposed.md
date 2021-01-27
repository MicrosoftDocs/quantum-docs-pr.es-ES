---
uid: Microsoft.Quantum.Arrays.Transposed
title: Función transpuesta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850931"
---
# <a name="transposed-function"></a><span data-ttu-id="76042-102">Función transpuesta</span><span class="sxs-lookup"><span data-stu-id="76042-102">Transposed function</span></span>

<span data-ttu-id="76042-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="76042-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="76042-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76042-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76042-105">Devuelve la transposición de una matriz representada como una matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="76042-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="76042-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="76042-106">Description</span></span>

<span data-ttu-id="76042-107">Entrada como $r \times c $ Matrix con $r $ Rows y $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="76042-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="76042-108">La matriz está basada en filas; es decir, `matrix[i][j]` tiene acceso al elemento de la fila $i $ y a la columna $j $.</span><span class="sxs-lookup"><span data-stu-id="76042-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="76042-109">Esta función devuelve la matriz $c \times r $ que es la transformación de la matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="76042-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="76042-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="76042-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="76042-111">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="76042-111">matrix : 'T[][]</span></span>

<span data-ttu-id="76042-112">$R basado en filas \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="76042-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="76042-113">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="76042-113">Output : 'T[][]</span></span>

<span data-ttu-id="76042-114">$C \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="76042-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76042-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="76042-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76042-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="76042-116">'T</span></span>

<span data-ttu-id="76042-117">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="76042-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="76042-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76042-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```