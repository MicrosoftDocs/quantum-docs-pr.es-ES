---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730221"
---
# <a name="headandrest-function"></a><span data-ttu-id="a7970-102">HeadAndRest función)</span><span class="sxs-lookup"><span data-stu-id="a7970-102">HeadAndRest function</span></span>

<span data-ttu-id="a7970-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7970-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7970-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7970-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7970-105">Devuelve una tupla del primer y el resto de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7970-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="a7970-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7970-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a7970-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="a7970-107">array : 'A[]</span></span>

<span data-ttu-id="a7970-108">Matriz con al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="a7970-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a7970-109">Salida: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="a7970-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="a7970-110">Tupla del primer y de todos los elementos restantes de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7970-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7970-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a7970-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a7970-112">' A '</span><span class="sxs-lookup"><span data-stu-id="a7970-112">'A</span></span>

<span data-ttu-id="a7970-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7970-113">The type of the array elements.</span></span>