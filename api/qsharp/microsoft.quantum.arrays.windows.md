---
uid: Microsoft.Quantum.Arrays.Windows
title: Función de Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729933"
---
# <a name="windows-function"></a><span data-ttu-id="281c4-102">Función de Windows</span><span class="sxs-lookup"><span data-stu-id="281c4-102">Windows function</span></span>

<span data-ttu-id="281c4-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="281c4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="281c4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="281c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="281c4-105">Devuelve todas las submatrices consecutivas de longitud `size` .</span><span class="sxs-lookup"><span data-stu-id="281c4-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="281c4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="281c4-106">Description</span></span>

<span data-ttu-id="281c4-107">Esta función devuelve todas las `n - size + 1` submatrices de longitud `size` en orden, donde `n` es la longitud de `arr` .</span><span class="sxs-lookup"><span data-stu-id="281c4-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="281c4-108">Las primeras submatrices son `arr[0..size - 1], arr[1..size], arr[2..size + 1]` hasta la última submatriz `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="281c4-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="281c4-109">Si `size <= 0` o `size > n` es, se devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="281c4-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="281c4-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="281c4-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="281c4-111">tamaño: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="281c4-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="281c4-112">Longitud de las submatrices.</span><span class="sxs-lookup"><span data-stu-id="281c4-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="281c4-113">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="281c4-113">array : 'T[]</span></span>

<span data-ttu-id="281c4-114">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="281c4-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="281c4-115">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="281c4-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="281c4-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="281c4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="281c4-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="281c4-117">'T</span></span>

<span data-ttu-id="281c4-118">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="281c4-118">The type of `array` elements.</span></span>