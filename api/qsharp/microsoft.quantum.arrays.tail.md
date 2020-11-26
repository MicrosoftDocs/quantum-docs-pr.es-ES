---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail, función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220100"
---
# <a name="tail-function"></a><span data-ttu-id="19532-102">Tail, función</span><span class="sxs-lookup"><span data-stu-id="19532-102">Tail function</span></span>

<span data-ttu-id="19532-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="19532-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="19532-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19532-105">Devuelve el último elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="19532-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="19532-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="19532-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="19532-107">matriz: ' A []</span><span class="sxs-lookup"><span data-stu-id="19532-107">array : 'A[]</span></span>

<span data-ttu-id="19532-108">Matriz de la que se toma el último elemento.</span><span class="sxs-lookup"><span data-stu-id="19532-108">Array of which the last element is taken.</span></span> <span data-ttu-id="19532-109">La matriz debe tener una longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="19532-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="19532-110">Salida: ' A</span><span class="sxs-lookup"><span data-stu-id="19532-110">Output : 'A</span></span>

<span data-ttu-id="19532-111">Último elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="19532-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="19532-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="19532-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="19532-113">' A '</span><span class="sxs-lookup"><span data-stu-id="19532-113">'A</span></span>

<span data-ttu-id="19532-114">El tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="19532-114">The type of the array elements.</span></span>