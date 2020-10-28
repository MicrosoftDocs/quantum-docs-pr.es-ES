---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixes (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730061"
---
# <a name="prefixes-function"></a><span data-ttu-id="3ad0d-102">Prefixes (función)</span><span class="sxs-lookup"><span data-stu-id="3ad0d-102">Prefixes function</span></span>

<span data-ttu-id="3ad0d-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3ad0d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3ad0d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ad0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ad0d-105">Dada una matriz, devuelve todos sus prefijos.</span><span class="sxs-lookup"><span data-stu-id="3ad0d-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="3ad0d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ad0d-106">Description</span></span>

<span data-ttu-id="3ad0d-107">Devuelve una matriz de todos los prefijos, empezando por una matriz que solo tiene el primer elemento hasta la matriz completa.</span><span class="sxs-lookup"><span data-stu-id="3ad0d-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="3ad0d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ad0d-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3ad0d-109">matriz: ' t []</span><span class="sxs-lookup"><span data-stu-id="3ad0d-109">array : 'T[]</span></span>

<span data-ttu-id="3ad0d-110">Matriz de elementos.</span><span class="sxs-lookup"><span data-stu-id="3ad0d-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="3ad0d-111">Salida: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="3ad0d-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ad0d-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="3ad0d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3ad0d-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="3ad0d-113">'T</span></span>

<span data-ttu-id="3ad0d-114">Tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="3ad0d-114">The type of `array` elements.</span></span>