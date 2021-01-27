---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845775"
---
# <a name="indexrange-function"></a><span data-ttu-id="145b6-102">IndexRange función)</span><span class="sxs-lookup"><span data-stu-id="145b6-102">IndexRange function</span></span>

<span data-ttu-id="145b6-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="145b6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="145b6-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="145b6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="145b6-105">Dada una matriz, devuelve un intervalo sobre los índices de esa matriz, adecuado para su uso en un bucle for.</span><span class="sxs-lookup"><span data-stu-id="145b6-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="145b6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="145b6-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="145b6-107">matriz: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="145b6-107">array : 'TElement[]</span></span>

<span data-ttu-id="145b6-108">Matriz para la que se debe devolver un intervalo de índices.</span><span class="sxs-lookup"><span data-stu-id="145b6-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="145b6-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="145b6-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="145b6-110">Un intervalo de todos los índices de la matriz.</span><span class="sxs-lookup"><span data-stu-id="145b6-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="145b6-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="145b6-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="145b6-112">' TEle</span><span class="sxs-lookup"><span data-stu-id="145b6-112">'TElement</span></span>

<span data-ttu-id="145b6-113">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="145b6-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="145b6-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="145b6-114">Example</span></span>

<span data-ttu-id="145b6-115">Los `for` bucles siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="145b6-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```