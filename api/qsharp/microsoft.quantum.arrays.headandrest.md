---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221086"
---
# <a name="headandrest-function"></a><span data-ttu-id="41c69-102">HeadAndRest función)</span><span class="sxs-lookup"><span data-stu-id="41c69-102">HeadAndRest function</span></span>

<span data-ttu-id="41c69-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41c69-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41c69-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41c69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41c69-105">Devuelve una tupla del primer y el resto de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="41c69-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="41c69-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="41c69-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="41c69-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="41c69-107">array : 'A[]</span></span>

<span data-ttu-id="41c69-108">Matriz con al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="41c69-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="41c69-109">Salida: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="41c69-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="41c69-110">Tupla del primer y de todos los elementos restantes de la matriz.</span><span class="sxs-lookup"><span data-stu-id="41c69-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="41c69-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="41c69-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="41c69-112">' A '</span><span class="sxs-lookup"><span data-stu-id="41c69-112">'A</span></span>

<span data-ttu-id="41c69-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="41c69-113">The type of the array elements.</span></span>