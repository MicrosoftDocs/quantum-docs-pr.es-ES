---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Función con particiones
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845538"
---
# <a name="partitioned-function"></a><span data-ttu-id="3503a-102">Función con particiones</span><span class="sxs-lookup"><span data-stu-id="3503a-102">Partitioned function</span></span>

<span data-ttu-id="3503a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3503a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3503a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3503a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3503a-105">Divide una matriz en varias partes.</span><span class="sxs-lookup"><span data-stu-id="3503a-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="3503a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3503a-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="3503a-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3503a-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3503a-108">Número de elementos de cada parte de la matriz</span><span class="sxs-lookup"><span data-stu-id="3503a-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="3503a-109">ARR: ' t []</span><span class="sxs-lookup"><span data-stu-id="3503a-109">arr : 'T[]</span></span>

<span data-ttu-id="3503a-110">Matriz de entrada que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="3503a-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="3503a-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="3503a-111">Output : 'T[][]</span></span>

<span data-ttu-id="3503a-112">Varias matrices donde la primera matriz es la primera `nElements[0]` de `arr` y la segunda matriz son las siguientes, `nElements[1]` `arr` etc. La última matriz contendrá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="3503a-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3503a-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3503a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3503a-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="3503a-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="3503a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3503a-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```