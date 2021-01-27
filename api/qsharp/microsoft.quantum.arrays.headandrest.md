---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848562"
---
# <a name="headandrest-function"></a><span data-ttu-id="fc44a-102">HeadAndRest función)</span><span class="sxs-lookup"><span data-stu-id="fc44a-102">HeadAndRest function</span></span>

<span data-ttu-id="fc44a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc44a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc44a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc44a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc44a-105">Devuelve una tupla del primer y el resto de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc44a-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="fc44a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc44a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fc44a-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="fc44a-107">array : 'A[]</span></span>

<span data-ttu-id="fc44a-108">Matriz con al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="fc44a-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="fc44a-109">Salida: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="fc44a-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="fc44a-110">Tupla del primer y de todos los elementos restantes de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc44a-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc44a-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fc44a-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fc44a-112">' A '</span><span class="sxs-lookup"><span data-stu-id="fc44a-112">'A</span></span>

<span data-ttu-id="fc44a-113">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fc44a-113">The type of the array elements.</span></span>