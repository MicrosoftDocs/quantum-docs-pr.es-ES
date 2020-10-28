---
uid: Microsoft.Quantum.Arrays.Transposed
title: Función transpuesta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729980"
---
# <a name="transposed-function"></a><span data-ttu-id="3c65f-102">Función transpuesta</span><span class="sxs-lookup"><span data-stu-id="3c65f-102">Transposed function</span></span>

<span data-ttu-id="3c65f-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3c65f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3c65f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c65f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c65f-105">Devuelve la transposición de una matriz representada como una matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="3c65f-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="3c65f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c65f-106">Description</span></span>

<span data-ttu-id="3c65f-107">Entrada como $r \times c $ Matrix con $r $ Rows y $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="3c65f-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="3c65f-108">La matriz está basada en filas; es decir, `matrix[i][j]` tiene acceso al elemento de la fila $i $ y a la columna $j $.</span><span class="sxs-lookup"><span data-stu-id="3c65f-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="3c65f-109">Esta función devuelve la matriz $c \times r $ que es la transformación de la matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="3c65f-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="3c65f-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c65f-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="3c65f-111">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="3c65f-111">matrix : 'T[][]</span></span>

<span data-ttu-id="3c65f-112">$R basado en filas \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="3c65f-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="3c65f-113">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="3c65f-113">Output : 'T[][]</span></span>

<span data-ttu-id="3c65f-114">$C \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="3c65f-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3c65f-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3c65f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c65f-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="3c65f-116">'T</span></span>

<span data-ttu-id="3c65f-117">Tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="3c65f-117">The type of each element of `matrix`.</span></span>