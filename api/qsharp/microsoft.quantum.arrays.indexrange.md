---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220950"
---
# <a name="indexrange-function"></a><span data-ttu-id="03aef-102">IndexRange función)</span><span class="sxs-lookup"><span data-stu-id="03aef-102">IndexRange function</span></span>

<span data-ttu-id="03aef-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03aef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03aef-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="03aef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="03aef-105">Dada una matriz, devuelve un intervalo sobre los índices de esa matriz, adecuado para su uso en un bucle for.</span><span class="sxs-lookup"><span data-stu-id="03aef-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="03aef-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="03aef-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="03aef-107">matriz: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="03aef-107">array : 'TElement[]</span></span>

<span data-ttu-id="03aef-108">Matriz para la que se debe devolver un intervalo de índices.</span><span class="sxs-lookup"><span data-stu-id="03aef-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="03aef-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="03aef-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="03aef-110">Un intervalo de todos los índices de la matriz.</span><span class="sxs-lookup"><span data-stu-id="03aef-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="03aef-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="03aef-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="03aef-112">' TEle</span><span class="sxs-lookup"><span data-stu-id="03aef-112">'TElement</span></span>

<span data-ttu-id="03aef-113">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="03aef-113">The type of elements of the array.</span></span>