---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Función intercalada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730197"
---
# <a name="interleaved-function"></a><span data-ttu-id="a6e0a-102">Función intercalada</span><span class="sxs-lookup"><span data-stu-id="a6e0a-102">Interleaved function</span></span>

<span data-ttu-id="a6e0a-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a6e0a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a6e0a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6e0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6e0a-105">Intercala dos matrices de (casi) el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a6e0a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6e0a-106">Description</span></span>

<span data-ttu-id="a6e0a-107">Esta función devuelve el intercalado de dos matrices, comenzando por el primer elemento de la primera matriz, el primer elemento de la segunda matriz, etc.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="a6e0a-108">La primera matriz debe tener la misma longitud que la segunda, o bien puede tener un elemento más.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="a6e0a-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="a6e0a-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="a6e0a-110">primero: ' t []</span><span class="sxs-lookup"><span data-stu-id="a6e0a-110">first : 'T[]</span></span>

<span data-ttu-id="a6e0a-111">Primera matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="a6e0a-112">segundo: ' t []</span><span class="sxs-lookup"><span data-stu-id="a6e0a-112">second : 'T[]</span></span>

<span data-ttu-id="a6e0a-113">Segunda matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="a6e0a-114">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="a6e0a-114">Output : 'T[]</span></span>

<span data-ttu-id="a6e0a-115">Matriz intercalada</span><span class="sxs-lookup"><span data-stu-id="a6e0a-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a6e0a-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a6e0a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a6e0a-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="a6e0a-117">'T</span></span>

<span data-ttu-id="a6e0a-118">Tipo de cada elemento de `first` y `second` .</span><span class="sxs-lookup"><span data-stu-id="a6e0a-118">The type of each element of `first` and `second`.</span></span>