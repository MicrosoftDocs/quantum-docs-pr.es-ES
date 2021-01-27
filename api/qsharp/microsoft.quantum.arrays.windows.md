---
uid: Microsoft.Quantum.Arrays.Windows
title: Función de Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842190"
---
# <a name="windows-function"></a><span data-ttu-id="c79ec-102">Función de Windows</span><span class="sxs-lookup"><span data-stu-id="c79ec-102">Windows function</span></span>

<span data-ttu-id="c79ec-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c79ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c79ec-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c79ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c79ec-105">Devuelve todas las submatrices consecutivas de longitud `size` .</span><span class="sxs-lookup"><span data-stu-id="c79ec-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="c79ec-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c79ec-106">Description</span></span>

<span data-ttu-id="c79ec-107">Esta función devuelve todas las `n - size + 1` submatrices de longitud `size` en orden, donde `n` es la longitud de `arr` .</span><span class="sxs-lookup"><span data-stu-id="c79ec-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="c79ec-108">Las primeras submatrices son `arr[0..size - 1], arr[1..size], arr[2..size + 1]` hasta la última submatriz `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="c79ec-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="c79ec-109">Si `size <= 0` o `size > n` es, se devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="c79ec-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="c79ec-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="c79ec-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="c79ec-111">tamaño: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c79ec-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c79ec-112">Longitud de las submatrices.</span><span class="sxs-lookup"><span data-stu-id="c79ec-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="c79ec-113">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="c79ec-113">array : 'T[]</span></span>

<span data-ttu-id="c79ec-114">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="c79ec-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="c79ec-115">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c79ec-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c79ec-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c79ec-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c79ec-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="c79ec-117">'T</span></span>

<span data-ttu-id="c79ec-118">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="c79ec-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="c79ec-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c79ec-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```