---
uid: Microsoft.Quantum.Arrays.Windows
title: Función de Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219896"
---
# <a name="windows-function"></a><span data-ttu-id="1c714-102">Función de Windows</span><span class="sxs-lookup"><span data-stu-id="1c714-102">Windows function</span></span>

<span data-ttu-id="1c714-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1c714-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1c714-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c714-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c714-105">Devuelve todas las submatrices consecutivas de longitud `size` .</span><span class="sxs-lookup"><span data-stu-id="1c714-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="1c714-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c714-106">Description</span></span>

<span data-ttu-id="1c714-107">Esta función devuelve todas las `n - size + 1` submatrices de longitud `size` en orden, donde `n` es la longitud de `arr` .</span><span class="sxs-lookup"><span data-stu-id="1c714-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="1c714-108">Las primeras submatrices son `arr[0..size - 1], arr[1..size], arr[2..size + 1]` hasta la última submatriz `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="1c714-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="1c714-109">Si `size <= 0` o `size > n` es, se devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="1c714-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="1c714-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c714-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="1c714-111">tamaño: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c714-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c714-112">Longitud de las submatrices.</span><span class="sxs-lookup"><span data-stu-id="1c714-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="1c714-113">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="1c714-113">array : 'T[]</span></span>

<span data-ttu-id="1c714-114">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="1c714-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="1c714-115">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="1c714-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c714-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1c714-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c714-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="1c714-117">'T</span></span>

<span data-ttu-id="1c714-118">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="1c714-118">The type of `array` elements.</span></span>