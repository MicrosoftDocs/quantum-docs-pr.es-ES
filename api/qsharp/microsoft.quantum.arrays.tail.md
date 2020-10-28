---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail, función
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729981"
---
# <a name="tail-function"></a><span data-ttu-id="d83a1-102">Tail, función</span><span class="sxs-lookup"><span data-stu-id="d83a1-102">Tail function</span></span>

<span data-ttu-id="d83a1-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d83a1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d83a1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d83a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d83a1-105">Devuelve el último elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d83a1-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="d83a1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d83a1-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="d83a1-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="d83a1-107">array : 'A[]</span></span>

<span data-ttu-id="d83a1-108">Matriz de la que se toma el último elemento.</span><span class="sxs-lookup"><span data-stu-id="d83a1-108">Array of which the last element is taken.</span></span> <span data-ttu-id="d83a1-109">La matriz debe tener una longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="d83a1-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="d83a1-110">Salida: ' A</span><span class="sxs-lookup"><span data-stu-id="d83a1-110">Output : 'A</span></span>

<span data-ttu-id="d83a1-111">Último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d83a1-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d83a1-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d83a1-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="d83a1-113">' A '</span><span class="sxs-lookup"><span data-stu-id="d83a1-113">'A</span></span>

<span data-ttu-id="d83a1-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d83a1-114">The type of the array elements.</span></span>