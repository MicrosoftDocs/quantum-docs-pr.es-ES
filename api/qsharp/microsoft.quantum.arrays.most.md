---
uid: Microsoft.Quantum.Arrays.Most
title: La mayoría de las funciones
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845575"
---
# <a name="most-function"></a><span data-ttu-id="cd887-102">La mayoría de las funciones</span><span class="sxs-lookup"><span data-stu-id="cd887-102">Most function</span></span>

<span data-ttu-id="cd887-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cd887-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cd887-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd887-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd887-105">Crea una matriz que es igual a una matriz de entrada, salvo que se quita el último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cd887-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cd887-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd887-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="cd887-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="cd887-107">array : 'T[]</span></span>

<span data-ttu-id="cd887-108">Matriz cuyo primer y último elemento se van a mostrar en la matriz de salida.</span><span class="sxs-lookup"><span data-stu-id="cd887-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="cd887-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="cd887-109">Output : 'T[]</span></span>

<span data-ttu-id="cd887-110">Una matriz que contiene los elementos `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="cd887-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cd887-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="cd887-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cd887-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="cd887-112">'T</span></span>

<span data-ttu-id="cd887-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cd887-113">The type of the array elements.</span></span>