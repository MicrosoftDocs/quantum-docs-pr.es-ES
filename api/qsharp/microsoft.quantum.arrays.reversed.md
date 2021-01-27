---
uid: Microsoft.Quantum.Arrays.Reversed
title: Función invertida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845456"
---
# <a name="reversed-function"></a><span data-ttu-id="408fb-102">Función invertida</span><span class="sxs-lookup"><span data-stu-id="408fb-102">Reversed function</span></span>

<span data-ttu-id="408fb-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="408fb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="408fb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="408fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="408fb-105">Cree una matriz que contenga los mismos elementos que una matriz de entrada, pero en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="408fb-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="408fb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="408fb-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="408fb-107">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="408fb-107">array : 'T[]</span></span>

<span data-ttu-id="408fb-108">Una matriz cuyos elementos se van a copiar en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="408fb-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="408fb-109">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="408fb-109">Output : 'T[]</span></span>

<span data-ttu-id="408fb-110">Una matriz que contiene los elementos `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="408fb-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="408fb-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="408fb-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="408fb-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="408fb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="408fb-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="408fb-113">'T</span></span>

<span data-ttu-id="408fb-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="408fb-114">The type of the array elements.</span></span>