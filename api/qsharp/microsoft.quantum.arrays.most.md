---
uid: Microsoft.Quantum.Arrays.Most
title: La mayoría de las funciones
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730101"
---
# <a name="most-function"></a><span data-ttu-id="5474b-102">La mayoría de las funciones</span><span class="sxs-lookup"><span data-stu-id="5474b-102">Most function</span></span>

<span data-ttu-id="5474b-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5474b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5474b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5474b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5474b-105">Crea una matriz que es igual a una matriz de entrada, salvo que se quita el último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5474b-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5474b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5474b-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="5474b-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="5474b-107">array : 'T[]</span></span>

<span data-ttu-id="5474b-108">Matriz cuyo primer y último elemento se van a mostrar en la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="5474b-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5474b-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="5474b-109">Output : 'T[]</span></span>

<span data-ttu-id="5474b-110">Una matriz que contiene los elementos `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="5474b-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5474b-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="5474b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5474b-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="5474b-112">'T</span></span>

<span data-ttu-id="5474b-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5474b-113">The type of the array elements.</span></span>