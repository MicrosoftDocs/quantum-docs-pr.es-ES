---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845602"
---
# <a name="mostandtail-function"></a><span data-ttu-id="fc028-102">MostAndTail función)</span><span class="sxs-lookup"><span data-stu-id="fc028-102">MostAndTail function</span></span>

<span data-ttu-id="fc028-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc028-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc028-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc028-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc028-105">Devuelve una tupla de todos menos uno y el último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc028-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="fc028-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc028-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fc028-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="fc028-107">array : 'A[]</span></span>

<span data-ttu-id="fc028-108">Matriz con al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="fc028-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="fc028-109">Salida: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="fc028-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="fc028-110">Una tupla de todos menos uno y el último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc028-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc028-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fc028-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fc028-112">' A '</span><span class="sxs-lookup"><span data-stu-id="fc028-112">'A</span></span>

<span data-ttu-id="fc028-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc028-113">The type of the array elements.</span></span>