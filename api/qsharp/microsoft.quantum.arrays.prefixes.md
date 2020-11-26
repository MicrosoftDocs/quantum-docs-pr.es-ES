---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixes (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220403"
---
# <a name="prefixes-function"></a><span data-ttu-id="b6afa-102">Prefixes (función)</span><span class="sxs-lookup"><span data-stu-id="b6afa-102">Prefixes function</span></span>

<span data-ttu-id="b6afa-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b6afa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b6afa-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6afa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6afa-105">Dada una matriz, devuelve todos sus prefijos.</span><span class="sxs-lookup"><span data-stu-id="b6afa-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b6afa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6afa-106">Description</span></span>

<span data-ttu-id="b6afa-107">Devuelve una matriz de todos los prefijos, empezando por una matriz que solo tiene el primer elemento hasta la matriz completa.</span><span class="sxs-lookup"><span data-stu-id="b6afa-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="b6afa-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b6afa-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b6afa-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="b6afa-109">array : 'T[]</span></span>

<span data-ttu-id="b6afa-110">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="b6afa-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b6afa-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="b6afa-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b6afa-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b6afa-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6afa-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="b6afa-113">'T</span></span>

<span data-ttu-id="b6afa-114">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="b6afa-114">The type of `array` elements.</span></span>