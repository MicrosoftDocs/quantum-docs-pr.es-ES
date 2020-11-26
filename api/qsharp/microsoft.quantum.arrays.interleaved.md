---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Función intercalada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220967"
---
# <a name="interleaved-function"></a><span data-ttu-id="25464-102">Función intercalada</span><span class="sxs-lookup"><span data-stu-id="25464-102">Interleaved function</span></span>

<span data-ttu-id="25464-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="25464-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="25464-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25464-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25464-105">Intercala dos matrices de (casi) el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="25464-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="25464-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="25464-106">Description</span></span>

<span data-ttu-id="25464-107">Esta función devuelve el intercalado de dos matrices, comenzando por el primer elemento de la primera matriz, el primer elemento de la segunda matriz, etc.</span><span class="sxs-lookup"><span data-stu-id="25464-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="25464-108">La primera matriz debe tener la misma longitud que la segunda, o bien puede tener un elemento más.</span><span class="sxs-lookup"><span data-stu-id="25464-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="25464-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="25464-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="25464-110">primero: ' t []</span><span class="sxs-lookup"><span data-stu-id="25464-110">first : 'T[]</span></span>

<span data-ttu-id="25464-111">Primera matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="25464-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="25464-112">segundo: ' t []</span><span class="sxs-lookup"><span data-stu-id="25464-112">second : 'T[]</span></span>

<span data-ttu-id="25464-113">Segunda matriz que se va a intercalar.</span><span class="sxs-lookup"><span data-stu-id="25464-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="25464-114">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="25464-114">Output : 'T[]</span></span>

<span data-ttu-id="25464-115">Matriz intercalada</span><span class="sxs-lookup"><span data-stu-id="25464-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="25464-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="25464-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25464-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="25464-117">'T</span></span>

<span data-ttu-id="25464-118">Tipo de cada elemento de `first` y `second` .</span><span class="sxs-lookup"><span data-stu-id="25464-118">The type of each element of `first` and `second`.</span></span>