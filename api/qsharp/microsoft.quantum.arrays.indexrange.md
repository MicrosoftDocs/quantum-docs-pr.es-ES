---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730204"
---
# <a name="indexrange-function"></a><span data-ttu-id="d2f47-102">IndexRange función)</span><span class="sxs-lookup"><span data-stu-id="d2f47-102">IndexRange function</span></span>

<span data-ttu-id="d2f47-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d2f47-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d2f47-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2f47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2f47-105">Dada una matriz, devuelve un intervalo sobre los índices de esa matriz, adecuado para su uso en un bucle for.</span><span class="sxs-lookup"><span data-stu-id="d2f47-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="d2f47-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d2f47-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="d2f47-107">matriz: ' Telement []</span><span class="sxs-lookup"><span data-stu-id="d2f47-107">array : 'TElement[]</span></span>

<span data-ttu-id="d2f47-108">Matriz para la que se debe devolver un intervalo de índices.</span><span class="sxs-lookup"><span data-stu-id="d2f47-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="d2f47-109">Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d2f47-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d2f47-110">Un intervalo de todos los índices de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d2f47-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d2f47-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d2f47-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="d2f47-112">' TEle</span><span class="sxs-lookup"><span data-stu-id="d2f47-112">'TElement</span></span>

<span data-ttu-id="d2f47-113">Tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d2f47-113">The type of elements of the array.</span></span>